# 🚀 Save_records v0.9
让每一次工作都留下清醒的回顾

<p align="center"> <img src="https://img.shields.io/badge/version-1.0.0-blue?style=flat-square" alt="version"> <img src="https://img.shields.io/badge/platform-Windows%2010%2F11-lightgrey?style=flat-square" alt="platform"> <img src="https://img.shields.io/badge/license-MIT-green?style=flat-square" alt="license"> <img src="https://img.shields.io/badge/AI-offline-important?style=flat-square" alt="offline AI"> </p>
Save_records 是一款完全本地运行的工作活动记录与分析工具。它定时截屏、记录窗口标题，并在结束时由离线语言模型生成结构化的分析报告——包括软件使用统计、活动推测、意义评估、注意力评分及改进建议，助你提高专注与生产力。

🎯 主要功能
🖥️ 自动活动记录
定时截图（WebP 高效压缩）并记录当前窗口标题，仅保存有变化的画面，不产生冗余数据。

🧠 离线 AI 分析
内置小型语言模型（Qwen2-0.5B），完全本地运行，无需联网，保障隐私安全。

📊 结构化报告
自动生成 Markdown 格式的详细报告，涵盖：

各软件使用时长统计

活动内容推测

工作/学习意义评估

注意力评分（1~10）

两条改进建议

📁 数据本地存储
所有日志、截图、报告均保存在程序同级目录，数据由你完全掌控。

🔧 实用工具
支持清理过期截图、将 CSV 导出为 HTML、随时查看历史报告。

⚙️ 环境要求
操作系统：Windows 10 / 11（64 位）

运行环境：无需安装 Python（使用预编译 EXE 版）

磁盘空间：至少 2GB 空闲（用于存放 AI 模型）

网络：首次运行时需联网下载模型（约 1GB），之后完全离线可用

📦 快速开始
方式一：预编译 EXE（推荐✨）
从 Releases 页面下载 RecordRetention.exe。

双击运行，程序将弹出控制台窗口并开始自动记录。

结束时按下 Ctrl+C，模型会在首次运行时自动下载，随后生成分析报告。

前往 reports/ 文件夹查看你的结构化报告。

方式二：从源码运行
bash
git clone https://github.com/yourname/RecordRetention.git
cd RecordRetention
pip install -r requirements.txt
python main.py
首次启动会自动下载模型至 models/Qwen2-0.5B-Instruct。

📂 项目结构（运行时生成的数据）
text
RecordRetention/
├── logs/
│   ├── session.csv          # 活动记录日志
│   ├── raw/                 # 截图（.webp 格式）
│   └── console.log          # 控制台输出备份
├── models/                  # AI 模型（首次运行后出现）
│   └── Qwen2-0.5B-Instruct/
├── reports/                 # 生成的 Markdown 报告
└── RecordRetention.exe      # 主程序
所有数据均存放在程序同级目录，可随时手动删除以清理空间。

❓ 常见问题
<details> <summary><b>Q: 首次运行下载模型失败怎么办？</b></summary> 可手动从 <a href="https://huggingface.co/Qwen">Hugging Face</a> 下载所有模型文件，并放入程序同目录的 <code>models/Qwen2-0.5B-Instruct</code> 文件夹内。 </details><details> <summary><b>Q: 杀毒软件报毒？</b></summary> 程序包含屏幕截图功能，部分安全软件可能误报。请将程序目录添加至信任区，或自行审查源码后运行。 </details><details> <summary><b>Q: 截图太多占用空间怎么办？</b></summary> 运行 <code>python utils.py clean --days 3</code> 可删除 3 天前的旧截图，报告和 CSV 日志不会被删除。 </details><details> <summary><b>Q: 如何修改截图间隔？</b></summary> 当前版本需编辑 <code>main.py</code> 中的 <code>interval</code> 变量（默认 15 秒），未来版本将支持配置文件修改。 </details>
🤝 贡献与支持
欢迎提交 Issue 或 Pull Request 一起打磨这个工具！
项目采用 MIT 协议 开源，你可以自由使用、修改和分发。

<p align="center"> <b>立即体验，让时间流向更清晰的方向！</b> </p>
