# streamtextpro后端部署流程 
## 前置条件
- 安装好 Anaconda
- 安装好 Git
- 安装好 Chocolatey
- 通畅的网络连接
  
下面为具体操作
### GetAudio环境部署

1. 打开 Anaconda PowerShell Prompt（以管理员身份运行）。

2. 输入以下命令创建虚拟环境，替换 `your-env-name` 为你自己对这个环境的命名，例如：`test_py3.11`。
```shell
   conda create -n your-env-name python==3.11
   ```
输入 'y' 以确认创建该环境<br>
3.输入以下命令激活环境：
   ```shell
   conda activate your-env-name
   ```
4.输入以下命令拉取和安装最新的仓库：
   ```shell
   pip install git+https://github.com/openai/whisper.git
   ```
可能会遇到网络问题导致的报错，可以尝试使用代理，节点选择香港。也可能需要更新 setuptools
   ```shell
   pip install --upgrade setuptools
   ```
完成了上述的步骤后等待大约五分钟
5.输入以下命令更新版本：
   ```shell
   pip install --upgrade --no-deps --force-reinstall git+https://github.com/openai/whisper.git
   ```
6.安装 FFmpeg：
   ```shell
   choco install ffmpeg
   ```
7.安装Rust
   ```shell
   pip install setuptools-rust
   ```
要运行语音转文字项目，打开 StreamTextPro，打开 GetAudio，运行 GetTransform，输入正在观看的 B 站网页，在 audio_reserve 文件夹下查看转换后的文本。
可能会遇到路径错误，需要修改相对路径为绝对路径。
第一次运行时，会在 C:\用户\用户名\.cache\whisper 下下载大小约为 140MB 的 base 模型，请耐心等待。
恭喜成功完成 Whisper 的本地部署！

###ChatGLM2-6B量化int4本地部署
1.以管理员运行Anaconda PowerShell
2.输入以下命令激活环境：
```shell
conda activate your-env-name
```
3.使用以下命令安装依赖项:
```shell
pip install protobuf cpm_kernels transformers==4.30.2 gradio mdtex2html sentencepiece accelerate sse-starlette streamlit>=1.24.0
```
4.输入以下命令安装`bigdl-llm`库用于量化模型：
```shell
pip install --pre --upgrade bigdl-llm[all]
```







