# Workflow Bundle Overview

This repository already holds the full JSON exports for each automation. When the files were shared earlier only the document text reached your teammate, which typically means the workflow was copied from the editor preview instead of exporting the `.json` from **Settings → Export** (n8n strips binary attachments, tool references, and metadata when you paste that preview). Pointing everyone back to the original JSONs avoids that loss and keeps the node configuration intact.

## Workflow Index

- **Blog Automation Template**  
  - Path: `awesome-n8n-templates-main/Google_Drive_and_Google_Sheets/Author and Publish Blog Posts From Google Sheets.json`  
  - Purpose: Pull queued topics from Google Sheets, generate long-form copy with an OpenAI model, then publish or stage content.  
  - Highlights: `Settings` sheet selector, `Basic LLM Chain` (`@n8n/n8n-nodes-langchain.chainLlm`), and `SetToPublish` sheet updates so each row tracks publishing status.

- **RFP Automation With OpenAI Assistants**  
  - Path: `awesome-n8n-templates-main/OpenAI_and_LLMs/Automate Your RFP Process with OpenAI Assistants.json`  
  - Purpose: Accept RFP PDFs, extract questions, generate answers through an OpenAI Assistant, write them into a fresh Google Doc, and notify the team.  
  - Highlights: `extractFromFile` for PDF text, `Item List Output Parser` to structure questions, `googleDocs` creation step, and batched assistant calls for each prompt.

- **OpenAI Assistant + Google Drive Integration**  
  - Path: `awesome-n8n-templates-main/Google_Drive_and_Google_Sheets/Build an OpenAI Assistant with Google Drive Integration.json`  
  - Purpose: Maintain an OpenAI Assistant fed by reference docs in Google Drive and expose a chat interface with conversation memory.  
  - Highlights: `googleDrive` download, companion `openAi` file upload, assistant updates, and `chatTrigger` plus `memoryBufferWindow` for stateful chats.

## Working With The Bundle

1. **Keep the originals** – Do not move or rename the JSON files above; import them via `n8n import:workflow --input <path>` when you need to spin up an environment.  
2. **Share this overview** – Send this document so collaborators can jump straight to the right path and pull the full export instead of re-building nodes manually.  
3. **Optional combined export** – If you need a single file, create a new workflow in n8n, add three `Execute Workflow` nodes pointing to the templates, and export that master flow (_this keeps each source JSON untouched_).  
4. **Versioning tip** – Any edits made inside n8n should be written back with `n8n export:workflow --id <id> --output <same path>`; that ensures the repository copy always matches your running instance.

With this overview in the repo, everyone has one place to locate and cross-reference the automations while the canonical JSON exports stay under their original directories.
