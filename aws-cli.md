## AWS Command Line Interface

- **简介**

​      [AWS Command Line Interface](https://docs.aws.amazon.com/zh_cn/cli/index.html) (AWS CLI) 是一种开源工具，让您能够在命令行 Shell 中使用命令与 AWS 服务进行交互。仅需最少的配置，您就可以从常用终端程序中的命令提示符开始使用基于浏览器的 AWS 管理控制台提供的相同功能：

- **Linux Shell** – 使用常见 Shell 程序（例如 `bash`、`zsh` 和 `tsch`）在 Linux, macOS, or Unix 中运行命令。

- **Windows 命令行** – 在 Windows 上，在 PowerShell 或 Windows 命令提示符处运行命令。

- **远程** – 通过远程终端（如 PuTTY 或 SSH）或者使用 AWS Systems Manager 在 Amazon Elastic Compute Cloud (Amazon EC2) 实例上运行命令。

  

  所有 IaaS（基础设施即服务）AWS 管理和访问 AWS API 和 CLI 中提供的 AWS 管理控制台 函数。新的 AWS IaaS 功能和服务在启动时或在 180 天启动期内通过 API 和 CLI 提供全部 AWS 管理控制台 功能。

  AWS CLI 提供对 AWS 服务的公共 API 的直接访问。您可以使用 AWS CLI 探索服务的功能，可以开发 Shell 脚本来管理资源。或者，也可以通过 AWS 开发工具包利用所学知识开发其他语言的程序。

  除了低级别的 API 等效命令，多项 AWS 服务还为 AWS CLI 提供了自定义项。自定义项可能包括更高级别的命令，可简化具有复杂 API 的服务的使用。例如，`aws s3` 命令集提供熟悉的语法，用于管理 Amazon Simple Storage Service (Amazon S3) 中的文件。

- **安装AWS CLI**

   **先决条件**

  - Python 2 版本 2.6.5+ 或 Python 3 版本 3.3+
  - Windows、Linux, macOS, or Unix

     注意: 较早版本的 Python 可能无法兼容所有 AWS 服务。如果在安装或使用 AWS CLI 时看到 `InsecurePlatformWarning` 或弃用通知，请更新到更高的版本。

  

    [Linux 安装](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/install-linux.html) AWS Command Line Interface (AWS CLI) 的方法:

  - [Using pip](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-chap-install.html#install-tool-pip)
  - [使用虚拟环境](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-chap-install.html#install-tool-venv)
  - [使用捆绑安装程序](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-chap-install.html#install-tool-bundled)

  

   [Windows 安装](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/install-windows.html) AWS Command Line Interface (AWS CLI) 的方法:

  可以在 Windows 上使用独立安装程序或 `pip`（一种适用于 Python 的程序包管理器）来安装 AWS Command Line Interface (AWS CLI)。如果您已有 `pip`，请按照主要[安装主题](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-chap-install.html)中的说明执行操作。

  - [使用 MSI 安装程序安装 AWS CLI](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/install-windows.html#install-msi-on-windows)

  - [在 Windows 上使用 Python 和 pip 安装 AWS CLI](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/install-windows.html#awscli-install-windows-pip)

  - [将 AWS CLI 可执行文件添加到命令行路径](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/install-windows.html#awscli-install-windows-path)

    

    [MacOS 安装](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/install-windows.html) 

  

- **配置AWS CLI**
  - [快速配置 AWS CLI](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-chap-configure.html#cli-quick-configuration)
  - [配置设置和优先顺序](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-chap-configure.html#config-settings-and-precedence)
  - [配置和证书文件](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-files.html)
  - [命名配置文件](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-profiles.html)
  - [环境变量](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-envvars.html)
  - [命令行选项](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-options.html)
  - [使用外部进程获取凭证](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-sourcing-external.html)
  - [实例元数据](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-metadata.html)
  - [使用 HTTP 代理](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-proxy.html)
  - [在 AWS CLI 中代入 IAM 角色](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-role.html)
  - [命令完成](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-configure-completion.html)



- **使用AWS CLI**

    查看AWS CLI版本

  ```bash
  aws --version
  aws-cli/1.16.128 Python/3.7.3 Darwin/18.6.0 botocore/1.12.118
  ```

  

  - [使用 AWS CLI 获取帮助](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-help.html)
  - [AWS CLI 中的命令结构](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-commandstructure.html)
  - [为 AWS CLI 指定参数值](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-parameters.html)
  - [从 JSON 输入文件生成 CLI 骨架和输入参数](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-skeleton.html)
  - [控制 AWS CLI 的命令输出](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-output.html)
  - [将速记语法与 AWS Command Line Interface结合使用](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-shorthand.html)
  - [使用 AWS CLI 分页选项](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-pagination.html)
  - [了解 AWS CLI 的返回代码](https://docs.aws.amazon.com/zh_cn/cli/latest/userguide/cli-usage-returncodes.html)





