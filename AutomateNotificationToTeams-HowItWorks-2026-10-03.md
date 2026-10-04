## Trigger

- You run `$automate-notification-to-teams`.
- For an ongoing automation, future notifications start from the event or schedule you choose. They begin after the connected tool is configured and activated.

## Inputs

- You choose one message or an ongoing automation.
- You provide the Microsoft Teams team and channel, or the person or group chat.
- You provide the message.
- For an automation, you choose an event and its source app, or a schedule and time zone.
- You identify the item that a link should open, when a link is needed.
- You choose a draft or live setup.
- The plugin uses available connections to Teams and the source app.

## What happens

1. The plugin asks one short question at a time. It waits for your answer. It skips details you have already supplied for this setup.
2. It checks which connected tool can send the notification. For an automation, it also checks which tool can watch the chosen event or run the schedule. The plugin does not watch events by itself.
3. If a required connection is missing, it explains the setup gap. It can prepare the message. It cannot report the automation as active.
4. It finds the selected Teams destination. If you want a link, it finds the intended item. If several items match, it asks you to choose one. If none match, it explains what could not be found.
5. It shows the destination, message, and link. For an automation, it also shows the event or schedule and the tool that will run it. If you have not chosen a draft or live setup, it asks you to choose.
6. For a draft, it saves the message or automation without sending. For a live message, it sends once through Teams. For live automation setup, it configures and activates the connected tool.
7. For a live test, it runs the chosen test once. It states whether the test used a real event or replayed the automation actions.
8. After a send, it checks the matching message in Teams. If there is a record link, it clicks that link. It checks that the intended item opens.
9. If a send returns an uncertain result, it checks for the message before retrying. If a step fails, it reports the missing result.

## Outputs

- For one message, the selected Teams channel or chat receives the notification when the send succeeds.
- For a draft, the plugin reports where the unsent message or inactive automation is saved.
- For an activated automation, the chosen tool sends future notifications when the chosen event occurs or the scheduled time arrives.
- The plugin reports the checkpoints it verified. It distinguishes a saved draft, an active automation, an accepted send, a visible Teams message, and a working record link.
- When requested, it saves screenshots and a report of the test.
