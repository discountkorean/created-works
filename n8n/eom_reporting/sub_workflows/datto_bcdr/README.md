
# ↪️ EOM/MOM - Datto BCDR

## Overview
This workflow automates the monthly and mid-month reporting for Datto BCDR devices. It retrieves device data from the Datto API, filters out hidden or irrelevant entries, and appends the cleaned data to a SharePoint-hosted Excel workbook. The workflow also updates the timestamp to reflect the latest report generation.

## Usage Instructions
1. **Trigger**: The workflow is triggered either mid-month or end-of-month based on a schedule.
2. **Session Creation**: A workbook session is created to allow batch updates.
3. **Data Retrieval**: Device data is fetched from the Datto BCDR API.
4. **Filtering**: Devices marked as hidden or missing organization/customer names are excluded.
5. **Aggregation**: Active device counts are calculated per customer.
6. **Excel Update**:
   - Existing table data is cleared.
   - New rows are appended with the latest device counts.
   - A timestamp is updated to indicate the last refresh.
7. **Session Closure**: The workbook session is closed to finalize changes.

## Requirements
- n8n automation platform
- Valid Datto API credentials
- Microsoft Graph API access with OAuth2 credentials
- SharePoint site and Excel workbook configured with appropriate tables and worksheets

## Notes
- Ensure the workbook table IDs and worksheet IDs match those referenced in the workflow.
- The workflow is designed to run in the Australia/Sydney timezone.
- Error handling is configured to route failures to a designated error workflow.
