# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a collection of n8n workflow templates focused on SEO automation and AI-powered content analysis. The repository contains production-ready workflows (JSON files) for analyzing Google's AI Overviews, optimizing content, tracking keywords, and generating reports.

## Architecture

### Core Template Categories

**AI Overview Analysis & Optimization**
- `ai-overview-analyzer/` - Analyzes Google's AI Overviews to create content blueprints
- `ai-overview-optimizer/` - Compares existing content against AI Overviews and provides optimization recommendations

**SEO Data & Analytics**
- `seo-data-analyst/` - Natural language interface for querying BigQuery SEO data, includes sub-agent for website crawling
- `serp-analysis/` - Automates SERP analysis with multiple crawling backend options (SerpApi/Serper/Crawl4AI/Firecrawl)
- `keyword-rank-tracker/` - Unlimited keyword tracking with Google Sheets and PostgreSQL versions
- `traffic-performance-analysis/` - Website performance analysis workflows
- `get-google-search-console-data/` - GSC data retrieval utilities

**Content Creation & Optimization**
- `gsc-ai-seo-writer/` - Automates content optimization using GSC data from BigQuery
- `ai-powered-seo-team/` - Multi-agent SEO workflow system
- `website-seo-audit/` - Comprehensive SEO auditing workflows

**Supporting Tools**
- `report-generator/` - Converts JSON data to styled HTML reports
- `mailing-list-analysis/` - Email list analysis tools
- `google-index-checker/` - Google indexing status checker

### Workflow Structure Pattern

Each template directory typically contains:
- Main workflow JSON file(s) with descriptive names (e.g., `ai-overview-analyzer.json`)
- Tool/sub-workflow JSON files prefixed with `tool-` (e.g., `tool-analyze-ai-overview.json`)
- `readme.md` with prerequisites, setup instructions, and usage examples
- Screenshots/diagrams (PNG files)

### Multi-Service Integration Architecture

Workflows use a modular approach with interchangeable services:
- **SERP APIs**: SerpApi (structured JSON) or Serper (cost-effective alternative)
- **Content Crawling**: Crawl4AI (self-hosted, cost-effective), Firecrawl (paid SaaS), or Serper `/scraper` endpoint
- **LLMs**: OpenAI GPT-4.1 / GPT-4.1-Mini (configurable via n8n nodes)
- **Data Storage**: BigQuery (bulk GSC data), PostgreSQL, or Google Sheets
- **AI Framework**: n8n's LangChain integration with chat triggers, memory buffers, and tool calling

### Agent System Pattern

Multi-agent workflows follow this structure:
1. Main agent (chat-triggered) coordinates tasks
2. Sub-agents implemented as separate n8n workflows called via "Execute Workflow" nodes
3. Tools defined as workflows that agents invoke (e.g., website scraping, API calls)
4. Shared memory context using n8n's memory nodes

## Working with Workflows

### Importing/Editing Workflows
- Workflows are stored as JSON files containing n8n node configurations
- Import via n8n UI: Workflows → Import from File
- JSON structure includes: name, nodes array (with parameters, type, position, connections)
- Credentials are referenced by name, not embedded in JSON

### Common Node Types
- `@n8n/n8n-nodes-langchain.chatTrigger` - AI agent chat interface
- `@n8n/n8n-nodes-langchain.agent` - LangChain agent orchestration
- `@n8n/n8n-nodes-langchain.lmChatOpenAi` - OpenAI LLM integration
- `@n8n/n8n-nodes-langchain.memoryBufferWindow` - Conversation memory
- BigQuery, Google Sheets, PostgreSQL - Data storage nodes
- HTTP Request - API integrations (SerpApi, Serper, etc.)

### Required Credentials Setup
Most workflows require:
- OpenAI API key (for GPT models)
- SerpApi and/or Serper API key (for search data)
- Google Cloud credentials (for BigQuery, Sheets, Drive)
- PostgreSQL credentials (for database-backed workflows)

### BigQuery Bulk Export Dependency
Several workflows (`gsc-ai-seo-writer`, `keyword-rank-tracker`, `seo-data-analyst`) require:
- Google Search Console Bulk Data Export enabled
- BigQuery properly configured in Google Cloud Console
- Alternative: Use `get-google-search-console-data` workflow for direct GSC API access

## Development Workflow

### Testing Workflows
1. Pin data in nodes to avoid consuming API credits during development
2. Use limits when fetching SERP data or crawling content
3. Test with small date ranges for BigQuery queries
4. Check sticky notes within workflow files for setup instructions

### Extending Workflows
- To swap crawling backends: Replace HTTP Request or Execute Workflow nodes with equivalent service
- To change LLMs: Update model parameter in LangChain nodes (supports any OpenAI-compatible API)
- To modify data storage: Replace Google Sheets nodes with PostgreSQL or vice versa

### Creating New Templates
Follow the established pattern:
1. Main workflow + separate tool workflows
2. Include readme.md with prerequisites, features, setup, and usage
3. Add screenshots showing workflow structure
4. Document all required API keys and credentials
5. Provide example outputs when applicable

## Cross-Template Integration

Templates are designed to be composable:
- `ai-overview-analyzer` can be integrated into `gsc-ai-seo-writer` for real-time AI Overview data
- `ai-overview-optimizer` works standalone or as part of content optimization pipelines
- `report-generator` can be used by any workflow generating JSON output
- `seo-data-analyst` tools can be reused in other agent workflows

## Legacy/Backup Directories

- Numbered directories (e.g., `Activecampaign/`, `Aggregate/`) contain community/backup templates
- `Documentation/` contains auto-generated API docs and guides for community templates
- `workflows/` and `workflows_backup/` appear to be staging/backup directories
- Focus development on the named SEO template directories at root level
