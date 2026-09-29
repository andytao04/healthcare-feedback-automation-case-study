# Design Decisions

## 1. Use Google Sheets as the operational interface

The clinic workflow already relied on spreadsheet-based processes.

Keeping Google Sheets as the main operational surface reduced the need to introduce a completely new back-office system.

## 2. Use Apps Script for workflow orchestration

Apps Script provided a practical way to connect:

- the feedback web form;
- spreadsheet data;
- business rules;
- messaging;
- scheduled triggers;
- logging.

For this use case, the value came from reducing process friction rather than introducing a large custom application stack.

## 3. Maintain raw and latest-record views

The system keeps raw submissions in one sheet while generating a latest-record view keyed by phone number.

This supports both auditability and operational simplicity.

## 4. Gate messaging by consent

Consent is checked before sending WhatsApp communication.

This is particularly important because phone numbers are personal data and the workflow operates in a healthcare context.

## 5. Design for execution limits

Apps Script has bounded execution time.

The broadcast design therefore stores progress and schedules the next batch with a time-based trigger.

## 6. Preserve operational visibility

The design does not hide everything behind automation.

Statuses, message IDs, logs, config values, and admin controls remain visible to support staff.

## 7. Include rollback and recovery

Deployment versioning and explicit reset tools were included so the system could be supported after handover.

## 8. Treat maintainability as part of delivery

The project included admin/support documentation and staff training, not only implementation.

This reduced dependence on the original developer and made future modification more practical.
