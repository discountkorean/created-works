
# 🛠️ Patchable Servers - Monthly Workflow

This repository contains an n8n workflow configuration designed to automate monthly patchability checks for servers. It integrates with N-central and Microsoft Graph API to retrieve server data, clean and format it, and append results to SharePoint Excel tables.

## 📅 Schedule
- **Trigger**: First weekday of each month
- **Time**: 7:00 AM (Australia/Sydney timezone)

## 🔍 Workflow Overview

### 1. Authentication & Setup
- Authenticates with N-central and Microsoft Graph API.
- Retrieves necessary filter IDs for legacy and non-legacy servers.
- Initializes a workbook session in SharePoint.

### 2. Data Retrieval
- Fetches server data using N-central filters:
  - **Legacy Servers**
  - **Non-Legacy Servers**

### 3. Data Cleanup & Transformation
- Filters and formats server data:
  - Extracts customer name, site name, and server name.
  - Adds a calculated field to determine if the server is listed in predefined SharePoint tables.

### 4. Excel Table Management
- Deletes old data ranges from legacy and non-legacy tables.
- Appends new rows with updated server data.
- Uses Excel formulas to determine listing status.

### 5. Finalization
- Aggregates all data.
- Closes the workbook session.

## 📁 Output Format
Each row added to the Excel table includes:
- Customer name
- Site name
- Server name
- Listing status (Listed/Unlisted via Excel formula)

## 🧰 Technologies Used
- [n8n](https://n8n.io/) – Workflow automation
- N-central API – Server data retrieval
- Microsoft Graph API – Excel table manipulation
- JavaScript – Custom logic in n8n function nodes

## 🧠 Notes
- The workflow is designed to be resilient with retry logic and batching.
- Manual updates may be required for new customers or table structure changes.
- Ensure credentials are correctly configured in n8n before activation.
