# Automate Notification to Teams

Run `$automate-notification-to-teams` to begin setup.

The plugin asks one missing question at a time. It waits for your answer and remembers earlier answers. You choose whether to send one message or set up an automation. You provide the Microsoft Teams destination and message. For an automation, you also choose an event or schedule. You can include a link to the relevant item.

The plugin shows the setup before it acts. A connected tool sends the message. An activated automation sends future messages from that tool.

Read [how it works](AutomateNotificationToTeams-HowItWorks-2026-10-03.md) for the complete process.

## Install

This repository is the Codex marketplace for the plugin. The catalog is [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json). Install the plugin by name:

```shell
codex plugin marketplace add RachaelQuisel/automate-notification-to-teams
codex plugin add automate-notification-to-teams@automate-notification-to-teams
```

From a local checkout of this repository, add that directory as the marketplace, then install the same plugin:

```shell
codex plugin marketplace add .
codex plugin add automate-notification-to-teams@automate-notification-to-teams
```

The canonical source is [this GitHub repository](https://github.com/RachaelQuisel/automate-notification-to-teams). Local installations and ZIP files are copies of this source.

## License

MIT. See [LICENSE](LICENSE).
