
# ↪️ EOM/MOM - N-central

This workflow is part of the EOM/MOM Reporting Automation suite, specifically designed to collect and process device data from N-central for monthly reporting.

## Overview
The workflow retrieves device data from N-central using multiple filters, aggregates counts by customer, and appends the results to a SharePoint-hosted Excel workbook. It includes logic to distinguish between legacy and non-legacy servers, workstations/laptops, and network devices.

## Usage Instructions
1. **Authentication Setup**: Ensure valid N-central API credentials are configured in n8n.
2. **Triggering**: This workflow is triggered by the parent EOM/MOM workflow via `Execute Workflow` node.
3. **Data Flow**:
   - Retrieves filters and customer IDs.
   - Executes device queries per filter.
   - Aggregates counts per customer.
   - Appends results to the designated Excel table.
   - Updates the timestamp cell to reflect last update.

## Requirements
- n8n instance with HTTP Request, Code, Merge, Aggregate, and Execute Workflow nodes.
- OAuth2 credentials for Microsoft Graph API.
- Valid N-central API credentials.
- SharePoint site with an Excel workbook containing the required tables and worksheets.

## Notes
- Ensure the workbook session is created before invoking this workflow.
- The workflow expects `id_firstItem` as input to identify the workbook session.
- Customer filtering logic is customisable via the `Retrieve Customer ID` nodes.

