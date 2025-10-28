# ↪️ EOM/MOM - Acronis

## Overview
This workflow automates the reporting of Acronis usage metrics for each customer. It runs mid-month and end-of-month, collecting data from the Acronis API and updating a SharePoint-hosted Excel workbook.

## Workflow Steps
1. **Trigger**: Initiated by the parent EOM/MOM automation.
2. **Authentication**:
   - Retrieves an access token using client credentials.
3. **Data Retrieval**:
   - Fetches tenant and usage data from Acronis.
   - Extracts metrics such as:
     - Physical servers
     - Virtual machines
     - M365 seats
     - Total storage usage (converted to TiB)
4. **Aggregation**:
   - Summarizes usage per customer.
5. **Excel Update**:
   - Clears existing table data.
   - Appends new rows with usage metrics.
   - Updates the timestamp cell.

## Requirements
- n8n instance with HTTP Request, Code, and Excel nodes.
- Valid Acronis API credentials (client ID and secret).
- Microsoft Graph API access with OAuth2 credentials.
- SharePoint site with a configured Excel workbook.
