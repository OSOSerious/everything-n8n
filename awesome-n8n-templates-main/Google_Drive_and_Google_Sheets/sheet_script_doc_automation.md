# Sheet → Script Doc Automation

This workflow turns each “idea” row in Google Sheets into a finished script stored in Google Docs and logs the result back into Sheets. Use it when you want agents (ChatGPT, Claude, etc.) to pull context from a sheet, draft the copy, and write the finished asset plus links to a tracking tab.

---

## Prerequisites

| Component | Purpose | Where to Configure |
|-----------|---------|--------------------|
| Google Sheets OAuth credential | Read/write both the **Ideas** (source) and **Scripts** (log) tabs | Google Cloud Console → enable *Google Sheets API* → OAuth client → add to n8n under `googleSheetsOAuth2Api` |
| Google Docs OAuth credential | Create and update the generated Docs in your Drive folder | Same OAuth client can be reused; add a `googleDocsOAuth2Api` credential in n8n |
| OpenAI (or compatible) API key | Runs the LLM steps that actually write the script | OpenAI dashboard → API Keys → create key → add to n8n `openAiApi` credential |
| Google Drive folder ID | Where finished scripts should live | Copy the folder ID from its Drive URL |

> **Tip:** If you already have one Google OAuth credential in n8n you can reuse it for both Sheets and Docs by duplicating it and changing only the name.

---

## Sheet & Folder Structure

1. **Ideas Tab (sourceSheet)**
   - Required columns: `Idea` (or `Topic`), `Persona`, `row_number` (use Google Sheets formula `ROW()`), optional `Outline`, `Brief`, `Key Points`, `Pain Points`, `Reference Doc URL` / `Module Doc URL`.
   - Leave `Script Doc URL` and `Script Status` empty; the workflow fills them in.

2. **Scripts Tab (outputSheet)**
   - Include headers: `Idea`, `Persona`, `Reference Doc URL`, `Generated Doc URL`, `Generated At`.
   - The workflow appends a new row after each run so you have a historical log.

3. **Drive Folder**
   - Create a folder just for these scripts and copy its ID (the long string between `/folders/` and the next `/` in the URL). Paste that value into the Config node’s `folderId`.

---

## Installation & Setup

1. **Import the workflow**
   ```bash
   n8n import:workflow --input awesome-n8n-templates-main/Google_Drive_and_Google_Sheets/sheet_script_doc_automation.json
   ```

2. **Configure the `Config` node**
   - `sheetUrl`: full URL of your spreadsheet.
   - `sourceSheet`: tab name with the ideas (default `Ideas`).
   - `outputSheet`: tab name for the log (default `Scripts`).
   - `folderId`: Google Drive folder for finished docs.
   - `defaultPersona`: fallback persona prompt when the row doesn’t specify one.

3. **Attach credentials**
   - `Fetch Pending Rows`, `Append Script Row`, and `Update Source Row` → select your Google Sheets credential.
   - `Create Script Doc` and `Write Script Body` → select your Google Docs credential.
   - `Script Writer LLM`/`Generate Script` combo → select your OpenAI credential.

4. **Seed data**
   - Add at least one row in the Ideas tab with an `Idea` and `Persona`. Optional reference URLs or outlines enhance the prompt.

---

## How the Workflow Runs

1. **Manual Start / Scheduler (optional)** kicks things off.
2. **Config node** loads all runtime settings (sheet URL, tabs, folders, default persona).
3. **Fetch Pending Rows** pulls the entire Ideas tab; **Filter Pending Rows** keeps only rows missing a `Script Doc URL`.
4. **Loop Rows (SplitInBatches)** processes one idea at a time.
5. **Prepare Prompt** merges row data + persona + reference doc and crafts a detailed LLM prompt.
6. **Script Writer LLM + Generate Script** run the chain (leveraging `lmChatOpenAi` as the language model for `chainLlm`).
7. **Create Script Doc** spins up a Google Doc in your target folder and **Write Script Body** inserts the generated markdown/text.
8. **Append Script Row** logs a summary in the Scripts tab, while **Update Source Row** backfills `Script Doc URL` & `Script Status` in the original idea row.
9. Loop continues until no pending rows remain.

---

## Testing & Operation

1. Run the workflow manually once to verify it can access Sheets/Docs and the OpenAI key is active.
2. Check Google Drive for the new doc, then confirm the Scripts tab and the original idea row were updated.
3. After validation, add a `Schedule Trigger` node (hourly/daily) so it polls the sheet automatically.
4. Use pinned data on the LLM nodes if you want to test without incurring additional token costs.

---

## Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| “Spreadsheet not found” | `sheetUrl` incorrect or credential lacks access | Re-check the URL & share the sheet with the OAuth client email |
| Script doc created but rows not updated | `row_number` missing in source tab | Add a `ROW()` column and make sure it’s included in the dataset |
| LLM node errors | Missing OpenAI key or prompt too long | Attach `openAiApi` credential and trim Outline/Brief columns if needed |
| Docs created in root | `folderId` empty | Paste the Drive folder ID into the Config node |

---

## Where to Get Credentials & APIs

1. **Google OAuth (Sheets + Docs)**
   - Google Cloud Console → create project → *OAuth consent screen* (External) → *Credentials* → *Create credential → OAuth client ID* (choose “Web application”).
   - Add `https://oauth2.n8n.cloud/callback` (or your self-hosted callback) as an authorized redirect URI.
   - Download the JSON, then in n8n create both `googleSheetsOAuth2Api` and `googleDocsOAuth2Api` credentials using the same client ID/secret.

2. **OpenAI API Key**
   - https://platform.openai.com/account/api-keys → Create new secret key.
   - In n8n, add an `OpenAI` credential referencing that key. Select it in the `Script Writer LLM` node.

3. **Optional: Custom LLM / Claude**
   - Swap the `Script Writer LLM` node for your preferred model (Anthropic, OpenRouter, etc.) as long as it’s compatible with `chainLlm`.

With those pieces in place you can hand the workflow to teammates—just point them to this document, the JSON file, and the shared spreadsheet template. Once imported, updating the Config node is all that’s needed to aim it at their own Sheets/Drive.***
