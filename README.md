
# 人生重开模拟器游戏

## 一、游戏简介

本项目可将人生重开模拟器游戏，一键部署至云开发平台。项目原地址：https://github.com/VickScarlet/lifeRestart

项目在源码基础上，仅修改了package.json中的build指令和部分js的相对引用路径，适配项目部署到云端时需要的路径规范。（不修改亦可正常部署，但需将「部署配置」中的「资源路径」修改为“.”，且需要在域名后增加访问路径，并不优雅）

## 二、部署到云开发平台

**1.创建lifeRestart代码项目**

直接fork本项目到自己的GitHub账号下。

**2.打开云开发平台，完成阿里云账号注册登陆，同意云开发平台服务协议** https://workbench.aliyun.com/application

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/sign.png" width="400">

**3.创建云开发平台-前端部署应用**

3.1 创建前端应用

依次点击「应用列表」「前端应用」「新建前端应用」按钮。首先绑定GitHub帐号，允许云开发平台构建、发布你的GitHub代码为可访问的网站。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/create_0.png" width="200">

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/oauth.png" width="200">

选择第一步中的代码仓库、主干分支等，并点击下一步。主干分支一般指的是代码的master或main等分支。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/create_1.png" width="300">

点击「下一步」、「完成」。稍等片刻创建成功后，将进入到应用部署界面。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/create_2.png" width="600">

3.2 进行项目的部署

依次点击日常环境的「部署」「确定」，即可启动日常环境的发布流程。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/deploy.png" width="300">

如果您是第一次在该仓库上使用云开发平台，需要按照，将 https://ram.console.aliyun.com/manage/ak 中的AccessKeyID、AccessKeySecret，粘贴配置到GitHub Secret中的AK、SK变量中。具体步骤，请仔细阅读「部署配置」的Step1。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/config.png" width="500">

3.3 查看部署结果

部署成功后，点击「部署配置」，并点击「测试域名」，即可访问您的应用。请注意测试域名的过期时间。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/page.png" width="500">

如果测试域名访问时出现类似以下情况，请点击「高级」-「继续访问」。这是因为临时测试域名并未提供完整的证书，仅供您临时测试使用。如果需要发布为长期的正式网站，请看下一步。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/chromewarn.png" width="500">

3.4 （可选）添加自己的自定义域名

但是您可以通过设置自定义域名，并进行CNAME解析，来持久化这个前端游戏。在「部署配置」「自定义域名」中，添加您自己名下的域名，重新点击部署。再按照提示，将您名下的域名CNAME到指定的OSS域名下，即可使用自己的域名，持续访问该应用。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/mydomain.png" width="500">

3.5 （可选）使用CDN加速域名访问，节约流量费用

当网站流量巨大时，可点击「部署配置」中的「如何配置CDN加速」，将自己的域名与CDN加速绑定，从而加速网站访问，节约流量费用。

# 三、应用下线

云开发平台功能完全免费，但OSS存储会收取您存储、上传、下载的流量费用，具体请见： https://help.aliyun.com/document_detail/173521.html

如果希望马上停止应用计费，目前请您在OSS控制台指定Bucket内进行手动操作： https://oss.console.aliyun.com/bucket

进入您在「部署配置」中选择的Bucket，点击「文件管理」，并在多选框中勾选所有存储的文件，点击「删除」，即可即时完全停止应用被外界访问。

<img src="https://ecoboost-readme-image.oss-cn-shanghai.aliyuncs.com/feApp/github/lifeRestart/ossdelete.png" width="500">

当您需要启动时，只要重新点击云开发平台的部署按钮即可开始部署。云开发平台会尽快增加一键停服的自动化功能，方便您随时暂停应用。