
# 🖥️ Offline Workstations Report Automation

This repository contains two n8n workflow configurations designed to automate the generation and distribution of offline workstation reports for managed service customers. These workflows help identify devices that have not checked in within a specified time frame and compile customer-specific reports.

## 📦 Workflows Included

### 1. Fortnightly Offline Workstations Report
- **Frequency**: Every second Friday
- **Target Devices**: Workstations that haven't checked in for **28–60 days**
- **Purpose**: To monitor and report on device inactivity for selected customers on a biweekly basis.

### 2. Monthly Offline Workstations Report
- **Frequency**: Last weekday of each month
- **Target Devices**: Workstations that haven't checked in for **60+ days**
- **Purpose**: To provide a broader monthly overview of offline devices across a different customer set.

## 🔧 Workflow Features

- **Customer Filtering**: Each workflow filters customers based on predefined lists.
- **Device Filtering**: Uses N-central API filters to identify offline devices.
- **Data Cleanup**: Removes entries with zero offline devices to reduce noise.
- **Grouping**: Devices are grouped by customer for report generation.
- **File Generation**: Reports are exported as `.xlsx` files with meaningful filenames.
- **Compression**: Multiple reports are zipped for efficient delivery.
- **Email Dispatch**: Final reports are sent to the NOC team via Outlook integration.

## 📁 Output Format

Each report includes:
- Device name
- Site name
- Network address
- Last check-in time
- Last logged-in user

## 📤 Delivery

Reports are automatically emailed to the NOC team with a summary message and attached ZIP file containing individual customer reports.

## 🛠️ Technologies Used

- [n8n](https://n8n.io/) – Workflow automation
- N-central API – Device and customer data
- Microsoft Outlook – Email integration
- JavaScript – Custom logic within n8n function nodes

## 🧠 Notes

- If a customer has no offline devices in the specified range, no report is generated for them.
- Manual intervention may be required if data is missing or corrupted.
- The workflows are timezone-aware and operate in **Australia/Sydney** time.
