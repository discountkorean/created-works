
# EOM/MOM - SentinelOne

## Overview
This workflow automates the monthly and mid-month reporting for SentinelOne agents. It retrieves agent data via API, processes it to count device types per site, and appends the results to a SharePoint-hosted Excel workbook.

## Usage Instructions
1. Triggered automatically at mid-month and end-of-month.
2. Retrieves agent data from SentinelOne API.
3. Splits and merges paginated data.
4. Aggregates device counts by site.
5. Appends results to the designated Excel table.
6. Updates the timestamp in the worksheet.

## Requirements
- Valid SentinelOne API credentials.
- Access to Microsoft Graph API with appropriate permissions.
- n8n environment with HTTP Request, Code, and Excel nodes.
