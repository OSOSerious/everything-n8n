# n8n Templates Repository - Complete Topology

**Total Directories:** 208
**Total JSON Workflow Files:** 4,427
**Last Updated:** 2025-10-21

---

## Table of Contents

1. [Core SEO Template Directories](#core-seo-template-directories)
2. [Supporting Directories](#supporting-directories)
3. [Community/Backup Directories](#communitybackup-directories)
4. [Configuration Files](#configuration-files)
5. [Detailed Directory Breakdown](#detailed-directory-breakdown)

---

## Core SEO Template Directories

These are the **production-ready SEO automation workflows** that are actively maintained:

### AI Overview & Content Analysis
- **[ai-overview-analyzer/](ai-overview-analyzer/)** - Analyzes Google's AI Overviews to create content blueprints
  - `ai-overview-analyzer.json` - Main workflow
  - `tool-analyze-ai-overview.json` - SerpApi tool integration
  - `readme.md` - Setup documentation
  - Screenshots: `n8n-google-ai-overview-analyzer.png`, `n8n-google-ai-overview-analyzer-serpapi-tool.png`

- **[ai-overview-optimizer/](ai-overview-optimizer/)** - Compares existing content against AI Overviews
  - Main workflow + tool files
  - Optimization recommendation engine
  - `readme.md` - Usage instructions

### SEO Data & Analytics
- **[seo-data-analyst/](seo-data-analyst/)** - Natural language interface for querying BigQuery SEO data
  - `seo_data_analyst.json` - Main agent workflow
  - `tool_serper_crawl_urls.json` - Serper crawling tool
  - `tool_website_agent.json` - Website crawling sub-agent
  - `readme.md` - Complete setup guide
  - Screenshots: `n8n-ai-seo-data-analyst.png`, `n8n-seo-data-analyst-tool-serper.png`, `n8n-seo-data-analyst-tool-website-agent.png`

- **[serp-analysis/](serp-analysis/)** - Automated SERP analysis with multiple backend options
  - Supports: SerpApi, Serper, Crawl4AI, Firecrawl
  - `readme.md` - Backend configuration guide

- **[keyword-rank-tracker/](keyword-rank-tracker/)** - Unlimited keyword tracking
  - Google Sheets version
  - PostgreSQL version
  - `readme.md` - Implementation instructions

- **[traffic-performance-analysis/](traffic-performance-analysis/)** - Website performance analysis
  - Traffic metrics workflows
  - Performance monitoring tools
  - `readme.md`

- **[get-google-search-console-data/](get-google-search-console-data/)** - GSC data retrieval utilities
  - Direct GSC API access workflows
  - Alternative to BigQuery bulk export
  - `readme.md`

### Content Creation & Optimization
- **[gsc-ai-seo-writer/](gsc-ai-seo-writer/)** - Automated content optimization using GSC data
  - BigQuery integration
  - AI-powered content suggestions
  - `readme.md`

- **[ai-powered-seo-team/](ai-powered-seo-team/)** - Multi-agent SEO workflow system
  - Multiple specialized agents
  - Coordinated SEO task execution
  - `readme.md`

- **[website-seo-audit/](website-seo-audit/)** - Comprehensive SEO auditing workflows
  - Technical SEO checks
  - On-page optimization analysis
  - `readme.md`

### Reporting & Tools
- **[Redis/report-generator/](Redis/report-generator/)** - Converts JSON data to styled HTML reports
  - `tools_report_generator.json` - Main report generation tool
  - `report_generator_usage_example.json` - Example implementation
  - `report-examples/` - Sample report outputs
  - `readme.md` - Usage documentation
  - Screenshots: `n8n-report-generation-tool.png`, `n8n-report-generation-tool-usage.png`, `n8n-report-generation-report-example.png`

- **[tracked-keyword-performance-report-generator/](tracked-keyword-performance-report-generator/)** - Keyword performance reporting
  - Works with keyword-rank-tracker data
  - `readme.md`

- **[mailing-list-analysis/](mailing-list-analysis/)** - Email list analysis tools
  - `mailing_list_analysis.json` - Main workflow
  - `readme.md` - Setup guide
  - Screenshots: `n8n-automated-mailing-list-analysis.png`, `n8n-mailing-list-analyis-workflow.png`, `n8n-mailing-list-analysis-output.png`

- **[google-index-checker/](google-index-checker/)** - Google indexing status checker
  - Bulk URL indexing verification
  - `readme.md`

---

## Supporting Directories

### Templates & Examples
- **[templates/](templates/)** - Generic workflow templates
  - `communication/` - Communication workflow templates
  - `data-processing/` - Data processing templates
  - `README.md`

### API & Development
- **[api/](api/)** - API integration utilities and configurations

### External Resources
- **[awesome-n8n-templates-main/](awesome-n8n-templates-main/)** - Curated community templates collection
  - `AI_Research_RAG_and_Data_Analysis/` - AI & research workflows
  - `Airtable/` - Airtable integrations
  - `Database_and_Storage/` - Database workflows
  - `Discord/` - Discord bot workflows
  - `Forms_and_Surveys/` - Form automation
  - `Gmail_and_Email_Automation/` - Email workflows
  - `Google_Drive_and_Google_Sheets/` - Google workspace automation
  - `HR_and_Recruitment/` - HR automation
  - `Instagram_Twitter_Social_Media/` - Social media automation
  - `Notion/` - Notion integrations
  - `OpenAI_and_LLMs/` - LLM integrations
  - `Other/` - Miscellaneous templates
  - `Other_Integrations_and_Use_Cases/` - Additional use cases
  - `PDF_and_Document_Processing/` - Document automation
  - `Slack/` - Slack integrations
  - `Telegram/` - Telegram bots
  - `WhatsApp/` - WhatsApp automation
  - `WordPress/` - WordPress integrations
  - `img/` - Images and screenshots

---

## Community/Backup Directories

### Staging & Backups
- **[workflows/](workflows/)** - Staging directory for workflows in development
- **[workflows_backup/](workflows_backup/)** - Complete backup of all workflow directories (mirrors main structure)

### Documentation
- **[Documentation/](Documentation/)** - Auto-generated API documentation for community templates
  - Contains subdirectories mirroring all integration categories
  - 100+ service-specific documentation folders

---

## Integration-Specific Directories

The repository contains **150+ integration-specific directories**, each containing workflow JSON files organized by service:

### A-D Services
- **Activecampaign/** - ActiveCampaign CRM workflows
- **Acuityscheduling/** - Acuity Scheduling integrations
- **Affinity/** - Affinity CRM workflows
- **Aggregate/** - Data aggregation workflows
- **Airtable/** - Airtable database workflows
- **Airtabletool/** - Airtable tool integrations
- **Airtoptool/** - Airtop tool workflows
- **Amqp/** - AMQP message queue workflows
- **Apitemplateio/** - API Template.io integrations
- **Asana/** - Asana project management workflows
- **Automate/** - Generic automation workflows
- **Automation/** - Automation utility workflows
- **Autopilot/** - Autopilot marketing automation
- **Awsrekognition/** - AWS Rekognition image analysis
- **Awss3/** - AWS S3 storage workflows
- **Awssns/** - AWS SNS notification workflows
- **Awstextract/** - AWS Textract document extraction
- **Bannerbear/** - Bannerbear image generation
- **Baserow/** - Baserow database workflows
- **Beeminder/** - Beeminder goal tracking
- **Bitbucket/** - Bitbucket repository workflows
- **Bitly/** - Bitly URL shortener integrations
- **Bitwarden/** - Bitwarden password management
- **Box/** - Box cloud storage workflows
- **Calcslive/** - Calcslive spreadsheet integrations
- **Calendly/** - Calendly scheduling workflows
- **Chargebee/** - Chargebee subscription management
- **Clickup/** - ClickUp project management
- **Clockify/** - Clockify time tracking
- **Code/** - Custom code execution workflows
- **Coingecko/** - CoinGecko crypto data
- **Comparedatasets/** - Dataset comparison utilities
- **Compression/** - File compression workflows
- **Convertkit/** - ConvertKit email marketing
- **Converttofile/** - File conversion utilities
- **Copper/** - Copper CRM workflows
- **Cortex/** - Cortex security workflows
- **Create/** - Generic creation workflows
- **Cron/** - Scheduled/cron job workflows
- **Crypto/** - Cryptocurrency workflows
- **Customerio/** - Customer.io marketing automation
- **Datetime/** - Date/time manipulation workflows
- **Debughelper/** - Debugging utility workflows
- **Deep/** - Deep learning workflows
- **Discord/** - Discord bot workflows
- **Discordtool/** - Discord tool integrations

### E-H Services
- **Dropbox/** - Dropbox storage workflows
- **Editimage/** - Image editing workflows
- **Elasticsearch/** - Elasticsearch search workflows
- **Emailreadimap/** - IMAP email reading
- **Emailsend/** - Email sending workflows
- **Emelia/** - Emelia email automation
- **Error/** - Error handling workflows
- **Eventbrite/** - Eventbrite event management
- **Executecommand/** - Command execution workflows
- **Executeworkflow/** - Workflow execution utilities
- **Executiondata/** - Execution data workflows
- **Export/** - Data export workflows
- **Extractfromfile/** - File data extraction
- **Facebook/** - Facebook integrations
- **Facebookleadads/** - Facebook Lead Ads
- **Figma/** - Figma design workflows
- **Filter/** - Data filtering workflows
- **Flow/** - Flow control workflows
- **Form/** - Form processing workflows
- **Functionitem/** - Function item utilities
- **Getresponse/** - GetResponse email marketing
- **Github/** - GitHub repository workflows
- **Gitlab/** - GitLab repository workflows
- **Gmail/** - Gmail email workflows
- **Gmailtool/** - Gmail tool integrations
- **Googleanalytics/** - Google Analytics workflows
- **Googlebigquery/** - Google BigQuery data workflows
- **Googlecalendar/** - Google Calendar integrations
- **Googlecalendartool/** - Google Calendar tools
- **Googlecontacts/** - Google Contacts management
- **Googledocs/** - Google Docs automation
- **Googledrive/** - Google Drive storage workflows
- **Googledrivetool/** - Google Drive tool integrations
- **Googlesheets/** - Google Sheets workflows
- **Googlesheetstool/** - Google Sheets tool integrations
- **Googleslides/** - Google Slides automation
- **Googletasks/** - Google Tasks workflows
- **Googletaskstool/** - Google Tasks tools
- **Googletranslate/** - Google Translate integrations
- **Gotowebinar/** - GoToWebinar workflows
- **Graphql/** - GraphQL API workflows
- **Grist/** - Grist spreadsheet workflows
- **Gumroad/** - Gumroad product workflows
- **Helpscout/** - Help Scout support workflows
- **Http/** - HTTP request workflows
- **Hubspot/** - HubSpot CRM workflows
- **Humanticai/** - Humantic AI personality insights
- **Hunter/** - Hunter.io email finder

### I-O Services
- **Intercom/** - Intercom customer messaging
- **Interval/** - Interval scheduling workflows
- **Invoiceninja/** - Invoice Ninja invoicing
- **Jira/** - Jira project management
- **Jiratool/** - Jira tool integrations
- **Jotform/** - JotForm form workflows
- **Keap/** - Keap CRM workflows
- **Lemlist/** - Lemlist email outreach
- **Limit/** - Rate limiting workflows
- **Linkedin/** - LinkedIn integrations
- **Localfile/** - Local file operations
- **Mailcheck/** - Email validation workflows
- **Mailchimp/** - Mailchimp email marketing
- **Mailerlite/** - MailerLite email marketing
- **Mailjet/** - Mailjet email service
- **Manual/** - Manual trigger workflows
- **Markdown/** - Markdown processing
- **Matrix/** - Matrix messaging workflows
- **Mattermost/** - Mattermost team chat
- **Mautic/** - Mautic marketing automation
- **Microsoftexcel/** - Microsoft Excel workflows
- **Microsoftonedrive/** - OneDrive storage workflows
- **Microsoftoutlook/** - Outlook email workflows
- **Microsofttodo/** - Microsoft To Do workflows
- **Mondaycom/** - Monday.com project management
- **Mongodbtool/** - MongoDB database tools
- **Mqtt/** - MQTT messaging workflows
- **Mysqltool/** - MySQL database tools
- **N8ntrainingcustomermessenger/** - n8n training workflows
- **Netlify/** - Netlify deployment workflows
- **Nocodb/** - NocoDB database workflows
- **Noop/** - No-operation placeholder workflows
- **Notion/** - Notion workspace workflows
- **Odoo/** - Odoo ERP workflows
- **Onfleet/** - Onfleet delivery management
- **Openai/** - OpenAI API workflows
- **Openweathermap/** - OpenWeatherMap API

### P-Z Services
- **Paypal/** - PayPal payment workflows
- **Pipedrive/** - Pipedrive CRM workflows
- **Postgres/** - PostgreSQL database workflows
- **Postgrestool/** - PostgreSQL tool integrations
- **Posthog/** - PostHog analytics workflows
- **Postmark/** - Postmark email service
- **Process/** - Data processing workflows
- **Quickbooks/** - QuickBooks accounting
- **Raindrop/** - Raindrop bookmark manager
- **Readbinaryfile/** - Binary file reading (singular)
- **Readbinaryfiles/** - Binary file reading (plural)
- **Redis/** - Redis cache/database workflows (also contains report-generator)
- **Removeduplicates/** - Duplicate removal workflows
- **Respondtowebhook/** - Webhook response workflows
- **Rssfeedread/** - RSS feed reader workflows
- **Schedule/** - Scheduling workflows
- **Send/** - Generic send workflows
- **Shopify/** - Shopify e-commerce workflows
- **Signl4/** - SIGNL4 alerting workflows
- **Slack/** - Slack messaging workflows
- **Splitinbatches/** - Batch splitting workflows
- **Splitout/** - Data splitting workflows
- **Sse/** - Server-Sent Events workflows
- **Stickynote/** - Sticky note/annotation workflows
- **Stopanderror/** - Error stopping workflows
- **Strapi/** - Strapi CMS workflows
- **Summarize/** - Text summarization workflows
- **Supabase/** - Supabase backend workflows
- **Surveymonkey/** - SurveyMonkey workflows
- **Taiga/** - Taiga project management
- **Telegram/** - Telegram bot workflows
- **Telegramtool/** - Telegram tool integrations
- **Thehive/** - TheHive security workflows
- **Todoist/** - Todoist task management
- **Toggl/** - Toggl time tracking
- **Travisci/** - Travis CI workflows
- **Trello/** - Trello board workflows
- **Twilio/** - Twilio SMS/voice workflows
- **Twitter/** - Twitter/X API workflows
- **Twittertool/** - Twitter tool integrations
- **Typeform/** - Typeform form workflows
- **Uptimerobot/** - UptimeRobot monitoring
- **Wait/** - Wait/delay workflows
- **Webflow/** - Webflow CMS workflows
- **Webhook/** - Generic webhook workflows (largest collection)
- **Whatsapp/** - WhatsApp messaging workflows
- **Wise/** - Wise payment workflows
- **Woocommerce/** - WooCommerce e-commerce
- **Woocommercetool/** - WooCommerce tools
- **Wordpress/** - WordPress CMS workflows
- **Writebinaryfile/** - Binary file writing
- **Wufoo/** - Wufoo form workflows
- **Xml/** - XML processing workflows
- **Youtube/** - YouTube API workflows
- **Zendesk/** - Zendesk support workflows
- **Zohocrm/** - Zoho CRM workflows

---

## Configuration Files

### Project Configuration
- **[.claude/](.claude/)** - Claude Code configuration directory
- **[CLAUDE.md](CLAUDE.md)** - Project-specific instructions for Claude Code
- **[AGENTS.md](AGENTS.md)** - Agent system documentation and guidelines
- **[README.md](README.md)** - Repository overview (if exists)
- **.DS_Store** - macOS folder metadata (ignore)

---

## File Naming Conventions

### Workflow Files
- Pattern: `NNNN_Service_Action_Type_Trigger.json`
- Example: `0420_Hunter_Form_Create_Triggered.json`
  - `0420` = Template ID
  - `Hunter` = Primary service
  - `Form` = Secondary service/node
  - `Create` = Action type
  - `Triggered` = Trigger mechanism

### Tool Files
- Pattern: `tool-descriptive-name.json`
- Example: `tool-analyze-ai-overview.json`

### Documentation Files
- `readme.md` or `README.md` - Setup and usage instructions
- Screenshots: `n8n-[workflow-name]-[description].png`

---

## Repository Statistics

### By Category
- **SEO Templates (Active):** 13 directories
- **Integration Directories:** ~150 directories
- **Community Templates (awesome-n8n-templates-main):** 16 categories
- **Documentation Mirrors:** ~150 directories
- **Backup Directories:** 2 (workflows, workflows_backup)

### File Counts
- **Total JSON Workflows:** 4,427 files
- **Readme/Documentation Files:** 15+ (in active SEO directories)
- **Screenshot/Image Files:** 30+ (across all SEO templates)

### Size Distribution
- **Largest Category:** Webhook/ (100+ workflow files)
- **Most Complete Templates:** SEO-related directories (with readme, screenshots, multiple workflows)
- **Most Complex:** ai-powered-seo-team/, seo-data-analyst/ (multi-agent systems)

---

## Directory Usage Priority

### High Priority (Active Development)
1. All SEO template directories (ai-*, seo-*, gsc-*, keyword-*, serp-*, etc.)
2. Redis/report-generator/
3. templates/

### Medium Priority (Reference/Community)
1. awesome-n8n-templates-main/
2. Integration-specific directories (as needed)

### Low Priority (Backup/Archive)
1. Documentation/ (auto-generated mirrors)
2. workflows_backup/ (backups only)
3. workflows/ (staging)

---

## Navigation Tips

### Finding Workflows
1. **By Service:** Look in service-named directories (e.g., Slack/, Gmail/)
2. **By Use Case:** Check awesome-n8n-templates-main/ categories
3. **By SEO Function:** Use dedicated SEO template directories
4. **By Pattern:** Use glob patterns: `**/*keyword*.json`

### Understanding Workflow Relationships
1. Main workflows often reference tool workflows via `Execute Workflow` nodes
2. Agent systems have multiple sub-agents as separate JSON files
3. Tools are prefixed with `tool-` or `tools_`
4. Usage examples are suffixed with `_usage_example`

### Quick Access Paths
```
SEO Templates:        ./[template-name]/
Community Templates:  ./awesome-n8n-templates-main/[category]/
Service Workflows:    ./[ServiceName]/
Documentation:        ./[ServiceName]/readme.md or ./Documentation/[ServiceName]/
Report Generator:     ./Redis/report-generator/
```

---

## Cross-Reference Map

### Templates That Work Together
- **ai-overview-analyzer** ↔ **gsc-ai-seo-writer** (AI Overview data → content optimization)
- **keyword-rank-tracker** ↔ **tracked-keyword-performance-report-generator** (tracking → reporting)
- **seo-data-analyst** ↔ **serp-analysis** (data query → SERP analysis)
- **Any workflow** ↔ **Redis/report-generator/** (JSON output → HTML reports)

### Common Dependencies
- **BigQuery:** seo-data-analyst, gsc-ai-seo-writer, keyword-rank-tracker
- **SerpApi/Serper:** ai-overview-analyzer, serp-analysis, seo-data-analyst
- **Crawl4AI/Firecrawl:** serp-analysis, website-seo-audit
- **OpenAI:** All AI-powered templates
- **Google Sheets:** keyword-rank-tracker, various data storage workflows
- **PostgreSQL:** keyword-rank-tracker (alternative to Sheets)

---

## Version Control Notes

This repository appears to be:
- **NOT a git repository** (based on env info)
- Likely a **Downloads folder collection** of exported n8n workflows
- Contains multiple backup/staging directories suggesting manual version control
- Best practice: Initialize git and create proper version control structure

---

## Recommended Next Steps

1. **Initialize Git Repository**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: n8n template collection"
   ```

2. **Clean Up Structure**
   - Move backup directories to separate branch
   - Consolidate Documentation/ if it's auto-generated
   - Create proper .gitignore for .DS_Store and temp files

3. **Organize by Priority**
   - Consider moving community/backup templates to separate repo
   - Keep main repo focused on active SEO templates
   - Archive legacy workflows

4. **Add Master README**
   - Create comprehensive README.md at root
   - Link to all template directories
   - Include quick start guide

---

## File Structure Visualization

```
n8n-templates-/
├── Core SEO Templates (13 dirs)
│   ├── ai-overview-analyzer/
│   ├── ai-overview-optimizer/
│   ├── ai-powered-seo-team/
│   ├── get-google-search-console-data/
│   ├── google-index-checker/
│   ├── gsc-ai-seo-writer/
│   ├── keyword-rank-tracker/
│   ├── mailing-list-analysis/
│   ├── seo-data-analyst/
│   ├── serp-analysis/
│   ├── tracked-keyword-performance-report-generator/
│   ├── traffic-performance-analysis/
│   └── website-seo-audit/
│
├── Supporting Tools
│   ├── Redis/report-generator/
│   ├── templates/
│   └── api/
│
├── Community Resources
│   └── awesome-n8n-templates-main/ (16 categories)
│
├── Integration Directories (~150 dirs)
│   ├── [A-D Services] (40+ dirs)
│   ├── [E-H Services] (40+ dirs)
│   ├── [I-O Services] (40+ dirs)
│   └── [P-Z Services] (40+ dirs)
│
├── Backups & Documentation
│   ├── Documentation/ (mirrors all integration dirs)
│   ├── workflows/
│   └── workflows_backup/ (complete backup)
│
└── Configuration
    ├── .claude/
    ├── AGENTS.md
    ├── CLAUDE.md
    └── REPOSITORY_TOPOLOGY.md (this file)
```

---

## Summary

This repository is a **comprehensive collection of 4,427+ n8n workflow templates** with a focus on:
- **SEO automation and AI-powered content optimization** (13 specialized template sets)
- **150+ service integrations** (from ActiveCampaign to Zoho)
- **Community-curated examples** (16 categories in awesome-n8n-templates-main)
- **Multi-agent systems** using n8n's LangChain integration

The structure suggests this is a working collection/download folder that would benefit from proper version control and organization into separate repositories by category (SEO templates, community templates, backups).
