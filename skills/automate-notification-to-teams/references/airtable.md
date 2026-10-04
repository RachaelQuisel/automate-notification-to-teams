# Airtable Teams notifications

Use these notes when the user chooses an Airtable automation. They describe an observed workflow. Read the current configuration before applying them.

## Read the current setup

Find the actual base, automation, fields, Teams account, and recipient. Do not copy identifiers from another project.

When the connector supports it, request `includeDeployedVersion: true`. This returns the published configuration when it differs from the draft. Check that the intended change is active.

Keep the existing Teams account and destination when the user only wants a link change. If the account fails, diagnose the connection. Do not silently replace it.

## Preserve message fields

An observed `sendToMsTeams` action used `richTextMessageContent`. This is a list containing text and references to values from earlier steps.

A `quillDelta` entry contains inserted text. An `unformattedTemplateValue` entry contains a reference to a trigger field or script output.

The following pattern worked for one Grant link:

```text
A new final report from [Organization Text] for [Program Name Text]
has been submitted. Please <a href="[ziteGrantUrl]">review the submitted
final report in Zite</a>.
```

The bracketed names represent dynamic fields. They are not text to paste into the message.

The script used the triggering Grant's record identifier:

```javascript
const grantUrl = ziteBaseUrl + '/grant/' + encodeURIComponent(recordId);
output.set('ziteGrantUrl', grantUrl);
```

Use this pattern only when the current target app supports that page address. Keep the Grant link when the user wants a specific Grant. Remove any unwanted organization link from the message.

## Use the editor when needed

In the observed session, the update connector rejected the rich message format. A simpler message update returned a permission error. These results apply to that session.

Inspect the actual error. Use the authorized signed-in editor when it supports the required change.

The editor had a Delete action in each dynamic field's menu. Deleting a URL field left an empty link in the surrounding text. That text also needed to be removed.

Filling ordinary description fields worked. Filling the rich message field was unreliable. Read back the resulting template after editing.

Use Update to publish when the user has chosen live setup. Check the active configuration after publication.

## Test the result

Airtable's Test automation ran live actions. It could send a real Teams message and create an Automation Log without a new form submission.

The observed workflow logged Started before the Teams action. It logged Succeeded after Teams accepted the message. This result did not confirm email receipt or a working record link.

Find the new message in Teams. Count links inside that message. Click the requested link and check the intended item.

Teams may open a temporary sign-in address before the app loads. Do not save that temporary address. Save the final app address and recognizable item details.
