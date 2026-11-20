# zongyunfwx · AI 算法工程作品集

使用原生 HTML、CSS、JavaScript 的静态个人网站，聚焦自动驾驶、VLA、机器人导航和深度学习。无需安装前端依赖，无后端、数据库或付费服务。字体、插图和样式均从本站加载。

## 文件结构

改造前仓库只有根目录的 `index.html` 和 `README.md`，没有构建配置或 GitHub Actions 工作流。改造后继续以根目录作为静态网站入口：

```text
.
├── index.html                         # 首页：介绍、技能、项目、联系
├── assets/
│   ├── style.css                      # 共享样式、响应式布局与减少动态效果设置
│   ├── main.js                        # 手机菜单、项目筛选与年份
│   ├── aerovla/                        # 原项目插图、来源与许可证
│   ├── favicon.svg
│   ├── autonomy.svg                   # 自动驾驶概念图
│   ├── vla.svg                        # 视觉语言动作概念图
│   ├── navigation.svg                 # 路径规划概念图
│   └── learning.svg                   # 网络与训练曲线概念图
├── projects/                          # 21 个独立项目详情页
│   ├── autonomous-driving.html         # 自动驾驶决策规划
│   ├── robot-navigation.html           # 世界模型 / Waypoint 导航
│   ├── vision-language-action.html     # VLM 微调 / Action 导航
│   ├── aerovla.html                    # 无人机 VLA 复现
│   └── ...                            # 其余项目按语义化文件名组织
└── README.md
```

首页按 `docs/项目汇总.md` 顺序展示 21 个项目，支持 7 个技术方向筛选，补充展示人脸识别、CAN/CANopen 和远程桌面实践。详情页包含技术实践及图片或视频，并提供前后项目与首页入口。图片与视频位于 `assets/<项目名>/demo.*`。所有页面均为真实静态 HTML 文件，支持直接访问与刷新；关闭 JavaScript 仍可浏览完整内容。

## 本地预览

在 PowerShell 中进入仓库并运行（需要 Python 3）：

```powershell
cd D:\Github_clone\zongyunfwx.github.io
python -m http.server 8000 --bind 127.0.0.1
```

浏览器打开 **http://127.0.0.1:8000/**。按 `Ctrl+C` 停止；端口被占用时可换成 `8001`。修改文件后刷新页面即可看到更新。也可以直接双击 `index.html` 查看基本页面，建议通过 HTTP 服务检查链接与详情页。

## GitHub Pages

保留现有 GitHub Pages 部署方式和根目录 `index.html` 入口；没有新增构建步骤、工作流、Sites 托管配置或其他托管服务。无需运行 npm 或生成 `dist`。仓库中没有可供核实的 Pages 远程设置文件，因此本次未更改 GitHub 后台的分支或目录设置。

后续由你自行检查改动并提交、推送到原 Pages 发布分支，沿用已有发布流程即可。本次修改不会自动提交或推送。

## 替换为真实个人资料

- `index.html`：修改显示名称、个人介绍、技术方向，以及首页项目摘要。
- 联系方式：GitHub 使用 `zongyunfwx` 账号；联系电话来自项目汇总文档。
- `projects/*.html`：内容和实验数字来自 `docs/项目汇总.md`，按原描述保留任务、基线与指标含义；医学问答项目的 100% 指推理与答案标签完整率。
- `projects/aerovla.html`：保留开源项目复现角色和原项目链接。
- `docs/`：本地原始资料，Git 忽略。网站使用的图片和视频需复制到 `assets/` 后引用。
- 增加项目时复制一个详情页，并在首页添加对应卡片；如新增分类，同步补充筛选按钮的 `data-filter` 与卡片的 `data-category`。
- 所有内部地址使用相对路径，方便 GitHub Pages 根站点或项目子路径部署。

## AeroVLA 项目来源

AeroVLA 内容依据本地参考仓库版本 `b87aaa7` 的 README 与代码整理，原项目为 [XuPeng23/AeroVLA](https://github.com/XuPeng23/AeroVLA)。图片原样保存在 `assets/aerovla/`，附来源说明与原仓库 Apache-2.0 许可证。图片和原项目方法归原作者所有，个人实验记录应与原作者结果区分。未复制模型、数据集或运行代码，也不会在网站中执行模型推理。
