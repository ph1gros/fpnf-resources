# FPNF 资源中心

For People No Friend 的公开可选语音组件仓库。适用于 Windows x64，配合 FPNF v1.8.0 使用。主程序与组件分开发布，按需下载。

[主程序仓库](https://github.com/ph1gros/for-people-no-friend) · [组件下载](https://github.com/ph1gros/fpnf-resources/releases/tag/components-v1.8.0)

## 安装

在 FPNF 设置或托盘菜单打开独立的“资源中心”，分别安装需要的引擎、基础模型、音色模型或语音识别模型。刷新目录不会自动安装，也不会替换已经安装的组件。首次启动引擎仍需加载模型，之后复用进程。

- 伊蕾娜朗读：Style-Bert-VITS2 引擎 + 日语 DeBERTa 基础模型 + 伊蕾娜音色模型。
- 未花朗读：Genie-TTS 引擎 + Genie 基础模型 + 圣园未花（Mika）音色。选择 Genie-TTS 后使用内置 Mika 日语预设。
- 麦克风输入：SenseVoiceSmall 语音识别模型；识别引擎已包含在主程序中。
- 主程序文字聊天不依赖这些组件。断网时仍可使用已安装的组件；未装齐的组合会显示缺少资源。

## 组件清单

所有组件版本为 1.0.0，Genie-TTS 引擎为 1.0.3（包含句尾终止标记修复、保守的长停顿降噪及 HTTP 打断后恢复；不改变音频长度或模型权重）。

| 资源 | 用途 | 下载大小 | 许可 |
| --- | --- | ---: | --- |
| [Style-Bert-VITS2 引擎](https://github.com/ph1gros/fpnf-resources/releases/download/components-v1.8.0/voice-runtime-1.0.0.zip) | 将文字合成为语音，提供 Style-Bert-VITS2 推理程序与独立运行环境。 | 127.65 MiB | AGPL-3.0；部分模块 LGPL-3.0；依赖按各自许可 |
| [Genie-TTS 引擎](https://github.com/ph1gros/fpnf-resources/releases/download/components-v1.8.0/genie-tts-1.0.3.zip) | 将文字合成为语音，提供 Genie-TTS 推理程序与独立运行环境。 | 169.96 MiB | 引擎 MIT；依赖和模型按各自许可 |
| [Genie 基础模型](https://github.com/ph1gros/fpnf-resources/releases/download/components-v1.8.0/genie-data-1.0.0.zip) | 为语音合成提供参考音频特征，帮助引擎理解发音与说话人信息，不决定角色音色。 | 270.12 MiB | 上游资源仓库标注 MIT；保留来源及第三方权利说明 |
| [圣园未花（Mika）音色](https://github.com/ph1gros/fpnf-resources/releases/download/components-v1.8.0/voice-genie-mika-1.0.0.zip) | 提供圣园未花（Mika）的日语音色，决定角色发声特征；角色出自《蔚蓝档案》。 | 291.38 MiB | 上游仓库标注 MIT；角色及声音权利另行适用，见随附说明 |
| [日语 DeBERTa 基础模型](https://github.com/ph1gros/fpnf-resources/releases/download/components-v1.8.0/bert-japanese-1.0.0.zip) | 为语音合成提供日语文本特征，帮助引擎理解读音与上下文，不决定角色音色。 | 348.12 MiB | CC BY-SA 4.0；保留署名、来源和修改说明 |
| [伊蕾娜音色模型](https://github.com/ph1gros/fpnf-resources/releases/download/components-v1.8.0/voice-ireina-1.0.0.zip) | 提供伊蕾娜（Ireina）的日语音色，决定角色发声特征；角色出自《魔女之旅》。 | 220.54 MiB | 仅限非商业使用；须保留随附使用说明 |
| [SenseVoiceSmall 语音识别模型](https://github.com/ph1gros/fpnf-resources/releases/download/components-v1.8.0/speech-input-1.0.0.zip) | 将录音转换为文字，提供 SenseVoiceSmall 识别模型，供麦克风输入使用。 | 152.88 MiB | FunASR 模型许可；保留模型名称与来源声明 |

全部七项下载共 1.54 GiB（1657430665 字节）。通常只需选择其中一套朗读组件。安装时还需要解压空间，客户端会在下载前检查磁盘余量。

## 来源与使用条件

- Style-Bert-VITS2 2.7.0：[上游源码](https://github.com/litagin02/Style-Bert-VITS2/tree/d8148f3090ee5038ca7b4e4b327116c64467f952)，源文件、AGPL-3.0 / LGPL-3.0 与依赖声明在组件包内。FPNF 本地接口源文件也随包提供。
- 日语 DeBERTa：[KU-NLP 原模型](https://huggingface.co/ku-nlp/deberta-v2-large-japanese-char-wwm)、[tsukumijima ONNX 转换](https://huggingface.co/tsukumijima/deberta-v2-large-japanese-char-wwm-onnx)，CC BY-SA 4.0，保留署名和来源；本轮仅分包，未修改权重。
- SenseVoiceSmall：[FunAudioLLM](https://github.com/FunAudioLLM/SenseVoice)、[sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx)，遵守随附 [FunASR 模型许可](https://github.com/modelscope/FunASR/blob/main/MODEL_LICENSE)。
- Genie-TTS 2.0.2 与模型：[Genie](https://github.com/High-Logic/Genie-TTS)、[固定版本模型来源](https://huggingface.co/High-Logic/Genie/tree/52b17272e0b7032415e85ad37b551db2386b1810)，保留随附 MIT 及依赖声明。Mika 为《蔚蓝档案》圣园未花的日语示例音色，角色及声音权利仍归各自权利人。
- **伊蕾娜仅限非商业用途**。允许在保留随附说明的前提下非商业复制、分享和再分发，不得用于收费产品、商业服务、转售或变现。角色及声音权利归各自权利人。见包内 LICENSE.txt。

本仓库不是一个统一许可的素材库；主项目的非商用条件不改变第三方组件原始许可，也不额外授予角色或声音权利。未包含 OneDrive 的传统 VITS 音色、黑猫模型、训练原始录音、用户配置或对话数据。

## 下载校验与更新

目录 catalog.json 仅展示资源信息；speech-assets-v1.8.0.json 仅提供组件 ID、版本和下载地址。真正的 SHA-256、大小、文件数和安装目标固定在主程序源码中，下载后核对一致才解压激活；远程仓库不能通过换一个哈希授权新的程序。

Release 附带 SHA256SUMS.txt 与 measurements.json 供人工核对，不作为客户端信任来源。未来更换任何组件都需要发布带有新校验记录的主程序，旧版路由文件保持兼容。
