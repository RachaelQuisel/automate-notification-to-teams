---
name: automate-notification-to-teams
description: Interactively set up Microsoft Teams notifications. Ask about the destination, message, trigger, and optional record link. Send one message or configure an ongoing automation in a connected tool. Verify delivery and record links.
---

# Automate Notification to Teams

Read [the conversation and writing rules](references/conversation-and-writing.md) before responding. Apply them to all user-facing text.


Help the user choose when Microsoft Teams should receive a notification. Ask a few questions before taking action. A request to run this skill without other details starts setup. It does not send a previous message or replay an earlier test.

Apply [the Voice Align writing rules](references/plain-english.md) to every question, notification, explanation, error message, and report. Keep exact product names, field names, statuses, and commands.

## Start the conversation

Use the question tool when available. Ask one short question at a time. Wait for each answer. Skip a question when the user has already answered it for this setup.

1. Ask: “Do you want to send one notification now or set up an automatic notification?”
   Offer “Send one now” and “Set up an automation.”
2. Ask: “Where should the notification go in Microsoft Teams?”
   Ask for the team and channel, or the person or group chat.
3. For an automation, ask: “What should start the notification?”
   Offer “An event in another app” and “A schedule.”
   For an event, ask which app records the event. For a schedule, ask for the time and time zone.
4. Ask: “What should the notification say? Should it include a link?”
   If the user wants a link, ask what should open. Use a recognizable item name rather than asking the user for an internal record identifier.

Reuse answers from this setup. Do not select the grant workflow from earlier conversation unless the user chooses it for this run.

## Explain the setup

Tell the user which connected tool can perform the requested work. Explain where the automatic notification will run. The plugin provides instructions for Codex. It does not include a service that watches events by itself.

For a one-time message, use an available Teams connection or the authorized signed-in Teams browser.

For an event in another app, inspect that app's supported automation tools. For a schedule, inspect the available scheduling tools. Use a tool that can perform the requested action. Do not invent a Teams connection or an unsupported trigger.

If a required connection is missing, name the missing connection. Explain the next setup step. Continue preparing the message and setup details when possible. Report the automation as unconfigured until the required tool is available.

Show a brief setup preview:

- State the Teams destination.
- State the event or schedule for an automation.
- Show the notification text.
- Show the link and the item it opens, when requested.
- Name the tool that will send future notifications.

If the user has not chosen a draft or live setup, ask the question for their chosen mode. For one message, ask: “Would you like to keep this as a draft or send it now?” For an automation, ask: “Would you like to save this as a draft or activate it?” Reuse an explicit instruction to send or activate. Do not ask for the same approval twice.

## Find the right item

Discover the current recipient and record identifiers through the connected tools. Confirm the exact destination. Do not substitute a similarly named channel or chat.

Inspect the target app's existing record page before creating a link. Use the identifier for the item the user selected. An organization's QuickBooks Vendor ID can identify an organization. It cannot identify one of that organization's several grants.

If a lookup returns several items, ask the user to choose the intended item. If it returns none, explain what could not be found. Do not silently select the first result or send a link to a list page.

For one review destination, include one descriptive link. Follow the user's requested link count. Keep credentials and temporary sign-in links out of messages and saved evidence.

## Send one notification

For a draft, prepare the message and report where it is saved. Stop before sending.

For a live send, use the sender's supported message format. Send the chosen message once. Keep its message identifier or timestamp.

Find the matching message in the selected Teams destination. If it contains a record link, click that delivered link. Confirm that the intended item opens.

If the send returns an uncertain result, check the destination before retrying. Do not create a duplicate message because the first response was missing.

## Set up an automation

Read the current source configuration. Save a copy before editing an existing workflow. Preserve the trigger, recipients, business rules, logging, and unrelated actions unless the user requests a change.

Read [the Airtable reference](references/airtable.md) for an Airtable Teams action. Prefer a supported connector or command. Use the signed-in editor when it provides an authorized action that the connector cannot perform.

Configure the chosen event or schedule, message, and destination. Use the triggering item's current values to build a record link. Follow the sender's supported message format.

For a draft, save the draft and report where it is stored. For live setup, publish or activate the automation. Read back its active configuration. Saving a draft does not activate future notifications.

For a requested live test, identify a current test record. Preserve existing attachments, consent, approval, and payment fields unless changing them is part of the requested test.

Run the chosen test once. A full submission test starts with the real event or form. An editor's Test automation replays the actions. It does not prove that a new form submission reached the trigger.

Inspect the run and completion log. Find the new Teams message. Count links inside that message. Click the delivered record link and confirm the intended item.

If a step fails, explain which result is missing. Check for a delivered message before retrying a send. Do not add new business rules to resolve a test failure.

## Report the result

Use the user's chosen format. Name the actual destination and the item tested. Save screenshots or a report when they make the result reviewable.

State the checkpoints that were checked:

- **Draft saved:** The setup is saved but is not active.
- **Active:** The tool is configured to send future notifications.
- **Accepted:** The sending tool reports that it accepted the message.
- **Delivered:** The matching message is visible in Teams.
- **Link verified:** Clicking the delivered link opened the intended item.

Explain a test result by naming the behavior checked. State whether the test used a real event or a replay. Identify material gaps and test effects.

The setup does not prove grant approval, payment, or email receipt. Publish files to GitHub only when requested or already authorized for the current work. A GitHub upload does not activate a notification.
