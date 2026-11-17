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
│   ├── favicon.svg
│   ├── autonomy.svg                   # 自动驾驶概念图
│   ├── vla.svg                        # 视觉语言动作概念图
│   ├── navigation.svg                 # 路径规划概念图
│   └── learning.svg                   # 网络与训练曲线概念图
├── projects/
│   ├── autonomous-driving.html
│   ├── vision-language-action.html
│   ├── robot-navigation.html
│   └── deep-learning.html
└── README.md
```

详情页包含项目概述、技术方案、评估计划和后续工作，并提供返回首页与下一个项目入口。所有页面均为真实静态 HTML 文件，支持直接访问与刷新；关闭 JavaScript 仍可浏览完整内容。

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
- 联系方式：GitHub 使用与仓库对应的 `zongyunfwx` 账号；邮箱尚未提供，显示为“邮箱待补充”。确认邮箱后，可将该行替换为 `mailto:你的邮箱` 链接。
- `projects/*.html`：当前为明确标注的方案草稿，补充实际背景、个人职责、代码仓库、演示材料、数据来源、实验环境与真实结果后，再修改状态说明。不要把计划指标当作实测成果。
- SVG 均为可编辑的概念示意图，训练曲线不是实际实验数据；可替换为真实截图或实验图，并更新 `alt` 描述。
- 增加项目时复制一个详情页，并在首页添加对应卡片；如新增分类，同步补充筛选按钮的 `data-filter` 与卡片的 `data-category`。
- 所有内部地址使用相对路径，方便 GitHub Pages 根站点或项目子路径部署。
