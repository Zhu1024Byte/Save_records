# 🚀 Save_records v1.0.0 发行说明
让每一次工作都留下清醒的回顾

Save_records 是一款完全本地运行的工作活动记录与分析工具。它定时截屏、记录窗口标题，并在结束时由离线语言模型生成结构化的分析报告——包括软件使用统计、活动推测、意义评估、注意力评分及改进建议，助你提高专注与生产力。

🎯 主要功能
🖥️ 自动活动记录：定时截图（WebP压缩）并记录当前窗口标题，仅保存有变化的画面。
🧠 离线AI分析：内置小型语言模型（Qwen2‑0.5B），完全本地运行，无需联网。
📊 结构化报告：自动生成 Markdown 报告，涵盖：
各软件使用时长统计
活动内容推测
工作/学习意义评估
注意力评分（1~10）
两条改进建议
📁 数据本地存储：所有日志、截图、报告均保存在程序同级目录，隐私安全。
🔧 实用工具：支持清理过期截图、导出CSV为HTML、查看历史报告。
⚙️ 环境要求
Windows 10/11（64位）
无需安装 Python（若使用 EXE 版）
至少 2GB 空闲磁盘（用于模型存储）
模型下载需稳定网络（约 1GB），之后完全离线可用
📦 快速开始
方式一：使用预编译 EXE（推荐）
从 Releases 下载 RecordRetention.exe。
双击运行，程序会弹出控制台窗口并开始记录。
按下 Ctrl+C 停止记录，模型会自动下载（如首次），随后生成分析报告。
报告文件保存在 reports/ 文件夹中。
方式二：从源码运行
Bash
git clone https://github.com/yourname/RecordRetention.git
cd RecordRetention
pip install -r requirements.txt
python main.py
首次运行会下载模型到项目目录的 models/Qwen2-0.5B-Instruct。

📂 项目结构（生成的数据）
Text
RecordRetention/
├── logs/
│   ├── session.csv          # 活动记录
│   ├── raw/                 # 截图（.webp）
│   └── console.log          # 控制台输出
├── models/                  # AI模型（首次运行后出现）
│   └── Qwen2-0.5B-Instruct/
├── reports/                 # 生成的Markdown报告
└── RecordRetention.exe      # 主程序
所有数据均存放在程序同级目录，可随时删除以清理空间。

❓ 常见问题
Q: 首次运行下载模型失败怎么办？

A: 可手动从 Hugging Face 下载所有文件，并放入程序同目录的 models/Qwen2-0.5B-Instruct 文件夹内。

Q: 杀毒软件报毒？

A: 程序包含屏幕截图功能，部分安全软件可能误报。请将程序目录添加至信任区，或自行审查源码后运行。

Q: 截图太多占用空间？

A: 运行 python utils.py clean --days 3 可删除3天前的旧截图；报告和CSV日志不会被删除。

Q: 如何修改截图间隔？

A: 当前版本需编辑 main.py 中的 interval 变量（默认15秒），未来版本将支持配置文件。

🤝 贡献与支持
欢迎提交 Issue 或 Pull Request！

项目采用 MIT 协议开源，你可以自由使用、修改和分发。

立即体验，让时间流向更清晰的方向！
