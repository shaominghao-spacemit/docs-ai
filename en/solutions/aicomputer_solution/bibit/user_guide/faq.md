# Frequently Asked Questions

Start with the checks below. If the problem persists, contact the developer community.

| Problem or message | Suggested action |
| --- | --- |
| Connection failed at the top of the window | Check your network connection, then click the retry button next to the message. If it still fails, record the full message and ask the developer community |
| Select an assistant, or no experts available | Open the expert list on the new-chat page, refresh, and choose an available expert. Ask the community if none are available |
| Assistant reports no global model selected | Add a model under **Settings → Management → Models** and make it the current model before sending a new Runtime chat message |
| Send button unavailable | Make sure you have entered text or added an attachment, no attachment is still processing or reporting an error, and an expert is available. Check the message in the input area |
| The response stops updating | Check for running tools or pending approval. Review status and errors before stopping or retrying |
| Previous message operation result is unconfirmed | Use **Retry the original action** or **Send again** if available, or reload the conversation. Do not immediately submit the same device operation again |
| Conversation won't load | Select **Reload conversation**. Sending may be disabled until the conversation loads again |
| Cannot find an old chat | Clear the search, expand the sidebar, check the connection, and check whether the selected service has changed |
| File upload failed | Read the full error, check that the file exists and meets limits, then retry or remove and reselect it |
| Cannot open or summarize a file | Check that it still exists, return to its original conversation, and wait for the current answer to finish. Search again if it changed |
| Screenshot option unavailable | Check the desktop session, screenshot tool, and shortcut status. Use a regular file attachment for now |
| Global shortcut does nothing | Check that Enable BiBit is on, the shortcut is registered, and another desktop shortcut is not using it |
| Floating ball missing | Right-click the tray icon and select Show/Hide Floating Ball. If needed, open the main window from the application menu and check background settings |
| Agent Hub, Memory, or similar entry missing | Its plugin may not be enabled. Older Agent Hub versions may have different entry points and operations. Record the version and interface and ask the community |
| No Management or Monitoring group in Settings | Check under **Settings → Extensions** that the Runtime management extension is installed and enabled, then restart BiBit as prompted |
| Runtime page reports Runtime unavailable or host capability not provided | Check that Runtime is running and plugin authorization is valid. Refresh; if it still fails, record the full message and ask the developer community |
| Test connection fails | Check the vendor, the API Base (it usually ends with `/v1`) and the API key; a private gateway needs a reachable address. If the page reports a plugin/Runtime protocol mismatch, confirm the Runtime package and plugin versions match |
| MCP stays Preparing or Failed | The initial installation may take some time. Wait a moment, then refresh. On failure, read the card's error and check the command, dependencies, and directory permissions |
| Security page reports securityd unavailable | Check the Runtime security bridge and securityd status. Do not repeatedly save policies; record the message and refresh first |

## Ask the Developer Community for Help

If the checks above do not resolve the problem, contact the developer community and provide the following information:

1. Open **Settings → General → App Version** and click **Copy version information**.
2. Record the time, conversation, actions, expected result, and actual result.
3. Copy the complete error text. If a simple request without private information reproduces the issue, include the steps.
4. If logs are needed, open or reveal them through **App Logs** in General settings. Share only the relevant excerpts.

Check logs and screenshots for personal content, file paths, accounts, and keys before sharing. Include only information needed to investigate the problem.

## Related Guides

[Chat and Conversations](modules/chat.md) · [Files and Reference Materials](modules/files.md) · [Quick Chat](modules/quick-chat.md) · [Agent Hub](modules/agent-hub.md) · [Memory](modules/memory.md) · [Settings and Permissions](modules/settings.md) · [Runtime Management and Monitoring](modules/runtime.md)

[Quick Start](quickstart.md) · [Documentation Home](../index.md)
