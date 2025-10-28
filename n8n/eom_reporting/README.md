
# ❇️ EOM/MOM Reporting Automation

This repository contains a sanitised version of an **End-of-Month / Middle-of-Month Reporting Automation Workflow** built using [n8n](https://n8n.io/). It automates the generation, aggregation, and archival of monthly reports across various services.

## 🔧 Overview

The workflow includes:

- **Scheduled triggers** for mid-month and end-of-month execution.
- **Dynamic date logic** to determine the closest weekday to the middle or end of the month.
- **Workbook session management** using Microsoft Graph API.
- **Sub-workflow execution** for services like:
  - SentinelOne
  - Datto SaaS
  - Datto BCDR
  - N-central
  - Acronis
- **Aggregation and merging** of results.
- **Archival** of the final report to a designated SharePoint folder, making the Excel Workbook dynamically update.

## 📌 Requirements

- n8n (v1.2 or later recommended)
- Microsoft Graph API access
- SharePoint integration
- OAuth2 credentials configured in n8n

## 📄 License

This project is released under the MIT License. See `LICENSE` for details.
