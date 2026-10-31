# Windows 10 安装 Docker 完整教程(WSL2 + Docker Desktop)

## 本项目主要记录 Windows 系统下 Docker 开发环境的安装、配置、使用以及常见问题解决方案。

## 适用环境
- Windows 10 22H2
- WSL2 
- Ubuntu
- Docker Desktop 4.97.0

### 准备工作与安装WSL2
- 1 Win+R输入 optionalfeatures 打开 Windows功能对话框 

- 2 勾选Hyper-V、适用于Linux的Windows子系统、虚拟机平台  

- 3 确定后重启并等待更新

- 4 Win+R 输入 powershell 输入 wsl --set-default-version 2 设置默认WSL2为默认版本  

- 5 Win+R 输入 powershell 输入 wsl-install 此命令将启用运行WSL并安装Linux的Ubuntu分发所需的功能  

### 安装Docker Desktop
- 1 访问 Docker Desktop 官网 https://www.docker.com/products/docker-desktop/ 点击Download Docker Desktop下载

- 2 双击下载的 Docker Desktop Installer.exe  

- 3 勾选 Use WSL2 instead of Hyper-V 和 add shortcut to desktop 

- 4 安装路径自定义、 其他选项通常保持默认即可  

- 5 如果 Docker Desktop 显示 WSL needs updating , 直接下载WSL离线更新包 https://github.com/microsoft/WSL/releases 下载最新版本的 .msi安装包进行安装，并进行重启  

### debug
- 目前WSL有一个bug 无法加载远程桌面服务 ActiveX控件。请确保rdclientax.dll 在路径中。  

- 解决方案：Win+R 输入 powershell 输入 wsl --shutdown 关掉WSL 然后在C盘路径下新建或编辑%USERPROFILE%\.wslconfig 这个文件添加以下代码  
```
[wsl2]
guiApplications=false
```

### 汉化Docker Desktop
- 1 退出 Docker Desktop  

- 2 访问 https://github.com/asxez/DockerDesktop-CN/releases 选择所对应的版本进行下载，解压后点击 安装汉化.bat  

