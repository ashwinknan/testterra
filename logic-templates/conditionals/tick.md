# Tick

Applying Tick logic template to an asset allows you to attach a custom timer, whose start and stop can be controlled. This logic template can be used as a starting event for other logic templates

To add the Tick logic template to an asset, follow these steps:

1. Go to the Logic Tab.
2. Select Tick under the header "Conditionals".
3. Drag and drop it onto the desired asset.

You can edit the following parameters of this template directly through the scene editor interface:\


<table><thead><tr><th width="216">Parameters</th><th>Description</th></tr></thead><tbody><tr><td>Tick When</td><td><p>You can choose the start event for the object's timer from this dropdown:</p><ul><li>Game Start</li><li>Broadcast Received: When the object receives a broadcast message.</li></ul><p><br></p></td></tr><tr><td>Stop When</td><td>You can choose which broadcast will stop the execution when listened to.</td></tr><tr><td>Resume When</td><td>You can choose which broadcast will resume the execution when listened to.</td></tr><tr><td>Special Broadcasts</td><td><p>You can specify time intervals for the template to run and generate a broadcast. The available fields are:</p><ul><li><strong>When</strong>: Select "At" or "Every".</li><li><strong>In</strong>: Specify the time interval for the broadcast.</li><li><strong>Broadcast</strong>: Define the broadcast to be generated.</li></ul></td></tr></tbody></table>

### Accessing the Tick Logic Template using T\#

If you want to further customize this logic template, you can do so by accessing its T# Wrapper -  [TickTemplate](../../coding-using-t/t-logic-template-wrappers.md#ticktemplate)
