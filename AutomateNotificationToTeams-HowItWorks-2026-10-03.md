## Trigger

- The user starts Automate Notification to Teams. After activation, a chosen event or schedule starts future notifications in the connected tool.

## Inputs

- The user chooses one notification or an ongoing automation.
- The Teams team and channel, person, or group chat identify the destination.
- The notification text and optional linked item define the message.
- For automation, the source event or schedule with time zone defines when it runs.
- The selected draft or live mode determines whether it sends or activates.

## What happens

1. The plugin asks one missing question at a time. It waits for answers and remembers supplied choices.
2. It checks the available Teams connection and, for automation, the tool that can run the event or schedule. Missing access leaves the setup unconfigured. It can still prepare the message.
3. It finds the exact destination and optional linked item. If several items match, it asks which one to use. It reports a missing item rather than substituting another.
4. It shows the destination, text, link, and automation trigger when relevant. It asks for draft or live mode only when that choice has not been supplied.
5. For a draft, it saves without sending or activating. For a live message, it sends once. For a live automation, it configures, activates, and reads back the setup.
6. For a requested test, it runs the chosen test once. It states whether the test used the real trigger or replayed the actions.
7. It finds the delivered Teams message. It clicks a requested record link and checks the item it opens. After an uncertain send, it searches before retrying.
8. It reports the verified checkpoints and missing results. A successful send does not prove grant approval, payment, or email receipt.

## Outputs

- An unsent draft or inactive automation in the selected tool, when draft mode is chosen.
- A Teams notification or active automation when the live action succeeds.
- Delivery and link verification results, with a report or screenshots when requested.
