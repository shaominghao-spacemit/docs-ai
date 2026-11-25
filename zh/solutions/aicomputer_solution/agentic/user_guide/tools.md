---
sidebar_position: 9
---

# BiBit 本地工具列表

本文面向普通用户，按用途列出 BiBit 的设备工具。你不需要输入工具名称，直接描述想做的事情即可；工具名称用于反馈问题时准确定位功能。

## 1. 如何阅读这份清单

- 清单中的工具由本地执行，但理解你的请求可能需要云端；下载软件、查询外网等操作仍需联网。
- 实际可用性以当前设备提供的功能为准，清单项不代表已启用。
- **查询和修改要分清。** 修改系统、安装软件、删除数据等操作可能需要确认或授权；云端和本地都不能代替用户授权。
- **按实际情况使用示例。** 应用、路径、包名和设备标识需要替换为实际值。不要为了试用而执行格式化、删除用户等高风险操作。

下方列出基础工具及扩展工具；最后单独说明知识源与代码任务，避免将它们误认为纯本地离线能力。

## 2. 桌面与设备控制

包含音量、屏幕、应用、窗口、时间、语言、文件定位与有线网络等常用操作。

- 设置壁纸必须提供明确的本地图片路径，不会自动轮换或从网络挑选图片。
- 系统语言目前支持简体中文和英文；区域按设备已安装的配置选择。修改全局语言与区域通常需要注销后重新登录。
- 设置系统时间不是创建提醒。自动校时开启时，需先在支持确认交互的入口确认关闭自动校时。已检查的 CLI 版本可能不显示确认提示；此时不要把等待或回复结束当作成功，请改用桌面中可见的确认入口或系统设置。
- 显示模式、相机及音频操作受硬件和桌面服务支持情况限制。
- 批量打开或关闭应用、读取文件后的进一步理解等，不保证仅靠本地识别完成。关闭应用、重启或关机前先保存文件。

**说法示例：** “把音量设置为30%。”“查看当前系统时间。”“打开浏览器。”“在本机查找会议纪要。”

| 功能 | 工具名称 |
| --- | --- |
| 将指定的本地图片设为桌面壁纸 | `set_wallpaper` |
| 查询系统全局语言与区域 | `get_locale_settings` |
| 列出可用语言和已安装的区域配置 | `list_locale_options` |
| 修改系统全局界面语言 | `set_system_language` |
| 修改系统全局区域格式 | `set_system_region` |
| 查询系统日期、时间与时区 | `get_system_time` |
| 设置系统日期、时间或两者 | `set_system_time` |
| 查询音量 | `get_vol_status` |
| 设置音量 | `set_volume` |
| 调节音量 | `adjust_volume` |
| 查询亮度 | `get_display_light` |
| 设置屏幕亮度 | `set_brightness` |
| 调节屏幕亮度 | `adjust_brightness` |
| 设置屏幕分辨率 | `set_resolution` |
| 设置屏幕刷新率 | `set_refresh_rate` |
| 查看屏幕支持的显示模式 | `display_modes` |
| 旋转屏幕 | `rotate_screen` |
| 设置屏幕缩放比例 | `set_aspect_ratio` |
| 设置外接屏显示模式 | `set_display_mode` |
| 查询窗口/应用列表 | `window_list` |
| 切换/激活窗口 | `window_activate` |
| 最小化窗口 | `window_minimize` |
| 最大化窗口 | `window_maximize` |
| 静音/取消静音 | `mute` |
| 打开相机 | `camera_open` |
| 拍照 | `take_photo` |
| 关闭相机 | `camera_close` |
| 截图 | `screenshot` |
| 切换音频输出设备 | `audio_output_switch` |
| 调节输入音量 | `audio_input_volume` |
| 切换音频输入设备 | `audio_input_switch` |
| 输入设备静音/取消静音 | `audio_input_mute` |
| 查询系统状态 | `get_system_info` |
| 重启设备 | `reboot` |
| 关机 | `shutdown` |
| 睡眠/休眠 | `sleep` |
| 锁屏 | `lock_screen` |
| 启动应用 | `launch_app` |
| 关闭应用 | `close_app` |
| 批量关闭应用 | `close_apps` |
| 批量启动应用 | `launch_apps` |
| 列出可启动的应用 | `list_apps` |
| 本地搜索文件 | `file_search` |
| 打开本地文件 | `open_file` |
| 打开文件夹 | `open_folder` |
| 启用有线网卡 | `eth_up` |
| 禁用有线网卡 | `eth_down` |
| 查看有线网络状态 | `eth_status` |
| 查看有线网络 IP | `eth_ip` |

## 3. Wi-Fi 与蓝牙

需要对应网卡、蓝牙设备和系统服务支持。连接设备时应提供明确名称，出现多个候选时先选择目标。断开网络可能中断云端会话；不要在普通聊天中发送管理员密码，网络凭据优先按可信连接界面提示填写。

**说法示例：** “打开Wi-Fi。”“扫描Wi-Fi网络。”“查看Wi-Fi连接状态。”“打开蓝牙。”“扫描蓝牙设备。”

| 功能 | 工具名称 |
| --- | --- |
| 打开 WiFi | `wifi_on` |
| 关闭 WiFi | `wifi_off` |
| 扫描 WiFi 网络 | `wifi_scan` |
| 连接 WiFi | `wifi_connect` |
| 断开 WiFi | `wifi_disconnect` |
| WiFi 连接状态 | `wifi_status` |
| 查看 WiFi IP 地址 | `wifi_ip` |
| 打开蓝牙 | `bt_on` |
| 关闭蓝牙 | `bt_off` |
| 扫描蓝牙设备 | `bt_scan` |
| 连接蓝牙设备 | `bt_connect` |
| 断开当前蓝牙设备 | `bt_disconnect` |
| 切换蓝牙文件接收目录 | `bt_set_recv_dir` |
| 忽略蓝牙设备（取消配对） | `bt_forget` |
| 连接设备（自动判域） | `connect_any` |

## 4. 系统查询与诊断

包含系统信息、软件包查询、进程、存储、网络和安全检查。虽然放在查询与诊断分类中，**重置 USB 会影响设备连接，备份包列表会写入文件**，不能将本节一概视为无副作用。

外网 IP、域名查询、路由跟踪和 HTTP 查询可能访问网络。病毒扫描需要已安装扫描组件，耗时取决于文件数量等因素；如果存在无法读取的文件或扫描错误，不能据此认定整个目录安全。

**说法示例：** “查看系统版本。”“查看硬盘剩余空间。”“查看内存占用最高的进程。”“查看当前系统的防火墙规则。”“对/tmp目录进行一次病毒扫描。”

| 功能 | 工具名称 |
| --- | --- |
| 评估软件交付路径（RISC-V只读） | `software_delivery_assess` |
| 查询单包候选版本与架构（只读） | `pkg_candidate` |
| 单包安装卸载影响预检（只读模拟，不执行） | `pkg_operation_preview` |
| 核验软件包安装状态与目标版本（只读，不启动应用） | `pkg_verify` |
| 软件包模式只读预览 | `pkg_match_preview` |
| 查看软件包安装了哪些文件 | `pkg_files` |
| 搜索软件库中的软件 | `pkg_search` |
| 查看软件包信息 | `pkg_info` |
| 查看已安装的软件包列表 | `pkg_installed` |
| 查找文件属于哪个软件包 | `pkg_owns_file` |
| 查询软件包依赖哪些包 | `pkg_depends` |
| 查询软件包被哪些包依赖 | `pkg_rdepends` |
| 查看系统概览 | `sys_overview` |
| 查看内核版本 | `sys_kernel` |
| 查看系统版本 | `sys_version` |
| 查看 PCI 设备 | `sys_pci` |
| 显示 USB 设备树 | `usb_tree` |
| 显示 USB 设备详细信息 | `usb_detail` |
| 重置 USB 设备 | `usb_reset` |
| 查看 USB 设备 | `usb_list` |
| 显示系统运行时间 | `sys_uptime` |
| 查看硬盘剩余空间 | `disk_usage` |
| 查看目录占用空间 | `disk_dir_usage` |
| 查看块设备/分区 | `disk_lsblk` |
| 查看当前进程 | `proc_list` |
| 内存占用最高的进程 | `proc_top_mem` |
| CPU 占用最高的进程 | `proc_top_cpu` |
| 查看进程树 | `proc_tree` |
| 查看 IP/网卡地址 | `net_ip` |
| 查看网络连接/监听端口 | `net_conn` |
| 查看服务状态 | `service_status` |
| 查询系统更新状态 | `system_update_status` |
| 查看登录记录 | `login_records` |
| 查看当前在线用户 | `online_users` |
| 系统安装包统计信息 | `pkg_stats` |
| 查看下载缓存目录 | `pkg_archives` |
| 备份当前已安装包列表 | `pkg_selections` |
| 查看系统32/64位 | `sys_arch` |
| 查看内核加载的模块 | `sys_modules` |
| 查看 CPU 详细信息 | `sys_cpu` |
| 显示硬件信息 | `sys_hw` |
| 查看内存型号 | `sys_mem_type` |
| 显示当前内存大小 | `sys_mem_size` |
| 查看系统限制 | `sys_limits` |
| 查看内核限制 | `sys_kernel_limits` |
| 查看屏幕分辨率 | `sys_resolution` |
| 查看硬盘分区 | `disk_partitions` |
| 查看硬盘详细信息 | `disk_info` |
| 查看硬盘读写情况 | `disk_io` |
| 查看软 raid 阵列 | `disk_raid` |
| 查看当前内存使用 | `proc_mem` |
| 统计各程序内存耗用 | `proc_mem_stat` |
| 查看进程打开的文件 | `proc_open_files` |
| 查看端口被哪个程序占用 | `proc_port` |
| 查看路由信息 | `net_route` |
| 查看网卡 MAC 地址 | `net_mac` |
| 查看外网 IP | `net_ext_ip` |
| 域名 whois 查询 | `net_whois` |
| 路由跟踪 | `net_trace` |
| 查看 HTTP 响应头 | `net_http_head` |
| 本地网络诊断 | `net_diagnose` |
| 查看 iptables 规则 | `iptables_list` |
| 查看所有账号登录情况 | `sec_lastlog` |
| 病毒扫描 | `sec_antivirus` |
| 查看全部服务状态 | `service_list` |
| 查看系统用户 | `user_list` |
| 察看文件类型信息 | `file_info` |
| 察看文件编码 | `text_encoding` |

## 5. 软件安装与系统管理

这些工具可能修改系统、文件或账户。请确认目标和影响，按界面要求授权；安装和更新还可能联网下载，并受软件源与目标架构支持限制。

**格式化会破坏目标分区的数据；删除用户、终止进程、停止服务及修改防火墙可能造成数据丢失、业务中断或连接断开。** 不建议普通用户将这些功能作为试用指令。权限、确认和执行结果以界面实际提示为准。

依赖安装应先生成并查看计划；不要把软件查询结果或预检通过当作安装已经完成。

**说法示例：** “安装软件包 hello。”“查看之后再决定是否安装”应分成查询与确认步骤，不要直接执行不理解的管理操作。

| 功能 | 工具名称 |
| --- | --- |
| 安装软件（仅 apt/deb 系统包） | `pkg_install` |
| 卸载软件（仅 apt/deb 系统包） | `pkg_remove` |
| 安装 Python 包 | `pip_install` |
| 卸载 Python 包 | `pip_uninstall` |
| 安装 Node 包 | `npm_install` |
| 卸载 Node 包 | `npm_uninstall` |
| 本地安装软件包 | `install_local` |
| 按依赖计划安装（需确认） | `dep_apply` |
| 系统更新 | `pkg_update` |
| 清理软件缓存 | `pkg_clean` |
| 删除孤立软件 | `pkg_autoremove` |
| 从备份恢复包列表 | `pkg_restore_selections` |
| 挂载分区 | `disk_mount` |
| 卸载分区 | `disk_umount` |
| 硬盘检查 | `disk_check` |
| 格式化分区 | `disk_format` |
| 中止进程 | `proc_kill` |
| 清除僵尸进程 | `proc_zombie` |
| 重启服务 | `service_restart` |
| 停止服务 | `service_stop` |
| 启动服务 | `service_start` |
| 增加用户 | `user_add` |
| 删除用户 | `user_del` |
| 锁定用户 | `user_lock` |
| 解锁用户 | `user_unlock` |
| 阻止一个 IP | `iptables_block` |
| 让网络支持 NAT | `net_enable_nat` |
| 转换文件编码 | `text_convert` |

## 6. 日程提醒

需要设备上的日程服务。创建提醒时说清标题和时间；修改或删除时明确目标提醒，多个同名项目应先确认。提醒与修改系统时钟是不同功能。

**说法示例：** “10分钟后提醒我喝水。”“查看日程提醒。”

| 功能 | 工具名称 |
| --- | --- |
| 创建日程提醒 | `schedule_add` |
| 修改日程提醒 | `schedule_update` |
| 删除日程提醒 | `schedule_remove` |
| 查看日程提醒 | `schedule_list` |

## 7. 文件读取与办公模板

总结、写作等通常需要云端；提交前检查内容是否含有敏感信息。

**说法示例：** “列出办公模板。”需要读取文件时提供明确的本地路径。

| 功能 | 工具名称 |
| --- | --- |
| 读取本地文件（只读） | `file_read` |
| 列出办公模板（只读） | `template_list` |
| 取办公模板骨架（只读） | `template_get` |

## 8. 应用扩展与产出物检查

通常先查询可用能力，再由助手组织调用。执行应用命令可能修改文件，请确认后再操作。

**说法示例：** “列出可用的应用命令行。”

| 功能 | 工具名称 |
| --- | --- |
| 列出应用命令行（只读） | `appcli_list` |
| 执行应用命令行 | `appcli_run` |
| 复核产出物文件（只读） | `appcli_verify` |

## 9. 开发项目依赖检查

主要面向开发者：扫描项目、查看缺失依赖、生成安装计划并核验状态。生成计划不会直接安装，实际安装使用本清单中的 `dep_apply`，需要确认。

**说法示例：** 请求检查依赖时，提供项目的实际目录，并明确“先检查，不安装”。

| 功能 | 工具名称 |
| --- | --- |
| 扫描项目依赖（只读） | `dep_scan` |
| 查看依赖缺失情况（只读） | `dep_status` |
| 生成依赖安装计划（只读，干跑） | `dep_plan` |
| 验证依赖是否装好（只读） | `dep_verify` |
| 查看依赖安装记录（只读） | `dep_history` |
| 写下文件后提醒缺失依赖（只读，不安装） | `dep_notice` |

## 10. 需要联网或额外执行环境的扩展

以下工具也由 BiBit 提供，但不能视为纯本地离线功能：

- 知识源列表用于查看已配置的来源；云端知识检索需要用户启用来源，会把查询内容发送到配置的服务。
- 代码任务需要额外的代码执行环境，由助手协调处理，不能等同于端侧小模型直接完成任意编程任务；是否联网还取决于执行环境配置。
- 未配置知识源或未安装所需组件时，相应能力不可用。

**说法示例：** “查看云端知识源列表。”“在云端知识库搜索安装方法。”

| 功能 | 工具名称 |
| --- | --- |
| 查看云端知识源（只读） | `kb_sources` |
| 检索云端知识源（只读，需用户启用） | `kb_search` |
| 执行代码任务（由 dsh 完成） | `code_task` |

## 11. 工具不能使用时怎么办

1. 查看提示是目标不明确、功能未启用、缺少组件、权限不足还是执行失败。
2. 补充准确的应用名、文件路径、设备名称或参数；不要把密码发到聊天中。
3. 需要确认时看清操作内容。发生超时或结果不明确时，先查询实际状态，不要反复发送修改指令。
4. 反馈问题时提供原始说法、相关工具名称和错误提示，避免包含密码及其他敏感信息。

工具会随版本更新，可用范围可能变化，请以当前设备界面和执行结果为准。
