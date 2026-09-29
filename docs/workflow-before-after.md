# Workflow: Before & After

## Before automation

The project started by analysing the existing workflow, including:

- how feedback was collected;
- how data was consolidated;
- how staff followed up with patients;
- where manual interventions occurred;
- how Google Sheets, WhatsApp, and staff activities interacted.

A simplified representation:

```text
Patient feedback
   ↓
Manual / semi-manual collection
   ↓
Google Sheets
   ↓
Manual consolidation
   ↓
Staff identifies recipients
   ↓
One-by-one WhatsApp follow-up
   ↓
Manual tracking
```

## Redesigned workflow

```text
Patient submits digital feedback
   ↓
Apps Script validates and stores response
   ↓
Average score calculated
   ↓
Latest record per phone updated
   ↓
Consent and send-status checks
   ↓
Personalized WhatsApp message
   ↓
Delivery SID/status saved
   ↓
Audit log updated
```

## Conditional flows

### Positive feedback

When the score meets the configured threshold and a branch review URL is available, the user can be shown a Google Review prompt.

### Low-score feedback

An optional apology workflow can send a configured follow-up message when the score is below the threshold and consent conditions are satisfied.

### Broadcast workflow

For larger message lists, the workflow runs in batches, saves progress, and uses Apps Script time triggers to resume subsequent batches.

This avoids relying on one long-running script execution.
