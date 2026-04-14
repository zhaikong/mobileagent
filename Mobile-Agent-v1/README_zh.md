![](assets/logo.png?v=1&type=image)
## Mobile-Agent: 视觉感知方案的自动化移动设备操作智能体
<div align="center">
  <a href="https://arxiv.org/abs/2401.16158"><img src="https://img.shields.io/badge/Arxiv-2401.16158-b31b1b.svg?logo=arXiv" alt=""></a>
  <a href="https://huggingface.co/papers/2401.16158"><img src="https://img.shields.io/badge/🤗-Paper%20In%20HF-red.svg" alt=""></a>
</div>
<br>
<div align="center">
Junyang Wang<sup>1</sup>, Haiyang Xu<sup>2†</sup>, Jiabo Ye<sup>2</sup>, Ming Yan<sup>2†</sup>,
</div>
<div align="center">
Weizhou Shen<sup>2</sup>, Ji Zhang<sup>2</sup>, Fei Huang<sup>2</sup>, Jitao Sang<sup>1†</sup>
</div>
<div align="center">
{junyangwang, jtsang}@bjtu.edu.cn, {shuofeng.xhy, ym119608}@alibaba-inc.com
</div>
<br>
<div align="center">
<sup>1</sup>北京交通大学    <sup>2</sup>阿里巴巴集团
</div>
<div align="center">
<sup>†</sup>通讯作者
</div>

<div align="center">
<a href="README_zh.md">简体中文</a> | <a href="README.md">English</a>
<hr>
</div>
<!--
简体中文 | [English](README.md)
<hr>
-->

## 📋介绍
![](assets/example.png?v=1&type=image)
* 纯视觉方案，不依赖XML和其他系统底层文件。
* 不限制操作范围，具备跨应用操作能力。
* 多种视觉感知工具协助操作定位。
* 不需要探索阶段和训练，即插即用。

## 📢News
* [3.10]🔥🔥Mobile-Agent 被 **ICLR 2024 Workshop on Large Language Model (LLM) Agents** 接收。
* [3.4]🔥🔥我们发布了 [Mobile-Agent via Qwen-vl-max](https://github.com/X-PLUG/MobileAgent/blob/main/MobileAgent-qwen/README.md)。 Qwen-vl-max 是一个限时免费的多模态大语言模型。
* [2.21] 我们提供了一个可以上传设备截图的Demo。 目前可以在 [Hugging Face](https://huggingface.co/spaces/junyangwang0410/Mobile-Agent) 和 [ModelScope](https://modelscope.cn/studios/wangjunyang/Mobile-Agent/summary) 中体验。
*  [2.5] 我们提供了一个 **free** API 并且在远端服务上部署了Mobile-Agent的流程, 即使你**没有 OpenAI API Key**。 请查看 [快速开始](#quick_start).

## 📺演示

### 视频
https://github.com/X-PLUG/MobileAgent/assets/127390760/26c48fb0-67ed-4df6-97b2-aa0c18386d31

### Hugging Face Demo
![](assets/huggingface_demo.png?v=1&type=image)
Demo目前可以在 [Hugging Face](https://huggingface.co/spaces/junyangwang0410/Mobile-Agent) 和 [ModelScope](https://modelscope.cn/studios/wangjunyang/Mobile-Agent/summary) 体验。

## 🔧准备

❗目前仅安卓和鸿蒙系统（版本号 <= 4）支持工具调试。其他系统如iOS暂时不支持使用Mobile-Agent。

### 安装依赖
```
git clone https://github.com/X-PLUG/MobileAgent.git
cd MobileAgent
pip install -r requirements.txt
```


### 准备通过ADB连接你的移动设备

1. 下载 [Android Debug Bridge](https://developer.android.com/tools/releases/platform-tools?hl=en)（ADB）。
2. 在你的移动设备上开启“USB调试”或“ADB调试”，它通常需要打开开发者选项并在其中开启。
3. 通过数据线连接移动设备和电脑，在手机的连接选项中选择“传输文件”。
4. 用下面的命令来测试你的连接是否成功: ```/path/to/adb devices```。如果输出的结果显示你的设备列表不为空，则说明连接成功。
5. 如果你是用的是MacOS或者Linux，请先为 ADB 开启权限: ```sudo chmod +x /path/to/adb```。
6.  ```/path/to/adb```在Windows电脑上将是```xx/xx/adb.exe```的文件格式，而在MacOS或者Linux则是```xx/xx/adb```的文件格式。

<a id="quick_start"></a>

## 🔧快速开始
### 注意
❗由于GPT-4v在非英文场景中存在幻觉，我们建议在英文场景下使用。除此之外，你可以使用GPT-4o来提升非英文场景的性能。

### 运行
```
python run_api.py --adb_path /path/to/adb --url "The url you got" --token "The token you got" --instruction "your instruction"
```

## 🔧使用你自己的API-KEY运行

```
python run.py --adb_path /path/to/adb --api "your API_TOKEN" --instruction "your instruction"
```
API_TOKEN 是来自OpenAI的可以访问 ```gpt-4-vision-preview``` 的序列码。

## 📑引用

如果您发现移动设备对研究和应用程序有用，请使用此Bibtex引用：
```
@article{wang2024mobile,
  title={Mobile-Agent: Autonomous Multi-Modal Mobile Device Agent with Visual Perception},
  author={Wang, Junyang and Xu, Haiyang and Ye, Jiabo and Yan, Ming and Shen, Weizhou and Zhang, Ji and Huang, Fei and Sang, Jitao},
  journal={arXiv preprint arXiv:2401.16158},
  year={2024}
}
```
