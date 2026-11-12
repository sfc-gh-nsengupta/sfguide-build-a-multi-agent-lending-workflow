# Build a Multi-Agent Lending Workflow with Cortex Agents and MCP

Companion files for the Snowflake guide. You build a credit analyst agent that
reads loan documents and writes a credit memo, then explore an underwriting
agent that applies lending policy, delegates to the credit analyst over MCP and
records a decision.

**Guide:** https://www.snowflake.com/en/developers/guides/build-a-multi-agent-lending-workflow-with-cortex-agents-and-mcp/

## Setup

You need a Snowflake account with the ACCOUNTADMIN role. On a self-service trial
account, add a credit card first to turn on AI features. Setup takes about two
minutes.

1. In a SQL file in Snowsight, run:

   ```sql
   CREATE API INTEGRATION IF NOT EXISTS LENDING_LAB_GIT_API
       API_PROVIDER = git_https_api
       API_ALLOWED_PREFIXES = ('https://github.com/sfc-gh-nsengupta/')
       ENABLED = TRUE;
   ```

2. In **Projects » Workspaces**, open the workspace menu and select
   **From Git repository**. Paste this repository's URL, leave the name as it
   is, select **LENDING_LAB_GIT_API** and **Public repository**, then **Create**.
3. In the new workspace, open `setup.sql` and select **Run All**. The last
   result reads `Setup complete`.

To start the lab over from any point, run `setup.sql` again. To put edited
files back, discard your changes in the workspace's **Changes** tab.

The guide walks through each step.

## What is here

| Path | What it is |
|---|---|
| `setup.sql` | Creates everything the lab uses. Run it again to start over. |
| `lab.sql` | The SQL you run during the modules. |
| `cortex_project/` | The agent definitions, as YAML. |
| `utils/` | `helpful_queries.sql`, and `teardown.sql` to remove everything the lab created. |
| `data/` | The applicant documents and the evaluation settings that setup copies. |
