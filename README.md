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
   输入 'y' 以确认创建该环境
3.输入以下命令激活环境：
   ```shell
   conda activate your-env-name
   ```
4.输入以下命令拉取和安装最新的仓库：
  ```shell
pip install git+https://github.com/openai/whisper.git
```
