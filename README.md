# email-validator

Story 1: Email Replenishment Workflow
As a Data Engineer, I need to automate replenishment of commercial and personal emails from
vendors so that our master database remains current and compliant.
Tasks:
• Pull updated email lists from Lorann and YesData.
• Exchange data securely via SFTP.
• Deduplicate using internal master suppression list maintained by the Data Team.
• Apply domain suppression list for known bad or non-healthcare domains.
Acceptance Criteria:
Vendor files received and processed monthly. Deduplication and domain suppression applied
successfully.
Story 2: Monthly Email Validation
As a Data Engineer, I need to run monthly email validation via API, rotating between vendors, so that
invalid emails are flagged and removed.
Tasks:
• Integrate APIs for ZeroBounce, AtData, Verifalia, EmailListVerify.
• Schedule monthly validation jobs with vendor rotation.
• Update email statuses in the master database.
Acceptance Criteria:
Validation runs complete without errors. Status updates logged and auditable.
Story 3: Bounce Handling & Inactivation
As a Data Engineer, I need to inactivate bounced emails from internal and customer deployments to
maintain deliverability.
Tasks:
• Collect bounce reports from ESP and internal systems.
• Include sources: HCP Today, Clinical Briefing Report, and customer deployments.
• Flag and inactivate hard-bounced emails within 48 hours.
Acceptance Criteria:
Bounce handling workflow removes invalid emails promptly. Audit trail maintained for all changes.
Dependencies
- Vendor API credentials and access.
- Internal database update permissions.
- ESP bounce reporting integration.