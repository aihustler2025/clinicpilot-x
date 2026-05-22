# Old ClinicPilot X File Intake Summary

Generated from `D:\PROJECTS\CLINICPILOT X (Old)`. These files are reference material only, not final product truth.

## File Counts

- `.csv`: 1
- `.docx`: 28
- `.json`: 9
- `.pdf`: 6
- `.png`: 4
- `.xlsx`: 4

## Document Previews

### Dawood\Active\[VAPI] inbound calling scenario.json

- Size: 24719 bytes
- Detected themes: n8n, vapi, calendar, booking, inbound

```text
Workflow name: [VAPI] inbound calling scenario
Active flag: True
Node count: 9
- Create an event in Google Calendar1 | n8n-nodes-base.googleCalendarTool
- Webhook1 | n8n-nodes-base.webhook
- Respond to Webhook1 | n8n-nodes-base.respondToWebhook
- Simple Memory | @n8n/n8n-nodes-langchain.memoryBufferWindow
- Get many events in Google Calendar | n8n-nodes-base.googleCalendarTool
- calendar booking agent | @n8n/n8n-nodes-langchain.agent
- Google Gemini Chat Model | @n8n/n8n-nodes-langchain.lmChatGoogleGemini
- add to Inquiry sheet | n8n-nodes-base.googleSheetsTool
- add the appointment sheet | n8n-nodes-base.googleSheetsTool
```

### Dawood\Active\Email Agent.json

- Size: 26186 bytes
- Detected themes: n8n, email, calendar, booking

```text
Workflow name: Email Agent
Active flag: True
Node count: 9
- Create an event in Google Calendar1 | n8n-nodes-base.googleCalendarTool
- Simple Memory | @n8n/n8n-nodes-langchain.memoryBufferWindow
- Get many events in Google Calendar | n8n-nodes-base.googleCalendarTool
- calendar booking agent | @n8n/n8n-nodes-langchain.agent
- Google Gemini Chat Model | @n8n/n8n-nodes-langchain.lmChatGoogleGemini
- Gmail Trigger | n8n-nodes-base.gmailTrigger
- Send a message | n8n-nodes-base.gmail
- add the appointment sheet | n8n-nodes-base.googleSheetsTool
- add to Inquiry sheet | n8n-nodes-base.googleSheetsTool
```

### Dawood\Active\SMS  messages.json

- Size: 27560 bytes
- Detected themes: n8n, sms, calendar, booking

```text
Workflow name: SMS  messages
Active flag: True
Node count: 11
- Create an event in Google Calendar1 | n8n-nodes-base.googleCalendarTool
- Simple Memory | @n8n/n8n-nodes-langchain.memoryBufferWindow
- Get many events in Google Calendar | n8n-nodes-base.googleCalendarTool
- calendar booking agent | @n8n/n8n-nodes-langchain.agent
- Google Gemini Chat Model | @n8n/n8n-nodes-langchain.lmChatGoogleGemini
- Twilio Trigger | n8n-nodes-base.twilioTrigger
- Send an SMS/MMS/WhatsApp message | n8n-nodes-base.twilio
- Filter | n8n-nodes-base.filter
- OpenAI Chat Model | @n8n/n8n-nodes-langchain.lmChatOpenAi
- add the appointment sheet | n8n-nodes-base.googleSheetsTool
- add to Inquiry sheet | n8n-nodes-base.googleSheetsTool
```

### Dawood\Inactive\Daily data sending to clinic member.json

- Size: 9115 bytes
- Detected themes: n8n, clinic

```text
Workflow name: Daily data sending to clinic member
Active flag: False
Node count: 6
- Schedule Trigger | n8n-nodes-base.scheduleTrigger
- Get row(s) in sheet | n8n-nodes-base.googleSheets
- Filter | n8n-nodes-base.filter
- Code | n8n-nodes-base.code
- Aggregate1 | n8n-nodes-base.aggregate
- Send a message1 | n8n-nodes-base.gmail
```

### Dawood\Inactive\My workflow.json

- Size: 1466 bytes
- Detected themes: n8n, calendar

```text
Workflow name: My workflow
Active flag: False
Node count: 2
- When clicking ‘Execute workflow’ | n8n-nodes-base.manualTrigger
- Get availability in a calendar | n8n-nodes-base.googleCalendar
```

### Dawood\Inactive\NOTIFICATION.json

- Size: 17524 bytes
- Detected themes: n8n, sms, notification

```text
Workflow name: NOTIFICATION
Active flag: False
Node count: 9
- Switch | n8n-nodes-base.switch
- Get row(s) in sheet | n8n-nodes-base.googleSheets
- Send a message1 | n8n-nodes-base.gmail
- Send an SMS/MMS/WhatsApp message1 | n8n-nodes-base.twilio
- Send a message | n8n-nodes-base.gmail
- Send an SMS/MMS/WhatsApp message2 | n8n-nodes-base.twilio
- Merge | n8n-nodes-base.merge
- Update row in sheet | n8n-nodes-base.googleSheets
- Schedule Trigger | n8n-nodes-base.scheduleTrigger
```

### Dawood\Inactive\outbound calling Voice workflow.json

- Size: 17738 bytes
- Detected themes: n8n, voice, lead, outbound

```text
Workflow name: outbound calling Voice workflow
Active flag: False
Node count: 10
- Every Day at 8 AM | n8n-nodes-base.scheduleTrigger
- In Progress/Ended?1 | n8n-nodes-base.switch
- Missed/Accepted?1 | n8n-nodes-base.switch
- Wait 30 Seconds1 | n8n-nodes-base.wait
- Fetch Call Details1 | n8n-nodes-base.httpRequest
- Log Call1 | n8n-nodes-base.googleSheets
- Get Leads | n8n-nodes-base.googleSheets
- Loop Over Items | n8n-nodes-base.splitInBatches
- Mark Call 'Completed' | n8n-nodes-base.googleSheets
- Make Call3 | n8n-nodes-base.httpRequest
```

### Dawood\Inactive\outbound reachout.json

- Size: 34356 bytes
- Detected themes: n8n, sms, outbound

```text
Workflow name: outbound reachout
Active flag: False
Node count: 18
- When clicking ‘Execute workflow’ | n8n-nodes-base.manualTrigger
- Get row(s) in sheet | n8n-nodes-base.googleSheets
- Switch | n8n-nodes-base.switch
- Send a message1 | n8n-nodes-base.gmail
- Send an SMS/MMS/WhatsApp message1 | n8n-nodes-base.twilio
- Send a message | n8n-nodes-base.gmail
- Send an SMS/MMS/WhatsApp message2 | n8n-nodes-base.twilio
- Merge | n8n-nodes-base.merge
- Update row in sheet | n8n-nodes-base.googleSheets
- Switch1 | n8n-nodes-base.switch
- In Progress/Ended?1 | n8n-nodes-base.switch
- Missed/Accepted?1 | n8n-nodes-base.switch
- Wait 30 Seconds1 | n8n-nodes-base.wait
- Fetch Call Details1 | n8n-nodes-base.httpRequest
- Log Call1 | n8n-nodes-base.googleSheets
- Loop Over Items | n8n-nodes-base.splitInBatches
- Mark Call 'Completed' | n8n-nodes-base.googleSheets
- Make Call3 | n8n-nodes-base.httpRequest
```

### Dawood\Inactive\services credentials.json

- Size: 2665 bytes
- Detected themes: n8n, calendar

```text
Workflow name: services credentials
Active flag: False
Node count: 4
- When clicking ‘Execute workflow’ | n8n-nodes-base.manualTrigger
- Create spreadsheet | n8n-nodes-base.googleSheets
- Copy file | n8n-nodes-base.googleDrive
- Get availability in a calendar | n8n-nodes-base.googleCalendar
```

### Final\ClinicPilot Feature Map.docx

- Size: 10368 bytes
- Detected themes: email, sms, voice, vapi, lead, pricing, clinic, dashboard, supabase, automation, calendar, booking, notification, patient, crm

```text
ClinicPilot Feature Map
🟢 Core (MVP: live or in production now)
These are the must-have features that make ClinicPilot valuable at $199 and prove ROI.
Lead Capture & Intake
Multi-channel intake: Email, Chatbot (Voiceflow), Voice Agent (VAPI after-hours).
Unified Google Sheet (Name, Phone, Email, Service, Date/Time, RequestType, Status).
Centralized “Leads / Questionable / Spam” triage with AI filtering.
Instant Acknowledgments
Auto-email + SMS to patients within 5 minutes.
Auto-email + SMS to clinic staff (new lead alerts).
Daily Briefing
Morning summary of new leads + pending follow-ups for staff.
Smart Booking
Google Calendar availability check (freeBusy).
Proposed slots if requested date is unavailable.
HOLD system (expires after X hours).
Stripe/PayPal payment link for deposits.
Auto-confirmation email once paid (with appointment details, clinic info).
Reminders
Appointment reminders (2 days, 1 day, 2h before, with guardrails for early AM).
Outgoing Follow-ups
AI agent scans 3-day-old leads.
Sends follow-up email + call sequence (via Twilio/VAPI).
Multiple attempts (e.g., 1 email, 2–3 calls).
Lead status updated (Interested / No Response / Not Interested).
🟡 Premium (Upsell: high-value add-ons)
These features give you competitive edge and justify upselling to $299–499 tiers.
Review & Reputation Management
Post-consult (next day) or post-procedure (3–7 days later) automated review request.
SMS/email linking to Google/Facebook review pages.
AI-driven Lead Scoring (PriorityBook++)
Hot/Warm/Cold scoring based on service tier, intent, revenue potential.
Helps clinics prioritize callbacks.
Missed-Call Text-Back + Callback
If clinic misses a call, auto-SMS reply (“Sorry we missed you, book here”).
Optional AI callback to capture details immediately.
Two-Way SMS Conversatio
```

### Final\ClinicPilot GPT Agent – System Instructions.docx

- Size: 11148 bytes
- Detected themes: n8n, email, sms, lead, pricing, clinic, dashboard, lovable, automation, calendar, booking, crm

```text
ClinicPilot GPT Agent – System Instructions
Agent Name: ClinicPilotX Assistant
Short Description: An AI assistant that helps plan, build, and document the ClinicPilot automation system. It references the official documentation, pricing, feature maps, and master checklist to provide structured, step-by-step guidance for development, marketing, and investor materials.
Core Directives
1. Knowledge Base Priority Always rely on these documents first before generating or making assumptions. Each serves a specific role:
ClinicPilot – System Documentation (Developer Handbook) Technical reference for workflows, integrations, and developer handoff. Contains structured breakdown of incoming/outgoing workflows, automation schemas, and setup notes for n8n.
ClinicPilot Product Documentation (For Investors) High-level, layman-friendly explanation of ClinicPilot for stakeholders and investors. Focuses on problem, solution, value proposition, and business case.
ClinicPilot Feature Map Categorized list of features (Core, Premium, Future). Defines what’s live, what’s upsell, and what’s planned for roadmap.
ClinicPilot Suggested Pricing Packages Draft pricing tiers (starting at $199/mo) showing base plan, premium features, and ROI justification.
ClinicPilot Website Pages Website copy for all main pages (Home, Features, Integrations, FAQ, Pricing, Contact/Demo). Written in sales/marketing tone.
ClinicPilot Possible Video Titles Suggested demo/tutorial video titles for showcasing ClinicPilot in action (calls, reminders, follow-ups, etc.). Used for the “Demos” page and marketing assets.
ClinicPilot Master Checklist (Prefilled) The primary progress tracker. Tracks what’s pending, in progress, and completed across development phases (POC, MVP, Full App).
ClinicPilot PriorityBook Documentation D
```

### Final\ClinicPilot Possible Video Titles.docx

- Size: 7542 bytes
- Detected themes: email, sms, lead, clinic, dashboard, automation, calendar, booking, patient

```text
🔹 Possible Video/Demo Titles
Based on how ClinicPilot works, here are some dummy video titles you can start with for the gallery page:
“Getting Started with ClinicPilot”
“How to Capture Leads from Email, Chatbot, and Calls”
“Smart Booking with Google Calendar”
“Collecting Deposits with Stripe & PayPal”
“Setting Up Automated Reminders (2d/1d/2h)”
“How to Customize Follow-up Cadences”
“Re-engaging Old Leads with AI Calls & SMS”
“Requesting Patient Reviews Automatically”
“Using the Automation Center”
“ClinicPilot in Action: Bot Calling a Patient”
“ClinicPilot in Action: SMS Appointment Reminder Demo”
“Dashboard Walkthrough: Leads, Bookings, and ROI”
These can be placeholders until you upload real videos to your YouTube channel.
```

### Final\ClinicPilot PriorityBook Documentation.docx

- Size: 17245 bytes
- Detected themes: email, sms, voice, lead, pricing, clinic, automation, calendar, booking, patient

```text
PriorityBook Documentation
1. Introduction
What PriorityBook Is
PriorityBook is a smart service prioritization engine built into ClinicPilot. Its purpose is to categorize and score incoming appointment requests, helping clinics decide which services and patients should be prioritized in scheduling.
It works by classifying services into tiers (e.g., Basic, Intermediate, Advanced) and assigning priority scores based on factors like:
Revenue potential of the service.
Doctor involvement required (e.g., full surgery vs. short consult).
Time sensitivity or urgency.
PriorityBook integrates with Google Calendar to ensure that high-value or time-critical services get preferred booking slots, while still accommodating lower-priority requests in a fair and efficient way.
Why Clinics Need Prioritization
High-Value Services Drive Revenue
In cosmetic and plastic surgery, certain services (e.g., hair transplants, advanced procedures) generate significantly higher revenue. Prioritizing these services ensures clinics maximize profitability.
Doctor Time Is Scarce
Surgeons and specialists often do not need to be present for the full procedure. For example, a doctor may only need to spend 30 minutes in a 2-hour procedure. Overbooking is common, and PriorityBook ensures the doctor’s presence is optimized.
Better ROI on Marketing Spend
Many leads never convert. By focusing follow-ups and scheduling efforts on high-priority leads and services, clinics improve conversion rates and recover wasted marketing spend.
Operational Efficiency
Clinics with dozens of services (100+ in some cases) struggle to balance staff time, room allocation, and patient demand. PriorityBook simplifies this by automatically ranking services and suggesting the best possible scheduling option.
2. Service Categorization
```

### Final\ClinicPilot Product Documentation (For Investors).docx

- Size: 14929 bytes
- Detected themes: email, sms, voice, vapi, lead, pricing, clinic, dashboard, automation, calendar, booking, notification, front desk, patient

```text
ClinicPilot Product Documentation (For Investors)
1. Introduction
What is ClinicPilot?
ClinicPilot is an AI-powered front desk assistant designed specifically for clinics and service-based businesses. It automates the entire patient communication cycle — from capturing leads, to booking appointments, sending reminders, following up, and even requesting reviews. Think of it as a smart digital receptionist that never sleeps, working 24/7 to ensure no lead or opportunity slips through the cracks.
The Problem It Solves
Most clinics face the same challenges:
Missed Leads: Potential patients who reach out after hours or through multiple channels often go unanswered. By the time staff responds, many have already booked with another clinic.
Wasted Staff Time: Front desk staff spend hours on repetitive tasks like answering the same inquiries, confirming appointments, chasing payments, and reminding patients.
Lost Revenue: Unanswered inquiries, forgotten follow-ups, and no-shows translate directly into lost income. Even a small percentage of missed leads can mean thousands in unrealized revenue each month.
Who It’s For
ClinicPilot is designed for plastic surgeons, cosmetic clinics, dental practices, dermatologists, beauty and wellness clinics, and other businesses where patient inquiries, bookings, and follow-ups are essential. Any clinic that struggles with a high volume of calls, emails, and online inquiries can benefit from ClinicPilot’s automation.
The Value Proposition
ClinicPilot helps clinics:
Save Time by automating routine tasks like acknowledgments, reminders, and follow-ups.
Capture More Patients by responding instantly across all channels — email, phone, chatbot, and social ads.
Increase Revenue by converting old leads into paying patients and reducing costly no-shows
```

### Final\ClinicPilot Suggested Pricing Packages.docx

- Size: 8685 bytes
- Detected themes: email, sms, voice, lead, pricing, clinic, dashboard, automation, calendar, booking, patient

```text
ClinicPilot Suggested Pricing Packages
Here’s how we can frame 3 pricing tiers starting at $199, assuming we include both current features and some roadmap features to “juice it up” for investor/client appeal.
Starter – $199/mo
For small clinics that need automation without complexity.
Unified lead capture (email, chatbot, calls).
Google Calendar smart booking.
Stripe/PayPal deposit payments.
Email + SMS reminders (2d/1d/2h).
Automated acknowledgment emails + staff alerts.
Outgoing follow-ups (3-day stale leads).
Reputation requests (Google Review prompts).
Dashboard basics (Leads + Bookings).
👉 Best for solo practitioners or small clinics.
Professional – $399/mo
For growing clinics needing advanced automation and deeper insights.
Everything in Starter, plus:
Advanced chatbot plugin with knowledge base integration.
Multi-channel marketing lead capture (FB/IG ads → leads).
Customizable Automation Center (cadences, quiet hours, preferences).
AI-driven lead scoring & prioritization (“PriorityBook”).
Multi-staff calendar support (doctor, anesthesiologist, nurse).
Enhanced dashboard & reporting (ROI metrics, conversion rates).
SMS follow-ups + AI-assisted calls.
👉 Best for mid-size clinics that want to scale while saving staff time.
Enterprise – $699/mo
For clinics and networks that want the full ecosystem.
Everything in Professional, plus:
Native Mobile App (staff companion app with real-time alerts, schedules, and patient care notes).
Voice-to-care instructions (doctor dictation → patient aftercare messages).
Multi-clinic / franchise dashboard with white-label branding.
EHR/EMR integration (sync with medical records).
AI-driven marketing campaigns (promotions, seasonal offers).
Dedicated onboarding + priority support.
👉 Best for multi-location clinics or those wanting to d
```

### Final\ClinicPilot Website Pages.docx

- Size: 20052 bytes
- Detected themes: email, sms, voice, vapi, lead, pricing, clinic, dashboard, automation, calendar, booking, notification, front desk, patient, crm

```text
🌐 Website Pages for ClinicPilot
1. Home Page (Sales Pitch Hub)
Hero section (headline + subheadline + call-to-action).
Quick explainer of ClinicPilot (what it is in one line).
Core benefits (save time, capture more patients, increase revenue).
Visual/diagram of “How it Works.”
Highlight key features (with links to Features page).
Social proof (testimonials, success metrics, or quotes once available).
CTA banner (“Book a Demo” / “Start Free Trial”).
2. About Us
Story of ClinicPilot (why it was built, problem it solves).
Mission & vision (AI front desk for every clinic).
Background of the team (you don’t have to go deep; keep it credible and human).
Credibility boosters (years of experience, industry knowledge, early adopters).
3. Features
Full breakdown of all major features:
Unified Lead Capture
Chatbot Plugin
Smart Booking
Payments & Confirmations
Reminders
Follow-ups
Review Requests
Automation Center
Dashboard & Reporting
Each feature gets a headline, short explanation, and visual (icon or screenshot).
4. Integrations
Clear list of supported integrations: Gmail, Google Calendar, Google Sheets, Stripe, PayPal, Twilio/VAPI, Voiceflow, Facebook/Instagram Ads.
Explain that ClinicPilot “plugs into the tools clinics already use.”
Optional roadmap teasers (future integrations: EHR/EMR, marketing CRMs, etc.).
5. FAQ
Common questions:
How does it connect with our current systems?
Is it secure?
What happens if staff still want to call patients?
How do payments work?
Can we customize reminders/follow-ups?
Pricing FAQs.
6. Pricing
Base plan ($199/mo).
ROI example (1 lead covers the cost).
Premium add-ons (coming soon).
Clear CTA: “Book a Demo” or “Subscribe Now.”
7. Contact / Demo Request
Simple form: name, email, phone, clinic name, interest area.
Option to book a demo slot dire
```

### Final\ClinicPilot – System Documentation (Developer Handbook).docx

- Size: 229490 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, pricing, clinic, dashboard, automation, calendar, booking, notification, inbound, outbound, front desk, patient, crm

```text
ClinicPilot – System Documentation (Developer Handbook)
1. Feature Map
Core Features
Unified Lead Capture – Centralized intake from email, chatbot, and phone calls into a single system.
Smart Booking – Google Calendar integration to propose available slots and manage reservations.
Payment & Confirmation – Stripe/PayPal support for deposits with instant confirmations.
Reminders – Automated SMS/email reminders (2 days, 1 day, 2 hours before appointment).
Daily Briefings – End-of-day summary of new leads, confirmed bookings, and follow-ups.
Premium Features
Outgoing Lead Re-Engagement – Automated AI-driven follow-ups for old/unconverted leads.
Customizable Follow-up Cadence – Clinics can set preferred timing and number of calls/emails/SMS.
Reputation Management – Automated requests for Google reviews post-consultation or post-procedure.
Two-Way SMS Support – Patients can reply to reminders; system updates status automatically.
Advanced Reporting Dashboard – In-depth analytics of leads, conversions, no-shows, and ROI.
Future Vision / Roadmap
Native Staff Companion App – Mobile app for doctors/nurses to track bookings, patient notes, and reminders.
Multi-Clinic Support & White-Labeling – One account can manage multiple clinics with branding options.
AI-Generated Care Notes & Aftercare – Automatically draft post-procedure instructions for patients.
Deep EHR/EMR Integrations – Sync with medical record systems.
AI-Driven Marketing Campaigns – Intelligent targeting for old patients and local ad campaigns.
2. Incoming Workflow
Lead Capture (Email, Chatbot, Calls)
Email: Incoming leads from the website “Contact Us” form are filtered, parsed, and logged into the Leads Sheet.
Chatbot: Website chatbot (Voiceflow plugin) captures inquiries and bookings. Data is sent to the same Leads
```

### Misc 2\Checklist_ClinicPilot X – AI-Powered Front Desk Assistant.docx

- Size: 11118 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, pricing, clinic, dashboard, automation, calendar, booking, notification, outbound, front desk, crm

```text
✅ ClinicPilot X – Build Checklist (MVP + Voice Agent Demo)
Goal: Fully functional AI-powered front desk assistant for clinics (no-code, demo-ready)
📦 PHASE 1: Project Setup & Planning
Define key user stories and use cases
List all tools/accounts to create (Google, Twilio, Stripe, etc.)
Create shared folder for all assets, templates, and scripts
Draft high-level system diagram (optional for clarity)
🧠 PHASE 2: Knowledge Base + GPT Agent
Write and structure FAQ content for chatbot use
Train GPT agent or connect to a knowledge base (e.g., VoiceFlow, GPT API)
Test sample queries (e.g., pricing, hours, location)
📥 PHASE 3: Lead Capture + Notifications
Create lead intake form (Tally, Jotform, Webflow, etc.)
Connect form to Google Sheets or Airtable (via Make.com or n8n)
Trigger auto-email or SMS after form submission
Notify clinic staff (email, SMS, or dashboard)
📞 PHASE 4: Voice Agent Integration (VAPI.ai or similar)
4.1 – Basic Setup
Create VAPI.ai account
Choose voice (female/male, friendly tone)
Set up Twilio for outbound calls
Configure webhook endpoint (for AI response logic)
4.2 – Conversation Training
Write natural scripts: intro, questions, fallback, closings
Add FAQ logic (price, hours, services)
Test call scenarios: no answer, wrong number, success
4.3 – Lead Follow-Up Calls
Trigger call after form submission (via n8n or Make)
Voice agent checks interest: “Would you like to book now?”
Capture call outcome (interested, declined, no answer)
Log result to CRM (Google Sheet or Airtable)
4.4 – Booking + Payment Automation
Generate Stripe/PayPal link via API or Zapier/Make
Voice agent sends payment link (SMS or email)
Confirm payment success
Send appointment confirmation via SMS/email
Add to Google Calendar (optional)
4.5 – Demo Scenario (for Dr. Hong)
Prepare 1–2 demo l
```

### Misc 2\Clinic Pilot X — One‑page Summary & Workflow (v0.docx

- Size: 14991 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, clinic, automation, calendar, booking, notification, inbound, outbound, patient

```text
ClinicPilot X — One‑Page Summary & Workflow (v0.1)
A. Short Public Summary (for website / brochure)
ClinicPilot X is an AI‑powered front‑desk assistant for clinics. It answers calls and chats, books in‑person or virtual visits, collects booking deposits, sends reminders, and follows up—24/7. It connects to your existing tools (Calendly, Google Calendar/Outlook, Stripe/PayPal, WhatsApp/SMS, email) and logs every lead in a shared Google Sheet so your team always sees the latest status. Clinics use it to cut no‑shows, capture more leads after hours, and reduce front‑desk workload—so staff can focus on patient care.
At a glance: - Human‑sounding voice agent for calls; intelligent chatbot for your website. - Instant lead capture to Google Sheets with source tagging (phone, email, chatbot). - One‑click deposit links (Stripe/PayPal) before confirmation. - Smart reminders via SMS/email/voice; automatic re‑engagement of inactive or past leads. - Daily briefing to staff: today’s schedule, new inquiries, cancellations.
B. Workflow Quick Map (for n8n engineer)
Goal: simple, modular automation that a non‑developer can maintain.
1) Lead Sources → Intake
Phone calls → handled by Vapi voice assistant (AI captures name, phone, service, preferred date/time, in‑person vs virtual).
Emails → Gmail/IMAP watch → AI filter (spam vs lead) → extract name/phone/service/intent.
Website chatbot → Voiceflow form (same required fields).
All sources normalize fields and append a row to Google Sheets (master Leads sheet) with timestamp, source, name, phone, email, service, appointment_type, preferred_date, preferred_time, status = new.
2) Staff & Patient Notifications (on new lead)
Patient auto‑reply (channel‑matched): “Thanks—we’ll review and respond within 24 hours.” (Email/SMS/voice as available.)
C
```

### Misc 2\CLINICPILOT X Aug-3-2025.docx

- Size: 512095 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, pricing, clinic, dashboard, automation, booking, notification, inbound, outbound, front desk, patient, crm

```text
ClinicPilot X – n8n Automation Blueprint & Handoff Pack
Executive Snapshot
Goal – build an MVP of an AI‑enabled front desk for clinics that captures leads, schedules appointments, takes deposits and follows up automatically. Patients may inquire by phone or chat. The assistant should collect their details, propose open times, accept a deposit via Stripe/PayPal, send confirmations and reminders by SMS or WhatsApp, and re‑engage them if they become inactive. n8n orchestrates the workflow using no‑/low‑code nodes so that non‑developers can maintain the system.
Key components
Voice & chat front‑end – inbound voice calls are handled through Vapi while chat messages go through Voiceflow. Both send user utterances to an AI layer that extracts intent and key fields (name, contact details, preferred date/time) and summarises the conversation.
Workflow engine – n8n receives the structured data, stores it in Google Sheets, and then interacts with downstream APIs. The workflow: 1. Lead capture – create a row in Google Sheets with patient info and source; optionally send a “thank you” message. 2. Scheduling – use the Calendly API to retrieve availability and create an invite. Patients select a slot via chat or phone; the final booking is written back to Google Sheets. 3. Payments – send the patient a deposit link. For Stripe you typically listen for payment_intent.succeeded or checkout.session.completed events; for PayPal subscribe to PAYMENT.CAPTURE.COMPLETED via the developer dashboard[1]. When payment is confirmed, update the row and trigger a confirmation message. 4. Reminders and re‑engagement – schedule Twilio SMS/WhatsApp reminders 24 h and 2 h before the visit. If a deposit isn’t received within a configurable time, send a follow‑up via SMS and, if necessary, schedule an out
```

### Misc 2\ClinicPilot_Build_Checklist.csv

- Size: 2158 bytes
- Detected themes: n8n, email, sms, voice, vapi, clinic, automation, booking, notification, patient

```text
|  | Phase | Task | Estimated Time (hours) | Notes
Setup | Create Google account (if not already) | 0.25 | Basic requirement for Sheets |  Gmail |  etc.
Setup | Create Twilio account | 0.25 | Needed for SMS and voice agent features |  | 
Setup | Create Make.com account | 0.25 | Will handle visual automations |  | 
Setup | Create N8N cloud instance | 0.5 | For backend automation flows |  | 
Setup | Create OpenAI API key | 0.25 | To use GPT within your automation |  | 
Setup | Connect Google Sheets to N8N | 1 | Includes setting up credentials and sample sheet |  | 
Setup | Connect Gmail to Make | 1 | Setup includes OAuth and test automation |  | 
Setup | Connect Twilio to Make/N8N | 1.5 | Includes setup for SMS and calls |  | 
Automation – Intake | Design New Patient Intake Form | 1.5 | Form to capture all relevant data |  | 
Automation – Intake | Embed Form on Website or Landing Page | 1 | Use Make or web builder |  | 
Automation – Intake | Auto-write to Google Sheet from Form Submission | 1.5 | Sync form entries to Sheets |  | 
Automation – Notifications | Set up Email Confirmation (via Make) | 1.5 | For new inquiries or bookings |  | 
Automation – Notifications | Set up SMS Confirmation (via Twilio + Make) | 1.5 | Sends text confirmations |  | 
Automation – Voice Assistant | Integrate Voice AI (VAPI.ai) with Twilio | 3 | Handle incoming/outgoing calls |  | 
Automation – Voice Assistant | Train Voice Agent (FAQs |  Booking Dialogue) | 3.5 | Uses OpenAI prompt tuning or scripts | 
Automation – Voice Assistant | Demo Call Flow (inquiry > payment > confirmation) | 2 | Demo use-case setup |  | 
Automation – Payments | Setup Stripe or Payment Link Flow | 1.5 | Via Make or embedded in SMS/email |  | 
Automation – Payments | Auto-send confirmation message with receipt | 1 | B
```

### Misc 2\ClinicPilot_X_Handoff_Sheet.docx

- Size: 37050 bytes
- Detected themes: n8n, clinic, automation

```text
ClinicPilot X – Handoff Sheet
Step 1: Use in ChatGPT Agent Mode
Copy and paste the following prompt into ChatGPT’s Agent Mode. This will produce a structured automation blueprint for ClinicPilot X.
Prompt 1 – Agent Mode Blueprint Prompt
[Paste the full Agent Mode prompt from the previous response here]
Step 2: Give to Your n8n Expert
Hand this section to your n8n developer (e.g., on Fiverr). It includes the simplified MVP setup guide they can follow directly.
Prompt 2 – n8n MVP Setup Guide
[Paste the full n8n MVP setup guide from the previous response here]
Quick Notes
- Step 1 (Agent Mode) is for ChatGPT, not the developer. It helps you generate a detailed system blueprint.- Step 2 (MVP Setup) is for the developer to implement directly.- Together, these ensure clarity and save time.
```

### Misc 2\ClinicPilot_X_Voice_Assistant_Use_Cases.docx

- Size: 37545 bytes
- Detected themes: n8n, voice, vapi, lead, clinic, booking, front desk

```text
Voice Assistant Use Cases – ClinicPilot X
These are high-value, real-world use cases where the AI voice assistant can automate tasks typically handled by front desk staff or virtual assistants. Each use case includes the trigger condition, action performed, the tools used to automate it, and its estimated value in terms of time and money saved.
Post-Inquiry Callback
📌 Trigger Condition:No payment after 24h
🎯 Action:Call lead to ask if they want to proceed and resend payment link
🛠 Toolchain:n8n + Google Sheets + VAPI + GPT
💰 Estimated Value:$500–$1,500/mo (recovers lost consults)
Pre-Appointment Reminder
📌 Trigger Condition:Booking confirmed; 24h before appointment
🎯 Action:Call to confirm and offer reschedule option
🛠 Toolchain:n8n + Google Sheets + VAPI
💰 Estimated Value:$300–$1,000/mo (reduces no-shows)
Post-Appointment Satisfaction Call
📌 Trigger Condition:24h after appointment
🎯 Action:Call to ask about experience, offer follow-up or reviews
🛠 Toolchain:n8n + Google Sheets + VAPI + GPT
💰 Estimated Value:$300–$700/mo (boosts retention/reputation)
Quote Follow-Up (High-Ticket)
📌 Trigger Condition:Lead asks about surgery or high-cost procedure
🎯 Action:Voice call to ask if they have questions or want to book
🛠 Toolchain:n8n + Google Sheets + VAPI
💰 Estimated Value:$500–$1,000/mo (recovers high-value leads)
Failed Payment Recovery Call
📌 Trigger Condition:Stripe webhook fails or status is 'abandoned'
🎯 Action:Call to offer resend of payment link
🛠 Toolchain:n8n + Stripe + VAPI
💰 Estimated Value:$200–$600/mo (saves incomplete bookings)
After-Hours Follow-Up
📌 Trigger Condition:Lead arrives after office hours (6PM–9AM)
🎯 Action:Voicebot calls to offer help or resend payment/booking link
🛠 Toolchain:n8n + Gmail + VAPI
💰 Estimated Value:$400–$800/mo (extends hours without
```

### Misc 2\FULL DOCUMENTATION_ClinicPilot X – AI-Powered Front Desk Assistant.docx

- Size: 239615 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, pricing, clinic, dashboard, automation, calendar, booking, notification, inbound, outbound, front desk, patient, crm

```text
📘 ClinicPilot X – Full Build & Setup Documentation
This document provides the full, step-by-step build and configuration process for ClinicPilot X, based on the system architecture outlined in the "System Instructions" master guide.
It is intended to serve as:
A real-time build log of the development process
A finalized SOP (Standard Operating Procedure) for onboarding future clients
A productized manual for demo, testing, and QA purposes
📑 Table of Contents
PART 1: Initial Setup & Account Creation
1.1 Confirm Gmail Availability ✅
1.2 Create Make.com Account
1.3 Create Twilio Account
1.4 Create Stripe Account
1.5 Create Calendly Account
1.6 Create OpenAI Account
1.7 Create VAPI.ai Account
1.8 Connect Tools to Gmail for Access Control
PART 2: GPT Agent Setup
2.1 Load System Instructions into GPT Builder
2.2 Add Prompt Template & Personality Configs
2.3 Confirm Agent Is Ready
PART 3: Lead Capture Flow
3.1 Website Form → Google Sheets Flow
3.2 Form → SMS + Email Notification to Front Desk
PART 4: Voice Agent (VAPI Integration)
4.1 Setup Outbound Call Bot for Payment Confirmation
4.2 Trigger Payment Reminder Call
4.3 Log Call Summary into CRM
PART 5: CRM + Dashboard
5.1 Setup Google Sheets Tracker
5.2 Add Columns for Inquiry, Status, Payment, Follow-Up
PART 6: Testing & QA
6.1 Run Sample Test Lead
6.2 Observe Automation Behavior
6.3 Log Bugs & Fixes
PART 7: Demo & Walkthrough Prep
7.1 Setup Sample Patient Lead
7.2 Record Full Demo Flow
PART 8: Final SOP & Packaging
8.1 Export PDF Version of This Guide
8.2 Create Troubleshooting Appendix
We will now document Step 1.2 – Create Make.com Account next...
✅ PHASE 1: Initial Setup & Accounts
We'll handle each item in baby steps. Here’s the first checklist item:
🔹 Task 1.1 — Set Up Gmail (if not already configured)
✅ You already ha
```

### Misc 2\N8N Expert Response to Questions.docx

- Size: 12006 bytes
- Detected themes: email, sms, voice, lead, clinic, dashboard, lovable, automation, calendar, booking, notification, patient, crm

```text
1. Scheduling & Availability
A. Should the system auto-book the first available slot, or should it offer multiple options and wait for patient confirmation? The system should not auto-book. Instead, it should collect 2–3 preferred dates/times from the patient, then staff will call back to confirm the final slot. This works for both extremely busy doctors (booked months out) and smaller clinics with more open schedules.
B. Will there be multiple practitioners with separate Calendly links, or a single shared calendar? Please design the workflow so it supports both scenarios. For now, assume a single shared calendar (since we are starting with a free Calendly account). But structure it so we can later upgrade to multiple practitioners with separate Calendly links when needed. If a clinic already has their own Pro Calendly account, we should allow them to connect it directly.
2. Deposit & Payment Rules
A. What’s the deposit policy — fixed amount or percentage of service fee? The deposit policy will be a fixed amount of $100.
B. Should deposits be mandatory before booking, or do we allow pay-on-arrival in some cases? Deposits are mandatory before booking. Pay-on-arrival will not be allowed. The booking must be settled before it is finalized.
C. Do we need to support installment payments or only full deposits? Only full deposits will be supported. Payments will be processed through PayPal and Stripe.
3. Reminder & No-Show Logic
A. The default in the blueprint is T−48h, T−24h, T−2h reminders. Do you want to customize these timings? Yes, we want the ability to customize these reminder timings for flexibility. The default (48h, 24h, 2h) can remain in place, but each clinic should have the option to adjust them.
B. After a no-show, should we auto-offer a reschedule or just send a
```

### Misc 2\SYSTEM DOCUMENTATION_ClinicPilot X – AI-Powered Front Desk Assistant.docx

- Size: 513034 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, pricing, clinic, dashboard, supabase, automation, calendar, booking, notification, inbound, outbound, front desk, patient, crm

```text
📘 PART 0: STRUCTURE & WORKING RULES
How to use this documentation and what to expect in every section
🔧 Purpose of This Document
This document is the master blueprint for building ClinicPilot X — your AI-powered front desk assistant for clinics, spas, and dental offices.
It is written to serve:
You (the creator/founder)
Any developer or no-code assistant you bring in
Investors or partners reviewing the system
Internal documentation for client onboarding (future use)
📚 How This Document Is Structured
The document is divided into 8 main chapters, each focusing on a core part of the system:
Vision
Feature modules
Technology stack
Setup and build
User flows
Customization
Scaling
Security + future roadmap
Each chapter is broken down into smaller parts (e.g., 2.4, 4.1, etc.). If any part becomes complex, it will be divided into sub-parts (2.4.1, 2.4.2…).
🔁 Working Methodology
We will use the following development method:
Format
Description
📘 System Documentation (this doc)
Full concept and technical breakdown
✅ Checklist Doc (Doc 2)
A project tracker with all build steps
📂 Prompt/Asset Library (Doc 3)
Stores all voice scripts, prompts, templates
🧠 Notes-to-Self Blocks
Inline notes to yourself or devs (as needed)
Each section will have:
Concise title
Clear function
Explanation of how it works or connects
Tools or services involved
Integration notes or prompts (if applicable)
⚙️ Build Workflow Example
When building a feature like "AI Voice Assistant" we will:
Define the feature (in the main doc)
List build steps (in the checklist)
Provide scripts, prompts, API configs (in the library)
Track completion + updates (via checklist notes)
🧠 How to Use This in the Future
When you return to this project later — or start a new ChatGPT session — simply:
Copy/paste the latest version of:
```

### Misc 2\System instructions_ClinicPilot X – AI-Powered Front Desk Assistant.docx

- Size: 513343 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, pricing, clinic, dashboard, supabase, automation, calendar, booking, notification, inbound, outbound, front desk, patient, crm

```text
SYSTEM DOCUMENTATION
For: ClinicPilot X – AI-Powered Front Desk Assistant
📘 PART 0: STRUCTURE & WORKING RULES
How to use this documentation and what to expect in every section
🔧 Purpose of This Document
This document is the master blueprint for building ClinicPilot X — your AI-powered front desk assistant for clinics, spas, and dental offices.
It is written to serve:
You (the creator/founder)
Any developer or no-code assistant you bring in
Investors or partners reviewing the system
Internal documentation for client onboarding (future use)
📚 How This Document Is Structured
The document is divided into 8 main chapters, each focusing on a core part of the system:
Vision
Feature modules
Technology stack
Setup and build
User flows
Customization
Scaling
Security + future roadmap
Each chapter is broken down into smaller parts (e.g., 2.4, 4.1, etc.). If any part becomes complex, it will be divided into sub-parts (2.4.1, 2.4.2…).
🔁 Working Methodology
We will use the following development method:
Format
Description
📘 System Documentation (this doc)
Full concept and technical breakdown
✅ Checklist Doc (Doc 2)
A project tracker with all build steps
📂 Prompt/Asset Library (Doc 3)
Stores all voice scripts, prompts, templates
🧠 Notes-to-Self Blocks
Inline notes to yourself or devs (as needed)
Each section will have:
Concise title
Clear function
Explanation of how it works or connects
Tools or services involved
Integration notes or prompts (if applicable)
⚙️ Build Workflow Example
When building a feature like "AI Voice Assistant" we will:
Define the feature (in the main doc)
List build steps (in the checklist)
Provide scripts, prompts, API configs (in the library)
Track completion + updates (via checklist notes)
🧠 How to Use This in the Future
When you return to this project later — o
```

### Misc 2\TABLE OF CONTENTS_ClinicPilot X – AI-Powered Front Desk Assistant.docx

- Size: 10408 bytes
- Detected themes: n8n, sms, voice, vapi, lead, clinic, dashboard, supabase, automation, booking, inbound, front desk, patient, crm

```text
📘 SYSTEM DOCUMENTATION: Table of Contents
For: ClinicPilot X – AI-Powered Front Desk Assistant
🔰 PART 0: STRUCTURE & WORKING RULES
(How this document works, how it’s broken down, and how we’ll build in parts)
1. INTRODUCTION
1.1 What Is ClinicPilot X?
1.2 Who This Is For (Clinics, Spas, Dental Practices)
1.3 Key Outcomes and Benefits
1.4 System Architecture Snapshot (Text + Diagram)
2. CORE MODULES OVERVIEW
2.1 Inbox Assistant (Gmail Parser + Smart Replies)
2.2 Chatbot Assistant (FAQ + Lead Capture)
2.3 SMS Follow-Up Assistant (Twilio or VAPI)
2.4 AI Voice Agent (Powered by VAPI)
2.5 Smart Payment + Booking Flow
2.6 Knowledge Base Integration (For GPT memory)
2.7 CRM & Dashboard View (For Staff Oversight)
2.8 Alert & Escalation System (For urgent cases)
3. TECH STACK + INTEGRATIONS
3.1 APIs Used (Gmail, VAPI, OpenAI, Twilio, Stripe, Calendly)
3.2 Platform/Hosting Options
3.3 Self-hosted vs Cloud (n8n, Voiceflow, Supabase, Retool)
3.4 Cost Breakdown & API Usage Notes
4. USER ROLES & WORKFLOW
4.1 Patient/Client Journey (Lead POV)
4.2 Staff Interaction Flow (Clinic POV)
4.3 AI Agent Escalation + Limitations
4.4 Data Logging, Privacy, & Failover Scenarios
5. SETUP PROCESS (DEV + NO-CODE PATHS)
5.1 Gmail Listener & Classifier
5.2 Sheets/CRM Setup
5.3 Booking & Payment Flow
5.4 GPT Agent Tuning & Prompting
5.5 Connecting VAPI for Voice Automation
5.6 Twilio SMS Follow-Up Flow
5.7 Optional: Unified Chatbot Frontend
6. CUSTOMIZATION OPTIONS
6.1 Branding & Tone of Voice
6.2 Creating Multiple Voice Agents (Billing, Reception, Nurse)
6.3 Adding Languages or Translation
6.4 Smart Intake Forms + Data Capture
6.5 Expanding to WhatsApp, Instagram, Facebook
7. SCALING & TEAM HANDOFF
7.1 Deploying Across Multiple Clinics
7.2 White-Label Setup
7.3 Admin Training Plan
7.4 Troubleshooting
```

### Misc 2\Title_ ClinicPilot X – n8n Automation Blueprint & Handoff Pack.docx

- Size: 10873 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, clinic, automation, calendar, booking, notification, inbound, front desk, patient, crm

```text
Title: ClinicPilot X – n8n Automation Blueprint & Handoff Pack
Role: You are a senior workflow architect who designs production-grade automations in n8n (prefer n8n over Make unless there’s a hard blocker).
Goal: Produce a complete, actionable automation blueprint + developer handoff for ClinicPilot X (AI-powered front desk automations for clinics).
Authoritative context: – Product vision & capabilities (sales-facing): AI front-desk assistant that handles inquiries, bookings, reminders, follow-ups, and aggressive but professional re-engagement to increase bookings. Integrations called out: VoiceFlow chatbot on clinic websites, Calendly + Google Calendar, Stripe + PayPal payments, communications via Twilio (SMS), Vapi (voice), and email; initial Google Sheets as the lightweight CRM/log. The assistant saves staff time and boosts revenue via consistent follow-ups.
– Technical direction (developer-facing): automate lead capture → log to Google Sheets/Airtable, calendar sync & reminders, Twilio/Vapi messaging & calling, OpenAI for AI responses. (We are prioritizing n8n for this MVP.)
Must-have features for the MVP (in n8n):
Lead capture from chatbot (VoiceFlow) → n8n Webhook → append to Google Sheets “Leads” with fields: timestamp, name, phone, email, source, consent, intent, notes, status. Notify staff (email + SMS).
Booking flow via Calendly webhooks (V2—since V1 is deprecated) → log to Sheets → patient + staff notifications (email/SMS); optional Vapi voice call alert to staff. Calendly Help CenterCalendly Developer+1
Payments: handle Stripe events (Stripe Trigger) and PayPal events (PayPal Trigger or Webhook) → log to Sheets, send receipts/alerts, tag lead as “Paid/Deposit.” n8n Docs+2n8n Docs+2n8n
Reminders: 24h and 2h before appointment (SMS + email; optional Vapi confi
```

### Misc\ClinicPilot (Website Copies).docx

- Size: 20052 bytes
- Detected themes: email, sms, voice, vapi, lead, pricing, clinic, dashboard, automation, calendar, booking, notification, front desk, patient, crm

```text
🌐 Website Pages for ClinicPilot
1. Home Page (Sales Pitch Hub)
Hero section (headline + subheadline + call-to-action).
Quick explainer of ClinicPilot (what it is in one line).
Core benefits (save time, capture more patients, increase revenue).
Visual/diagram of “How it Works.”
Highlight key features (with links to Features page).
Social proof (testimonials, success metrics, or quotes once available).
CTA banner (“Book a Demo” / “Start Free Trial”).
2. About Us
Story of ClinicPilot (why it was built, problem it solves).
Mission & vision (AI front desk for every clinic).
Background of the team (you don’t have to go deep; keep it credible and human).
Credibility boosters (years of experience, industry knowledge, early adopters).
3. Features
Full breakdown of all major features:
Unified Lead Capture
Chatbot Plugin
Smart Booking
Payments & Confirmations
Reminders
Follow-ups
Review Requests
Automation Center
Dashboard & Reporting
Each feature gets a headline, short explanation, and visual (icon or screenshot).
4. Integrations
Clear list of supported integrations: Gmail, Google Calendar, Google Sheets, Stripe, PayPal, Twilio/VAPI, Voiceflow, Facebook/Instagram Ads.
Explain that ClinicPilot “plugs into the tools clinics already use.”
Optional roadmap teasers (future integrations: EHR/EMR, marketing CRMs, etc.).
5. FAQ
Common questions:
How does it connect with our current systems?
Is it secure?
What happens if staff still want to call patients?
How do payments work?
Can we customize reminders/follow-ups?
Pricing FAQs.
6. Pricing
Base plan ($199/mo).
ROI example (1 lead covers the cost).
Premium add-ons (coming soon).
Clear CTA: “Book a Demo” or “Subscribe Now.”
7. Contact / Demo Request
Simple form: name, email, phone, clinic name, interest area.
Option to book a demo slot dire
```

### Misc\ClinicPilot Complete Documentation (Oct-17-2025).docx

- Size: 14896 bytes
- Detected themes: email, sms, voice, vapi, lead, pricing, clinic, dashboard, automation, calendar, booking, notification, front desk, patient

```text
CLINICPILOT
1. Introduction
What is ClinicPilot?
ClinicPilot is an AI-powered front desk assistant designed specifically for clinics and service-based businesses. It automates the entire patient communication cycle — from capturing leads, to booking appointments, sending reminders, following up, and even requesting reviews. Think of it as a smart digital receptionist that never sleeps, working 24/7 to ensure no lead or opportunity slips through the cracks.
The Problem It Solves
Most clinics face the same challenges:
Missed Leads: Potential patients who reach out after hours or through multiple channels often go unanswered. By the time staff responds, many have already booked with another clinic.
Wasted Staff Time: Front desk staff spend hours on repetitive tasks like answering the same inquiries, confirming appointments, chasing payments, and reminding patients.
Lost Revenue: Unanswered inquiries, forgotten follow-ups, and no-shows translate directly into lost income. Even a small percentage of missed leads can mean thousands in unrealized revenue each month.
Who It’s For
ClinicPilot is designed for plastic surgeons, cosmetic clinics, dental practices, dermatologists, beauty and wellness clinics, and other businesses where patient inquiries, bookings, and follow-ups are essential. Any clinic that struggles with a high volume of calls, emails, and online inquiries can benefit from ClinicPilot’s automation.
The Value Proposition
ClinicPilot helps clinics:
Save Time by automating routine tasks like acknowledgments, reminders, and follow-ups.
Capture More Patients by responding instantly across all channels — email, phone, chatbot, and social ads.
Increase Revenue by converting old leads into paying patients and reducing costly no-shows.
In short, ClinicPilot transforms the
```

### Misc\ClinicPilot_Automation_Center_Settings_Schema.docx

- Size: 38845 bytes
- Detected themes: n8n, email, sms, lead, clinic, automation, booking, patient

```text
ClinicPilot – Automation Center Settings Schema
This document defines the configurable settings clinics can control in the Automation Center. Settings are stored in a Config sheet/table and consumed by n8n workflows and (optionally) the web app.
1) Storage Model
Settings can be stored in either a Google Sheet tab named 'Config' (key/value/notes) or in a database table ('automation_settings'). For multi-clinic use, include a clinic_id column and one row per clinic.
2) Canonical Keys & Allowed Ranges
Acknowledgments
ack_delay_minutes — int — allowed: 0–60 — Delay before sending patient/staff acknowledgments.
Channels
channels.email — bool — allowed: true/false — Enable/disable email sends.
channels.sms — bool — allowed: true/false — Enable/disable SMS sends.
channels.call — bool — allowed: true/false — Enable/disable AI call attempts.
Follow-ups
followups.start_after_days — int — allowed: 0–14 — Days after intake to begin follow-up sequence.
followups.max_emails — int — allowed: 0–10 — Max number of follow-up emails.
followups.max_sms — int — allowed: 0–10 — Max number of follow-up SMS.
followups.max_calls — int — allowed: 0–10 — Max number of follow-up calls.
followups.quiet_hours.start — HH:MM — allowed: 00:00–23:59 — Local time start of quiet hours.
followups.quiet_hours.end — HH:MM — allowed: 00:00–23:59 — Local time end of quiet hours.
followups.timezone — string — allowed: IANA tz — Clinic timezone, e.g., Asia/Manila.
Booking
booking.search_radius_days — int — allowed: 0–30 — ±Days around requested date to search.
booking.hold_hours — int — allowed: 1–72 — Length of provisional hold before expiry.
booking.deposit_amount — number — allowed: 0–5000 — Deposit (in clinic currency).
Reviews
reviews.consult_days_after — int — allowed: 0–7 — Days after consult to request a
```

### Misc\ClinicPilot_Developer_Handoff_n8n.docx

- Size: 38107 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, clinic, dashboard, supabase, automation, calendar, booking, patient

```text
ClinicPilot – Developer Handoff (n8n Workflows)
This document provides guidance for n8n specialists (or internal admins) to understand the ClinicPilot system, import workflows, configure credentials, and know where to adjust clinic-specific variables.
1) Workflow Import
• Workflows are exported as JSON files from n8n.• To import, log into self-hosted n8n → Workflows → Import from File.• After import, review all nodes for credential placeholders.
2) Required Credentials
Gmail OAuth2 (for intake and ACK emails).
Google Sheets OAuth2/Service Account (for leads database).
Google Calendar OAuth2/Service Account (for booking).
Stripe API key (for payments).
PayPal API key (if enabled).
Twilio SID/Auth Token (for SMS & calls).
VAPI API Key (for AI voice agent).
Facebook App/Page Token (for Lead Ads).
Voiceflow webhook URL (for chatbot intake).
Optional: Airtable/Baserow/Supabase keys (for dashboards).
3) Workflow Groups
Incoming Workflow → Email/Chatbot/Voice intake → Normalize → ACK patient & staff → Smart Booking → Payment → Calendar.
Outgoing Workflow → Identify stale leads → Email/SMS/Call follow-ups → Log outcomes.
Reminders → Scheduled trigger (cron) → Send reminders 2d/1d/2h before appointment.
Review Requests → Delayed trigger (1–7 days) → Email/SMS review request.
Automation Center Sync → Read Config sheet/DB → Apply per-clinic settings.
Reporting → Daily 08:00 summary email to staff with leads, bookings, and follow-ups.
4) Variables & Configurable Settings
Clinic-specific values should be externalized in the Config sheet or env vars. Examples:• clinic_name, clinic_email, clinic_phone, clinic_address• deposit_amount• ack_delay_minutes• followup cadence limits• timezone
Developers should avoid hardcoding these in workflow nodes.
5) Error Handling
• Each workflow should
```

### Misc\ClinicPilot_Email_and_SMS_Templates.docx

- Size: 37873 bytes
- Detected themes: email, sms, lead, clinic, booking, patient

```text
ClinicPilot – Email & SMS Templates
This document contains standardized templates for patient-facing and clinic-facing communication. Variables are wrapped in {{brackets}} for dynamic substitution from the lead database.
1) Patient Acknowledgment
Email
Subject: Thank you for reaching out, {{name}}!Body:Hello {{name}},Thank you for contacting {{clinic_name}} regarding {{service}}. We’ve received your request and one of our staff will be in touch within 24 hours.Requested Date/Time: {{preferred_date}} at {{preferred_time}}Best regards,{{clinic_name}} Team
SMS
Hi {{name}}, thanks for contacting {{clinic_name}}. We got your request for {{service}}. Our team will reach out within 24h. – {{clinic_name}}
2) Clinic Staff Alert
Email
Subject: New Lead – {{service}} inquiry from {{name}}Body:New lead details:Name: {{name}}Email: {{email}}Phone: {{phone}}Service: {{service}}Requested Date: {{preferred_date}}Please follow up within 24 hours.
SMS
New lead: {{name}}, {{service}}, requested {{preferred_date}}. Check Leads sheet for details.
3) Payment Request
Email
Subject: Confirm your booking – action requiredBody:Hello {{name}},We’ve held your appointment for {{service}} on {{proposed_date}} at {{proposed_time}}.To confirm, please complete your deposit payment here: {{payment_link}}This hold will expire on {{hold_expires_at}} if payment is not received.Best regards,{{clinic_name}} Team
SMS
Hi {{name}}, please confirm your booking for {{service}} on {{proposed_date}} at {{proposed_time}}. Pay deposit here: {{payment_link}} (expires {{hold_expires_at}}).
4) Appointment Confirmation
Email
Subject: Appointment Confirmed – {{service}} on {{confirmed_date}}Body:Hello {{name}},Your booking for {{service}} on {{confirmed_date}} at {{confirmed_time}} is confirmed.Clinic address: {{clinic_ad
```

### Misc\ClinicPilot_Feature_Map.docx

- Size: 38112 bytes
- Detected themes: email, sms, voice, vapi, lead, clinic, dashboard, supabase, calendar, booking, notification, patient

```text
ClinicPilot Feature Map
🟢 Core (MVP – Launch Package)
These are the essential features already in production or being finalized. They form the $199/month base package.
Lead Capture & Intake: Email, Chatbot (Voiceflow), Voice Agent (VAPI after-hours) → Unified Google Sheet.
AI Filtering: Sort incoming messages into Leads / Questionable / Spam.
Instant Acknowledgments: Auto-email + SMS to patients within 5 minutes.
Staff Alerts: Auto-email + SMS notifications to clinic staff.
Smart Booking: Google Calendar availability check, slot proposals, HOLD system with expiry.
Payment Integration: Stripe/PayPal link, auto-confirmation via webhook.
Reminders: Automated reminders (2 days, 1 day, 2h before appointment) with quiet-hour rules.
Daily Briefing: Morning summary of new leads and pending follow-ups.
Outgoing Follow-ups: Automated email + AI calls to 3-day-old unconverted leads.
🟡 Premium (Upsell – Advanced Features)
These features differentiate ClinicPilot and can justify upselling to higher-tier plans ($299–499).
Reviews & Reputation Management: Post-consult (1d) or post-procedure (3–7d) review requests by SMS/email.
AI-driven Lead Scoring (PriorityBook++): Hot/Warm/Cold classification based on service tier, urgency, and revenue.
Missed-Call Recovery: Instant SMS reply + optional AI callback when calls are missed.
Two-Way SMS Conversations: Patients can reply (e.g., reschedule) → AI parses → updates Calendar/Sheet.
Social Media Ad Capture: Facebook/Instagram Lead Ads → pipeline into Leads sheet + auto-ACK.
Customizable Follow-up Cadences: Clinics set ACK delay, follow-up timing, and channel mix (email/SMS/call).
Internal Staff Dashboard: Lightweight view (Baserow/Supabase) for leads, appointments, follow-ups, and toggles.
🔵 Future (Expansion Roadmap)
Longer-term features for
```

### Misc\ClinicPilot_Incoming_Workflow.docx

- Size: 37815 bytes
- Detected themes: email, sms, voice, vapi, lead, clinic, automation, calendar, booking, notification, patient

```text
ClinicPilot Incoming Workflow
This document describes how ClinicPilot handles all incoming leads (patients or prospects) from different channels, normalizes the data into a unified spreadsheet, and triggers automated acknowledgments and booking logic.
1. Channels of Intake
Email → Captured via Gmail watch (filtered to Contact Us messages).
Chatbot (Voiceflow) → Captures name, phone, email, service, request type; posts to webhook.
Voice Agent (VAPI after-hours) → Answers calls, captures lead info; sends webhook payload.
Business Hours Calls → Managed manually by clinic staff (outside automation scope).
2. Data Normalization
All lead data is written into the unified 'Leads' sheet with the following canonical columns:
lead_id, created_at, channel, request_type, name, email, phone
service_raw, service_mapped, tier, price_text, base_price
preferred_date, preferred_time_window, message
status, priority_score
proposed_slots, chosen_slot, hold_expires_at
stripe_checkout_url, payment_status
calendar_event_id, calendar_room, calendar_doctor
last_contacted_at, outcome, notes
3. Acknowledgments
Patient Acknowledgment → Email + SMS within 5 minutes.
Clinic Acknowledgment → Email + SMS to staff notifying them of the new lead.
Status column updated to 'ACKED' once both notifications are sent.
4. Smart Booking
Check Google Calendar availability (freeBusy API).
If requested slot is available → propose that slot and HOLD it for 24h.
If not available → propose 2-3 alternative slots closest to the request.
Update 'proposed_slots' and 'hold_expires_at' in sheet.
5. Payment Handling
Generate Stripe/PayPal Checkout link for deposit.
Send patient email/SMS with payment link if slot is held.
Stripe webhook updates sheet with payment_status=PAID.
If paid → create Google Calendar event + mark sta
```

### Misc\ClinicPilot_Integrations_and_Credentials.docx

- Size: 37686 bytes
- Detected themes: n8n, email, sms, voice, vapi, lead, clinic, dashboard, supabase, automation, calendar, booking, notification, patient

```text
ClinicPilot Integrations & Credentials
This document lists all the external services and tools that ClinicPilot connects to, along with credential requirements and notes for n8n configuration.
1. Gmail
Purpose: Capture leads from Contact Us emails, auto-ACK patients & staff.
n8n Node: Gmail Trigger / Gmail Read → Append to Sheet
Credentials: Google OAuth2 (Clinic’s Gmail/Workspace account).
Scopes: read, send, modify.
2. Google Sheets
Purpose: Central database of all leads and automation statuses.
n8n Node: Google Sheets (Append Row, Update Row, Read Row).
Credentials: Service Account JSON or OAuth2.
3. Google Calendar
Purpose: Smart Booking → Check freeBusy, hold slots, create confirmed events.
n8n Node: Google Calendar (Get Availability, Create Event, Delete Event).
Credentials: Service Account JSON or OAuth2.
Notes: Requires 'Make this account a delegate' if using clinic’s calendar.
4. Stripe / PayPal
Purpose: Collect booking deposits.
n8n Node: HTTP Request (to Stripe API) or Stripe Trigger (webhook).
Credentials: API Secret Key (live + test).
Notes: Webhook URL from n8n must be registered in Stripe dashboard.
5. Twilio / VAPI
Purpose: Send SMS notifications, place/receive AI-assisted calls.
n8n Node: Twilio SMS, Twilio Call / HTTP Request for VAPI.
Credentials: Twilio Account SID + Auth Token; VAPI API Key.
Notes: Twilio numbers must be SMS-enabled; VAPI requires agent configuration.
6. Voiceflow
Purpose: Web chatbot for bookings and inquiries.
n8n Node: Webhook (receives payload from Voiceflow).
Credentials: None (incoming webhook).
Notes: Map Voiceflow variables → Leads sheet columns.
7. Facebook / Instagram Lead Ads
Purpose: Capture leads directly from social ads into ClinicPilot.
n8n Node: Webhook (Zapier proxy or Meta webhook).
Credentials: Facebook Developer
```

### Misc\ClinicPilot_Outgoing_Workflow.docx

- Size: 37467 bytes
- Detected themes: email, sms, lead, clinic, automation, notification, outbound, patient

```text
ClinicPilot Outgoing Workflow
This document describes how ClinicPilot handles outbound automations. The goal is to re-engage leads that have not booked, remind patients of upcoming appointments, and reduce no-shows through automated email, SMS, and AI-assisted calls.
1. Target Leads
The outgoing workflow identifies leads that require follow-up or reminders:
3-day-old leads with status NEW or ACKED but not CONFIRMED.
Patients with upcoming appointments (reminders 2d/1d/2h before).
Missed calls (optional add-on: Missed Call Recovery with SMS callback).
2. Follow-up Cadence
Day 3 → Send email reminder.
Day 4–6 → Place AI-assisted call attempts (2–3 tries).
Each attempt is logged in the sheet under outcome/status.
Cadence is customizable per clinic via Automation Center.
3. Appointment Reminders
2 days before → Email reminder with appointment details.
1 day before → SMS reminder.
2 hours before → SMS reminder unless appointment <10am (then send 1h before).
Reminders respect quiet hours (no messages between 8pm–8am).
4. Outcomes & Status Updates
Interested → Lead books an appointment (status CONFIRMED).
Not Interested → Marked as LOST.
No Response → After final attempt, status set to CLOSED_NO_RESPONSE.
All updates logged in sheet with last_contacted_at and outcome notes.
5. Notifications & Reporting
Daily Briefing includes summary of follow-ups attempted and their outcomes.
Optional: Weekly conversion report on follow-up effectiveness.
```
