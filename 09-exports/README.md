# ClinicPilot X Exports

This folder holds files meant to be handed to the owner, assistant testers, Lovable, or other outside tools.

## Assistant QA File Naming

Use this pattern for assistant testing documents:

`CLINICPILOT QA {number}_{Module or Flow Name}.md`

Examples:

- `CLINICPILOT QA 1_Leads Module Step 2A.md`
- `CLINICPILOT QA 2_Appointments and Calendar Step 2B.md`
- `CLINICPILOT QA 3_Patients Module Step 2C.md`

If a Word document is needed, use the same name with `.docx`.

## Current QA Sequence

- QA 1: Leads Module Step 2A
- QA 2: Reserved for the next functional testing package, expected to be Appointments and Calendar Step 2B unless the priority changes.

## Rules

- Keep one QA file focused on one module or closely related flow.
- Include exact test URLs, login notes, copy/paste test data, expected results, and a simple bug report format.
- Avoid asking the assistant to invent test data unless the test specifically requires it.
- Mention known issues clearly so the assistant does not report already-logged bugs as new failures.
