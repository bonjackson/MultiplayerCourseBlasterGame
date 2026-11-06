# Multiplayer Course Blaster — UE 5.8

本项目以 [DruidMech/MultiplayerCourseBlasterGame](https://github.com/DruidMech/MultiplayerCourseBlasterGame) 的首次提交 [`0bf44af`](https://github.com/DruidMech/MultiplayerCourseBlasterGame/commit/0bf44af786597adfc5a11c69e3ca0954a3d9a158) 为起点，适配 Unreal Engine 5.8。它是课程的起始状态，不包含最终版游戏。

## 首次提交内容

原提交 `Project Creation`（2022-02-11）包含 Blaster C++ 工程和空的 GameMode、项目配置，以及 MultiplayerSessions 插件：Steam 在线会话的创建、查找、加入、销毁和启动，菜单 C++ 类及 WBP_Menu 资源。原提交指定的启动地图和默认 Lobby 地图并未包含在提交中；角色、武器等游戏资产也不在这一提交中。

## UE 5.8 调整和启动

- 工程关联 UE 5.8，两个目标使用 V7 构建设置与 5.8 头文件顺序。
- 菜单清理使用 NativeDestruct，焦点在构造时设置；会话查找使用 UE 5.8 的 SEARCH_LOBBIES，并启用 Steam lobby。
- 缺失的启动地图临时改用引擎自带的地图。默认 Lobby 路径仍需要在创建菜单时指定实际存在的地图。
- 安装 UE 5.8、Visual Studio C++ 工具链及 Windows SDK，打开 `Blaster.uproject` 并按提示构建。Steam 联机需要运行 Steam，使用配置中的测试 App ID 480，并以多个客户端验证。

## 原仓库开发步骤（按提交历史归纳）

1. 创建项目与会话插件；测试在线会话，导入资产、重定向骨骼动画。
2. 创建角色、摄像机、移动和动画蓝图，搭建大厅和无缝切换。
3. 学习网络角色、属性复制和 RPC；实现武器拾取、装备、瞄准、动画和开火。
4. 增加投射物、碰撞、弹壳、准星 HUD；实现生命、伤害、淘汰、重生及积分。
5. 增加弹药、换弹、比赛计时、服务器时间同步和比赛状态。
6. 扩展火箭、射线枪、霰弹枪、狙击枪和手榴弹；加入拾取物、增益、护盾和武器切换。
7. 优化高延迟体验、客户端预测与服务器回溯；实现菜单退出、玩家统计和击杀公告。
8. 添加团队、友伤规则、团队计分和夺旗模式，选择比赛类型及地图；后续修复并更新资源。

上面的阶段由源仓库提交标题归纳，具体实现与资产请参考其提交历史。原仓库未提供明确的许可证文件；使用课程资产及代码前请确认相应授权。
