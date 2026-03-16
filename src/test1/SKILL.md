# VideoCut Skills 2.0 (Jianying/CapCut Edition)

这是一个基于 [Ceeon/videocut-skills](https://github.com/Ceeon/videocut-skills) 进行了深度扩展的 Antigravity AI 视频剪辑技能库。

## ✨ 主要增强功能

在原项目基础上，我们重点解决了口播视频自动化剪辑后与 **剪映专业版 (Jianying Pro)** 的无缝对接问题：

1.  **精准同步导出**：通过原始素材时间轴重建技术，彻底解决了长视频剪辑后音画不同步的累计误差。
2.  **真·字幕轨道支持**：自动生成 SRT 内容并利用 `pyJianYingDraft` 库将其转换为剪映原生的“字幕轨道”，而非普通的文本卡片。
3.  **智能语义断句**：
    *   **停顿识别**：利用语音停顿（isGap）进行自然断句。大三大四的
    *   **语义边界**：在语气词（的、了、好、吧等）后断句，避免在人名或核心词中间切断。
    *   **字数优化**：支持自定义单句字数限制（默认 12-14 字）。
4.  **工程化配置**：支持通过 `.env` 自动化管理本地素材路径和剪映草稿目录，实现脚本一键入库。
dds
## 🚀 快速开始

### 1. 安装依赖
```bash
pip install pyJianYingDraft
```

### 2. 配置环境
复制 `.env.example` 为 `.env` 并修改为你本地的实际路径：
- `RAW_VIDEO_DIR`: 你的原始录像存放地。
- `JIANYING_DRAFT_DIR`: 你的剪映草稿目录。
- `VOLCENGINE_API_KEY`: 火山引擎转录 API 密钥。

### 3. 使用脚本
运行剪辑脚本并带上导出参数：
```powershell
./scripts/cut_video.ps1 -VideoPath "你的视频.mp4" -ExportToJianying
```

## 🙏 特别鸣谢
本项目的核心剪辑逻辑深受 [Ceeon/videocut-skills](https://github.com/Ceeon/videocut-skills) 启发，感谢原作者提供的优秀方法论。

## License
MIT
