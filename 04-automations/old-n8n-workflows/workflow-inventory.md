# Old n8n Workflow Inventory

Copied from `D:\PROJECTS\CLINICPILOT X (Old)\Dawood`. Treat these as reference workflows until credentials, webhook URLs, and current hosting are audited.

## [VAPI] inbound calling scenario.json

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

## Daily data sending to clinic member.json

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

## Email Agent.json

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

## My workflow.json

```text
Workflow name: My workflow
Active flag: False
Node count: 2
- When clicking ‘Execute workflow’ | n8n-nodes-base.manualTrigger
- Get availability in a calendar | n8n-nodes-base.googleCalendar
```

## NOTIFICATION.json

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

## outbound calling Voice workflow.json

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

## outbound reachout.json

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

## services credentials.json

```text
Workflow name: services credentials
Active flag: False
Node count: 4
- When clicking ‘Execute workflow’ | n8n-nodes-base.manualTrigger
- Create spreadsheet | n8n-nodes-base.googleSheets
- Copy file | n8n-nodes-base.googleDrive
- Get availability in a calendar | n8n-nodes-base.googleCalendar
```

## SMS  messages.json

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
