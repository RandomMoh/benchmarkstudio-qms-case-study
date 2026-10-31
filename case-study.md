# Benchmarkstudio QMS: the workflow behind the dashboard

An operational system spanning order intake, AI-assisted Slack capture, query handling and production workflows. My ongoing work covers interfaces, backend workflows and integrations across the system.

## Context

Ongoing sister-company project.

Full-stack development and workflow automation.

## AI-assisted intake, with application rules around it.

The Slack integration turns identifiable work messages into records that staff can track. AI handles classification and structured extraction; the application handles routing, duplicates and database updates.

### Receive the event

Acknowledge Slack before the heavier processing work. Read the message and its workspace/channel context.

### Identify actionable work

Use AI to distinguish work from general conversation and classify new orders, amendments, completions or issues.

### Extract useful fields

Read the order reference or property identifier, work category and relevant notes from the structured response.

### Apply application rules

Use configured project/department context, handle multiple order references and check for existing active records.

### Update the work queue

Create or update the appropriate record. Link it back to the originating conversation.

### Follow the conversation

Use thread replies, order references and existing records to handle first replies, completions and issues.

### AI has a defined job

The integration requests structured output and attempts alternate model requests when a response cannot be used. Parsed fields feed the application rules that decide how to route and update records.

### People can still work directly

CSRs can add records manually, edit fields, extend deadlines and resolve issues through the interface. The automation sits alongside those workflows.

## Order taking is part of a wider operational workflow.

QMS covers more than one interface. The earlier PHP system includes production-role workflows; the newer React operations interface focuses on queries, staff activity and visibility. The case study separates these parts of the project history.

### Deadlines and response times

The interface includes configurable target deadlines, elapsed-time feedback, first-reply timestamps and completion information. These make the current state visible to staff.

### History and reporting

Field changes and status transitions have history views. Reports connect query records with staff activity and completion information; the source includes report exports.

### Earlier PHP production workflow

- Order entry and property details
- Assignment and reassignment
- Drawing and checking stages
- Amendments and repeat amendments
- Final uploads and role reports

### React operations interface

- Manual query and order capture
- Pending, issue and completed views
- Project and department filters
- CSR shifts and activity summaries
- History, Slack threads and reports

## Engineering across integration boundaries.

The work connects external conversations, AI responses, application rules, persistent records and staff interfaces. PHP and MySQL provide the operational foundation; React adds a richer interface for daily use.

### Duplicate and retry handling

The webhook acknowledges Slack retry events and checks for existing active records before adding work. These paths address repeated event delivery and duplicate intake.

### Conversation context

Thread references connect replies with existing work. Rule-based completion and issue handling complement the AI-assisted classification used during intake.

### Multiple ways to work

Automation, manual entry and editable records coexist. The production-role workflows and newer operations dashboard serve different parts of the work.

### What this demonstrates

Business workflow development, AI API integration, structured-data handling, operational dashboards and improvements to an existing PHP/MySQL system.

This case study describes my contribution and verified implementation areas. It excludes production source, prompts, credentials, customer records and unverified performance figures.
