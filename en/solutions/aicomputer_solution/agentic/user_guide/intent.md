---
sidebar_position: 4
---

# Intent Recognition

With BiBit, describe what you want to do without memorizing tool names or commands. Supported, explicit device operations are generally handled locally first. Requests requiring explanation, writing, analysis, or interpretation of complex requirements are passed to the cloud assistant.

This page explains which requests suit local processing, which usually need the cloud, and how to phrase requests for useful results.

For specific tools and their purposes, see the [BiBit Local Tool List](tools.md). A tool running on the device does not mean the request is understood entirely locally. That list also identifies extensions requiring network access or cloud coordination.

> Examples show typical supported processing patterns. Similar wording does not guarantee the same route. Version, enabled features, service status, and context also matter. Requests that cannot be clearly recognized locally may be passed to the cloud.

## 1. Remember the Main Distinction

**Clear requests to control this device are usually handled locally first. Requests involving explanation, analysis, writing, or complex task planning are usually sent to the cloud.**

| Request | Typical processing | Reason |
| --- | --- | --- |
| “Set the volume to 30%.” | Local first | Clear action and target value |
| “Show the current system time.” | Local first | Read existing device information |
| “Open the browser.” | Local first | Launch an installed application |
| “Why is there no sound?” | Cloud | Analyze a cause rather than simply change volume |
| “Write a meeting notice.” | Cloud | Generate text |
| “Open the browser, search for information, and write a report.” | Cloud | Coordinate several different steps |

Local processing does not necessarily mean a request is handled entirely offline. Likewise, cloud processing does not mean operations take place on a remote computer. For example, the cloud may interpret a task and then use tools on your device to carry it out.

## 2. Requests Suited to Local Processing

### 2.1 Volume and Display

Specify what to change and the value you want.

| Goal | Example request |
| --- | --- |
| Check volume | “Show the current volume.” |
| Set volume | “Set the volume to 30%.” |
| Adjust volume relatively | “Turn the system volume up a little.” |
| Mute | “Mute the sound.” |
| Unmute | “Unmute the sound.” |
| Check brightness | “Show the current screen brightness.” |
| Set brightness | “Set screen brightness to 60%.” |
| Check display modes | “Show supported display modes.” |
| Set resolution | “Set screen resolution to 1920×1080.” |

Adjusting brightness or resolution depends on support from your device and display. Even if BiBit understands your request, the hardware may not support the requested setting. Check the result to confirm it was applied.

“Set it to 30%” and “Turn it up a little” mean different things. If you want a specific volume level, say “Set the volume to 30%.”

### 2.2 Open Applications and Check Device Status

| Goal | Example request |
| --- | --- |
| Launch an application | “Open the browser.” |
| Close an application | “Close the calculator.” |
| View system information | “Show system information.” |
| View network status | “Show wired network status.” |
| View the device address | “Show the wired network IP address.” |
| Lock the screen | “Lock the screen.” |

Applications must be installed and discoverable by the system. Missing applications, multiple candidates, or unclear targets may require more information or further cloud processing.

### 2.3 Time, Language, and Region

| Goal | Example request |
| --- | --- |
| Check time | “Show the current system time.” |
| Set time only | “Set the system time to 15:30.” |
| Set date only | “Set the system date to 2026-11-03.” |
| Set date and time | “Set the system time to 2026-11-03 15:30:00.” |
| Check language and region | “Show the system language and region.” |
| List options | “List available languages and regions.” |
| Change interface language | “Change the system language to English.” |
| Switch back to Chinese | “Change the system language to Simplified Chinese.” |

Notes:

- Setting time changes the actual system clock; it does not create a reminder or alarm. Do not use the example date as if it were the current date.
- Setting only a date preserves the hours, minutes, and seconds at execution; setting only a time preserves the date at execution. Omitted seconds become 00. The time zone is unchanged.
- If automatic time synchronization is on, follow the on-screen prompt to confirm whether to turn it off before continuing. Do not proceed without confirmation.
- Confirmation options may differ depending on how you access BiBit. In the tested CLI version, a confirmation prompt may not appear, and the request may time out and be canceled. If you don’t see a confirmation option, don’t assume the change succeeded because you waited or the response ended. Cancel the request, then use a visible confirmation option in the desktop interface or change the setting in your system’s date and time settings.
- Supported system interface languages are currently Simplified Chinese and English. Region options depend on installed configurations; it is recommended that you list them before choosing.
- Language and region changes apply system-wide and usually need a logout and login to take full effect. Save your work first.

### 2.4 Find Files, Open Folders, and Set Wallpaper

| Goal | Example request |
| --- | --- |
| Find a local file | “Find meeting minutes on this computer.” |
| Open a common folder | “Open the Downloads folder.” |
| Set a particular wallpaper | “Set /home/bianbu/Pictures/wallpaper.jpg as the wallpaper.” |

Replace example paths with paths that actually exist on your device.

Finding a file and summarizing its contents are different tasks. BiBit can search for a file locally, while summarizing it usually requires the cloud to understand its contents and generate a response.

Wallpaper changes require an explicit local image path. “Change the wallpaper” does not automatically rotate to the next image or select and download one online. Provide an image location if missing.

## 3. Requests Usually Sent to the Cloud

### 3.1 Knowledge, Explanations, and Advice

- “What is a firewall?”
- “Why is there no sound?”
- “Help me analyze why the network is slow.”
- “Recommend video editing software for this device.”
- “What can you help me do?”

These requests need explanation or judgment rather than immediate device changes. The cloud may first read device information, then offer advice or suggest a next action.

### 3.2 Writing, Summarizing, Translation, and Programming

- “Write a meeting notice.”
- “Summarize the three key points of this document.”
- “Translate the following passage into English.”
- “Write a script to organize photos.”

Cloud models usually process these requests. Check files and screenshots for sensitive information you do not intend to submit.

“This document” needs an explicit source: upload the attachment, provide its actual file path, or paste its contents. Translation also requires source text. Do not assume a new session inherits material from another session. If a reply refers to a screenshot or document you did not provide for this request, check the source before relying on the summary.

### 3.3 Web Searches and Complex Tasks

- “Search the web for information about RISC-V.”
- “Research the topic, compare several options, and write a report.”
- “An application will not open. Find the cause and fix it.”
- “If the network is working, download the file; otherwise, diagnose the network.”

Multiple operations, conditions, and uncertain solutions usually require cloud coordination. Actual searching, downloading, or repairs depend on the assistant's tools and permissions.

Multiple items in one sentence do not always require the cloud. Supported fixed workflows and some directly combinable read-only queries can also run locally.

### 3.4 Context-dependent, Ambiguous, or Locally Unsupported Requests

- “Turn it off.”
- “Restore the previous setting.”
- “Change the time.”
- “Open that application.”

These may lack a target or value, or depend on earlier context. They usually go to the cloud for interpretation or a follow-up question.

**Cloud processing does not guarantee that your intent can be guessed.** You may still need to provide more information.

## 4. Why the Same Topic Can Use Different Processing

The topic matters, but so does what you want BiBit to do.

| Local operation request | Request usually needing the cloud | Difference |
| --- | --- | --- |
| “Set the volume to 30%.” | “Why is there no sound?” | Direct setting versus cause analysis |
| “Show the current system time.” | “Explain time zones.” | Read device data versus explain a concept |
| “Open the browser.” | “Open the browser, research the topic, and write a report.” | One action versus a complex task |
| “Find meeting minutes on this computer.” | “Summarize the minutes and list action items.” | Find a file versus understand its contents |
| “Change the system language to English.” | “What are the advantages and disadvantages of English and Chinese interfaces?” | Change a setting versus compare options |

The current implementation treats “Can you open the browser?” as a polite action request and launches the browser. A question mark does not mean “explain only, do not execute.” To ask about capabilities, explicitly say “Describe the feature only; do not perform any action.” Specify the action and target when you want BiBit to operate the device.

## 5. Phrase Requests for Better Results

1. **State the action and target.** Say “Turn the system volume up a little,” rather than just “A little more.”
2. **Give exact values when possible.** Say “Set brightness to 60%,” rather than “Use a suitable brightness.”
3. **Use specific paths, application names, and targets.** Use actual image paths and explicit application names, and reduce references such as “it” or “that one.”
4. **Send different tasks separately when helpful.** Opening the browser first and requesting a search afterward makes results easier to check. Searching and report generation may still need the cloud.
5. **Do not force complex goals into local commands.** Describe the full goal and let the cloud coordinate it. Respond to approval or clarification prompts as needed.
6. **Check results instead of repeatedly sending requests.** Review prompts when an operation is running, awaiting authorization, or unconfirmed to avoid duplicate actions.

## 6. Confirmation, Permissions, and Results

If an operation requires confirmation, BiBit asks you to confirm it regardless of whether the request is handled locally or in the cloud.

- Changes to system settings or closing applications may affect work in progress. Save your files first.
- When authorization is required, enter your password in a trusted system dialog—not in the chat.
- Before confirming, check the operation and its target carefully.
- If an operation is canceled, fails, times out, or is denied due to insufficient permissions, do not assume it was completed. If the result is unclear, check the actual device state.
- Some operations take longer than others. A wait does not necessarily mean intent recognition or the cloud response is slow.

### Known Limitations and Checking Results

These issues may occur in some versions.

- **The “✓ 已完成” (“Completed”) message alone does not confirm success.** It may also appear when a tool fails or does not finish. Check the actual device state.
- **Sentence-ending punctuation does not affect the verified routing of local queries and relative adjustments.** The Chinese requests “查看当前音量。”, “查看当前屏幕亮度。”, “把系统音量调大一点。”, and “把屏幕亮度调高一点。” were recognized correctly on the device tested. These mean “Show the current volume,” “Show the current screen brightness,” “Turn the system volume up a little,” and “Turn the screen brightness up a little,” respectively. Chinese or English punctuation at the end, such as `。`, `.`, `！`, `!`, `？`, or `?`, can be left in place. If a request does not work as expected, include the original wording and punctuation when reporting the issue.
- **Completing one step does not mean the whole task is complete.** Ask about the remaining steps until you see the final result.
- **Application startup detection may be delayed.** If BiBit says it could not detect an application but its window is already open, check the desktop before trying to launch it again.
- **Query results may include technical details.** The configuration fields shown in language and region results are not instructions to edit those settings manually. If the response is truncated or unclear, check the system settings and report the issue; do not change the configuration based on incomplete information.
- **A network diagnostic timeout does not identify a fault.** An incomplete traceroute alone cannot establish that the network is down or explain why it is slow. If the entire diagnostic fails, keep the results and error messages already shown; do not assume that steps not shown were completed.

## 7. Frequently Asked Questions

### Does Local Processing Work Without a Network?

Some device controls work offline when local services are healthy. Local-first does not guarantee that every feature works offline. Features may depend on installed models, device services, or network resources. Cloud interpretation and web searches require the appropriate service and network connections.

### Where Do Device Operations Run after Cloud Processing?

The cloud interprets or plans the task, but operations on your device are still carried out using local tools and are subject to local permissions and confirmation requirements.

### Does a Local Request Guarantee That Nothing Is Uploaded?

No. A local operation does not prove that the entire conversation stays off the cloud. Local routing describes request handling, not a product-wide data transmission guarantee. Cloud requests may include messages, attachments, or device information needed for the task. Refer to the current privacy notice and service configuration.

### What If My Request Is Not Recognized?

Use a clear action, clear target, and necessary parameters. For example, replace “Adjust it” with “Set the system volume to 30%.” If it still fails, preserve the original wording and interface message when reporting it. Avoid repeatedly sending operations that could change system state.

### Does Sending a Request to the Cloud Guarantee Completion?

No. Cloud processing still depends on tools, permissions, network access, and device support. Follow prompts to provide information or approval, or perform the action manually. Generated text is not proof that an operation succeeded.

---

For more interface instructions, see the [BiBit User Guide](index.md).
