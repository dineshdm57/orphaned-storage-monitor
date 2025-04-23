# Orphaned Storage Monitor

An OpenOps no-code workflow that detects inactive cloud storage buckets (e.g. S3, Blob, GCS) and sends alerts to Slack.

## What it does

- Queries AWS Athena to find buckets with no activity (read/write) in the last 30 days
- Sends the list to your Slack channel
- Runs monthly with no manual steps

## How it works

1. **Scheduled trigger** (monthly)
2. **Athena query** to detect buckets with no recent access
3. **Slack message** with the result
4. **Ends workflow**

## Requirements

- AWS Athena connection in OpenOps
- Slack channel integration
- CloudTrail logs (for S3) or equivalent access logs

## Setup Steps

1. Import the JSON workflow into OpenOps
2. Connect:
   - Athena (AWS account with access)
   - Slack (to post alerts)
3. Update the Athena query with your table and bucket details
4. Optional: Change the schedule or Slack recipient
5. Save and enable

## Reusability

You can adapt this workflow to:
- Azure Blob (via Kusto query)
- GCP Storage (via BigQuery)
- Any storage with access logs and API

This workflow is editable and works with any SaaS/tool that exposes API access logs.

