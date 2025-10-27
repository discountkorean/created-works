# ↪️ EOM/MOM - Datto SaaS

## Overview
This workflow automates the reporting process for Datto SaaS (Backupify) user seat counts. It runs mid-month and end-of-month to collect data from the Datto SaaS API and update a SharePoint-hosted Excel workbook.

## Workflow Steps
1. **Trigger**: Initiated by the parent EOM/MOM automation.
2. **Data Retrieval**:
   - Fetches domain and seat data from Datto SaaS API.
   - Filters for billable user seats.
3. **Aggregation**:
   - Counts user seats per customer.
4. **Excel Update**:
   - Clears existing table data.
   - Appends new rows with seat counts.
   - Updates the timestamp cell.

## Requirements
- n8n instance with HTTP Request, Code, and Excel nodes.
- Valid Datto SaaS API credentials.
- Microsoft Graph API access with OAuth2 credentials.
- SharePoint site with a configured Excel workbook.
