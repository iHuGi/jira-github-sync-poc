# 🧪 Jira & GitHub Automation Sandbox

A proof-of-concept repository to validate and demonstrate automated bidirectional workflow synchronization between Atlassian Jira and GitHub.

## ⚙️ Workflow Overview

This sandbox replicates a standard enterprise workflow, ensuring full automation of the issue lifecycle across both platforms:

1. **Jira ➔ GitHub:** Moving a Jira ticket to `To Do` automatically triggers a webhook to create a corresponding Issue in this GitHub repository via the GitHub REST API.
2. **GitHub ➔ Jira:** Closing an Issue in GitHub triggers an incoming webhook that seamlessly updates the Jira ticket status to `Code Integrated` (handling edge cases like skipping state transitions and just commenting when closed as *not planned*).

## 🛠️ Automation Stack
- **Core Engine:** Native Jira Automation (Web requests & Incoming Webhooks)
- **Authentication:** GitHub Fine-grained PAT (Principle of Least Privilege: `Issues: Read & Write`, `Metadata: Read-only`)
- **Architecture:** Direct REST API communication (zero middleware/third-party servers, event-driven async processing)

*Note: This repository is strictly for infrastructure, tooling, and DevOps pipeline validation.*
