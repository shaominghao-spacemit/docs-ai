---
sidebar_position: 9
---

# BiBit Local Tool List

This page lists BiBit device tools by purpose for general users. You do not need to enter tool names; describe what you want to do. Tool names help identify features when reporting problems.

## 1. How to Read This List

- The tools listed here run on your device, but BiBit may need the cloud to interpret your request. Operations such as downloading software or looking up information online still require a network connection.
- A listing does not mean the tool is enabled. Check which features are available on your device.
- **Distinguish queries from changes.** System changes, software installation, and deletion may require confirmation or authorization. Neither local nor cloud processing replaces your approval.
- **Adapt examples to your situation.** Replace applications, paths, packages, and device identifiers with actual values. Do not test features by formatting storage or deleting users.

The following sections cover basic and extended tools. Knowledge sources and code tasks are described separately because they are not purely local offline capabilities.

## 2. Desktop and Device Control

Common operations include volume, displays, applications, windows, time, language, file location, and wired networking.

- Wallpaper changes require an explicit local image path. They do not rotate wallpapers or select images online automatically.
- Supported system languages are currently Simplified Chinese and English. Regions depend on installed configurations. System-wide language and region changes usually require logging out and back in.
- Setting system time does not create a reminder. When automatic time synchronization is enabled, use an entry point that supports confirmation before disabling it. The tested CLI version may show no confirmation prompt; waiting or the end of a reply is not proof of success. Use a visible desktop confirmation control or system settings instead.
- Display modes, camera functions, and audio operations depend on hardware and desktop services.
- Batch application operations and interpreting file contents are not guaranteed to use local recognition alone. Save files before closing applications, restarting, or shutting down.

**Example requests:** “Set the volume to 30%.” “Show the current system time.” “Open the browser.” “Find meeting minutes on this computer.”

| Function | Tool name |
| --- | --- |
| Set a specified local image as wallpaper | `set_wallpaper` |
| Query system-wide language and region | `get_locale_settings` |
| List available languages and installed locales | `list_locale_options` |
| Change system-wide interface language | `set_system_language` |
| Change system-wide regional formats | `set_system_region` |
| Query system date, time, and time zone | `get_system_time` |
| Set system date, time, or both | `set_system_time` |
| Query volume | `get_vol_status` |
| Set volume | `set_volume` |
| Adjust volume | `adjust_volume` |
| Query brightness | `get_display_light` |
| Set screen brightness | `set_brightness` |
| Adjust screen brightness | `adjust_brightness` |
| Set screen resolution | `set_resolution` |
| Set screen refresh rate | `set_refresh_rate` |
| View supported display modes | `display_modes` |
| Rotate the screen | `rotate_screen` |
| Set screen scaling | `set_aspect_ratio` |
| Set external display mode | `set_display_mode` |
| Query windows and applications | `window_list` |
| Switch to or activate a window | `window_activate` |
| Minimize a window | `window_minimize` |
| Maximize a window | `window_maximize` |
| Mute or unmute | `mute` |
| Open the camera | `camera_open` |
| Take a photo | `take_photo` |
| Close the camera | `camera_close` |
| Take a screenshot | `screenshot` |
| Switch audio output device | `audio_output_switch` |
| Adjust input volume | `audio_input_volume` |
| Switch audio input device | `audio_input_switch` |
| Mute or unmute the input device | `audio_input_mute` |
| Query system status | `get_system_info` |
| Restart the device | `reboot` |
| Shut down | `shutdown` |
| Suspend or hibernate | `sleep` |
| Lock the screen | `lock_screen` |
| Launch an application | `launch_app` |
| Close an application | `close_app` |
| Close multiple applications | `close_apps` |
| Launch multiple applications | `launch_apps` |
| List launchable applications | `list_apps` |
| Search local files | `file_search` |
| Open a local file | `open_file` |
| Open a folder | `open_folder` |
| Enable a wired network interface | `eth_up` |
| Disable a wired network interface | `eth_down` |
| View wired network status | `eth_status` |
| View wired network IP addresses | `eth_ip` |

## 3. Wi-Fi and Bluetooth

These require compatible network and Bluetooth hardware and system services. Give a specific device name and select a target when there are several candidates. Disconnecting the network may interrupt cloud conversations. Do not send administrator passwords in chat; enter network credentials through trusted connection dialogs where possible.

**Example requests:** “Turn on Wi-Fi.” “Scan Wi-Fi networks.” “Show Wi-Fi connection status.” “Turn on Bluetooth.” “Scan Bluetooth devices.”

| Function | Tool name |
| --- | --- |
| Turn Wi-Fi on | `wifi_on` |
| Turn Wi-Fi off | `wifi_off` |
| Scan Wi-Fi networks | `wifi_scan` |
| Connect to Wi-Fi | `wifi_connect` |
| Disconnect Wi-Fi | `wifi_disconnect` |
| View Wi-Fi connection status | `wifi_status` |
| View Wi-Fi IP addresses | `wifi_ip` |
| Turn Bluetooth on | `bt_on` |
| Turn Bluetooth off | `bt_off` |
| Scan Bluetooth devices | `bt_scan` |
| Connect a Bluetooth device | `bt_connect` |
| Disconnect the current Bluetooth device | `bt_disconnect` |
| Change the Bluetooth received-files directory | `bt_set_recv_dir` |
| Forget or unpair a Bluetooth device | `bt_forget` |
| Connect a device with automatic domain selection | `connect_any` |

## 4. System Queries and Diagnostics

This includes system information, package queries, processes, storage, networking, and security checks. Although grouped as diagnostics, **resetting USB affects device connections, and backing up the package list writes a file**. Not every operation here is free of side effects.

External IP, domain, traceroute, and HTTP queries may access the network. Virus scanning requires installed scanning components and takes time depending on file counts and other factors. Unreadable files or scan errors prevent a conclusion that the entire directory is safe.

**Example requests:** “Show the system version.” “Show free disk space.” “Show the processes using the most memory.” “Show firewall rules.” “Scan /tmp for viruses.”

| Function | Tool name |
| --- | --- |
| Assess software delivery options for RISC-V, read-only | `software_delivery_assess` |
| Query one package's candidate version and architecture, read-only | `pkg_candidate` |
| Preview one package's installation or removal effects, read-only simulation without execution | `pkg_operation_preview` |
| Verify installation state and target version without launching the app, read-only | `pkg_verify` |
| Preview package pattern matches, read-only | `pkg_match_preview` |
| List files installed by a package | `pkg_files` |
| Search software repositories | `pkg_search` |
| View package information | `pkg_info` |
| List installed packages | `pkg_installed` |
| Find the package owning a file | `pkg_owns_file` |
| Query a package's dependencies | `pkg_depends` |
| Query reverse dependencies | `pkg_rdepends` |
| View a system overview | `sys_overview` |
| View kernel version | `sys_kernel` |
| View system version | `sys_version` |
| View PCI devices | `sys_pci` |
| Show the USB device tree | `usb_tree` |
| Show USB device details | `usb_detail` |
| Reset USB devices | `usb_reset` |
| List USB devices | `usb_list` |
| Show system uptime | `sys_uptime` |
| View free disk space | `disk_usage` |
| View directory disk usage | `disk_dir_usage` |
| View block devices and partitions | `disk_lsblk` |
| View current processes | `proc_list` |
| Show processes using the most memory | `proc_top_mem` |
| Show processes using the most CPU | `proc_top_cpu` |
| View the process tree | `proc_tree` |
| View IP and interface addresses | `net_ip` |
| View network connections and listening ports | `net_conn` |
| View service status | `service_status` |
| Query system update status | `system_update_status` |
| View login records | `login_records` |
| View currently logged-in users | `online_users` |
| View package statistics | `pkg_stats` |
| View the package download cache directory | `pkg_archives` |
| Back up the installed package list | `pkg_selections` |
| Check whether the system is 32-bit or 64-bit | `sys_arch` |
| View loaded kernel modules | `sys_modules` |
| View CPU details | `sys_cpu` |
| Show hardware information | `sys_hw` |
| View the memory module model | `sys_mem_type` |
| Show current memory size | `sys_mem_size` |
| View system limits | `sys_limits` |
| View kernel limits | `sys_kernel_limits` |
| View screen resolution | `sys_resolution` |
| View disk partitions | `disk_partitions` |
| View disk details | `disk_info` |
| View disk I/O | `disk_io` |
| View software RAID arrays | `disk_raid` |
| View current memory usage | `proc_mem` |
| Summarize memory usage by program | `proc_mem_stat` |
| View files opened by a process | `proc_open_files` |
| Identify the process using a port | `proc_port` |
| View routing information | `net_route` |
| View interface MAC addresses | `net_mac` |
| View the external IP address | `net_ext_ip` |
| Query domain WHOIS information | `net_whois` |
| Trace a network route | `net_trace` |
| View HTTP response headers | `net_http_head` |
| Diagnose local networking | `net_diagnose` |
| View iptables rules | `iptables_list` |
| View login information for all accounts | `sec_lastlog` |
| Scan for viruses | `sec_antivirus` |
| View all service statuses | `service_list` |
| List system users | `user_list` |
| Inspect file type | `file_info` |
| Inspect text encoding | `text_encoding` |

## 5. Software Installation and System Administration

These tools can change the system, files, or accounts. Check targets and impacts and authorize as prompted. Installation and updates may download files and depend on software repositories and architecture support.

**Formatting destroys data on the target partition. Deleting users, terminating processes, stopping services, and changing firewall rules may cause data loss, service interruption, or disconnection.** Ordinary users should not use these as test commands. Follow actual permission, confirmation, and result prompts.

Generate and review a dependency installation plan before applying it. A package query or successful preview does not mean installation is complete.

**Example requests:** “Install the hello package.” Separate “Check it before deciding whether to install” into query and confirmation steps. Do not execute administration operations you do not understand.

| Function | Tool name |
| --- | --- |
| Install software, apt/deb system packages only | `pkg_install` |
| Remove software, apt/deb system packages only | `pkg_remove` |
| Install a Python package | `pip_install` |
| Uninstall a Python package | `pip_uninstall` |
| Install a Node package | `npm_install` |
| Uninstall a Node package | `npm_uninstall` |
| Install a local package | `install_local` |
| Apply a dependency installation plan, confirmation required | `dep_apply` |
| Update the system | `pkg_update` |
| Clean the package cache | `pkg_clean` |
| Remove orphaned packages | `pkg_autoremove` |
| Restore package selections from a backup | `pkg_restore_selections` |
| Mount a partition | `disk_mount` |
| Unmount a partition | `disk_umount` |
| Check a disk | `disk_check` |
| Format a partition | `disk_format` |
| Terminate a process | `proc_kill` |
| Clean up zombie processes | `proc_zombie` |
| Restart a service | `service_restart` |
| Stop a service | `service_stop` |
| Start a service | `service_start` |
| Add a user | `user_add` |
| Delete a user | `user_del` |
| Lock a user | `user_lock` |
| Unlock a user | `user_unlock` |
| Block an IP address | `iptables_block` |
| Enable NAT | `net_enable_nat` |
| Convert text encoding | `text_convert` |

## 6. Scheduled Reminders

These need the device's scheduling service. Give a clear title and time when creating a reminder, and identify the target when changing or deleting one. Confirm the target if several share a name. Reminders and system clock changes are different features.

**Example requests:** “Remind me to drink water in 10 minutes.” “Show scheduled reminders.”

| Function | Tool name |
| --- | --- |
| Create a reminder | `schedule_add` |
| Update a reminder | `schedule_update` |
| Delete a reminder | `schedule_remove` |
| List reminders | `schedule_list` |

## 7. File Reading and Office Templates

Summarizing and writing usually require cloud processing. Before submitting content, check it for sensitive information.

**Example request:** “List office templates.” Provide an explicit local path when requesting a file read.

| Function | Tool name |
| --- | --- |
| Read a local file, read-only | `file_read` |
| List office templates, read-only | `template_list` |
| Retrieve an office template skeleton, read-only | `template_get` |

## 8. Application Extensions and Output Checks

Typically, BiBit checks which capabilities are available before the assistant coordinates the calls. Application commands may change files, so review and confirm the operation before running them.

**Example request:** “List available application command lines.”

| Function | Tool name |
| --- | --- |
| List application command lines, read-only | `appcli_list` |
| Run an application command line | `appcli_run` |
| Verify output files, read-only | `appcli_verify` |

## 9. Development Project Dependencies

Primarily for developers: scan projects, identify missing dependencies, generate installation plans, and verify state. A plan does not install anything. Applying it uses `dep_apply` from this list and requires confirmation.

**Example guidance:** Give the actual project directory and specify “Check first; do not install.”

| Function | Tool name |
| --- | --- |
| Scan project dependencies, read-only | `dep_scan` |
| View missing dependencies, read-only | `dep_status` |
| Generate an installation plan, read-only dry run | `dep_plan` |
| Verify installed dependencies, read-only | `dep_verify` |
| View dependency installation history, read-only | `dep_history` |
| Report missing dependencies after writing a file, read-only, no installation | `dep_notice` |

## 10. Extensions Requiring Networking or Additional Execution Environments

BiBit also provides the following tools, but they are not purely local offline features:

- Knowledge source lists show configured sources. Cloud retrieval requires user-enabled sources and sends queries to the configured service.
- Code tasks require an additional execution environment coordinated by the assistant. They do not mean a small on-device model can directly complete arbitrary programming tasks. Network use also depends on that environment's configuration.
- These features are unavailable without configured sources or required components.

**Example requests:** “Show cloud knowledge sources.” “Search the cloud knowledge base for installation instructions.”

| Function | Tool name |
| --- | --- |
| View cloud knowledge sources, read-only | `kb_sources` |
| Search cloud knowledge sources, read-only, requires user-enabled sources | `kb_search` |
| Execute a code task through dsh | `code_task` |

## 11. If a Tool Cannot Be Used

1. Check whether the problem is an unclear target, a disabled feature, a missing component, insufficient permissions, or an execution failure.
2. Provide accurate application names, file paths, device names, or parameters. Do not send passwords in chat.
3. Review operations before confirming. After a timeout or unclear result, query actual state instead of repeating change commands.
4. Report the original wording, relevant tool names, and error messages without passwords or other sensitive information.

Tools change with product updates. Available functions may vary; follow the current interface and actual execution results.
