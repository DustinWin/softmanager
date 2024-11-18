# 一、 说明
1. 每周五下午 6 点（北京时间 UTC+8）自动构建
2. [软件管理](https://pc.qq.com)提取自[腾讯电脑管家](https://guanjia.qq.com) 15.6.23123.201 版本（v15 系列版本已停更）
3. 软件库文件包含 SoftPolicy.etf 和 SoftVerInfo.etf（控制“软件库”版本），以及 GlobalConfig.etf（控制“首页”和“游戏”栏目中的推荐列表）

# 二、 软件特色
1. 免安装绿色版
2. 可下载、安装、升级、卸载软件
3. 可一键卸载 Windows 10 或 Windows 11 UWP 应用
4. 收录国内外主流软件，安装升级更方便
5. 可自动适配屏幕 DPI，显示更清晰

# 三、 使用方法
## 1. 首次使用
- ① 首次使用请下载完整绿色包 QQPCSoftMgr.zip，解压后得到“*版本号*”文件夹。然后下载软件库更新文件 libraries.zip
，解压里面的 .etf 文件到“*版本号*”文件夹
- ② **将“*版本号*”文件夹移动到 *C:\Program Files (x86)\Tencent\QQPCMgr* 路径下（没有则新建）**，双击“*版本号*”文件夹内的“QQPCSoftMgr.exe”文件即可运行
  - 注：提取自腾讯电脑管家 v15+ 版本的软件管理不可跳过第 ② 步，省略该步骤将无法运行；已上传自解压文件 QQPCSoftMgr.exe
  ，使用 WinRAR 制作，自解压后可直接运行软件管理

## 2. 更新软件库
- ① 编辑文本文档，粘贴如下内容：
  - 注：将 `{版本号}` 替换为当前提取自腾讯电脑管家的版本号

```
@echo off
rem 结束软件管理相关进程
taskkill /f /t /im QQPCSoftMgr*
taskkill /f /t /im QMDL*
rem 更新软件库文件
curl -o "%PROGRAMFILES(X86)%\Tencent\QQPCMgr\{版本号}\GlobalConfig.etf" -L https://cdn.jsdelivr.net/gh/DustinWin/softmanager@QQPCSoftMgr/GlobalConfig.etf
curl -o "%PROGRAMFILES(X86)%\Tencent\QQPCMgr\{版本号}\SoftPolicy.etf" -L https://cdn.jsdelivr.net/gh/DustinWin/softmanager@QQPCSoftMgr/SoftPolicy.etf
curl -o "%PROGRAMFILES(X86)%\Tencent\QQPCMgr\{版本号}\SoftVerInfo.etf" -L https://cdn.jsdelivr.net/gh/DustinWin/softmanager@QQPCSoftMgr/SoftVerInfo.etf
echo 更新软件库文件成功
pause
```
- ② 另存为 .bat 文件，右击并选择“以管理员身份运行”

# 四、 软件截图
## 1. 首页  
<img src="https://github.com/user-attachments/assets/8f045103-27ac-4b70-85f6-d062a32e56fa" width="60%" />

## 2. 升级  
<img src="https://github.com/user-attachments/assets/71639317-a797-4c3b-85f1-576193563852" width="60%" />

## 3. 卸载  
<img src="https://github.com/user-attachments/assets/3002ae95-70cc-4c9d-b7e8-e6b05d21d431" width="60%" />
