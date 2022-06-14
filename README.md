# uestc_temperature_report

**电子科技大学（UESTC）每日体温填报**

**本项目仅适用于微信小程序 ->  "uestc学生情况报送“**

**项目通过 Github 的 Actions 实现每日定时自动填报体温**

**有任何问题，欢迎提Issues,我会尽量解答**

**如果觉得本项目对你有帮助，请顺手点个`Star`吧QAQ**



## **💭前言**

辅导员每日多次督促体温打卡，催生了本项目

平时忙起来会有忘记上报的情况，于是撸出了这个项目，实现自动打卡





## **🌀简介**

+ 项目需要获取小程序的Cookie来实现自动体温打卡
+ 支持多账号体温上报





## 🔨**使用方式**

1. Fork仓库
   
   + 点击右上角的`Fork`，将仓库Fork到自己的账号下
   
     ![1.png](./image/1.png)
2. 获取Cookie

   + 推荐采用微信PC客户端抓包的方式获取，使用Wireshark或Charles等抓包工具，获取小程序"uestc学生情况报送“登陆时所用的cookie

     参考视频 https://www.bilibili.com/video/BV1Kf4y1p727
3. 添加 Cookie 至 Secrets
   + 回到自己的项目页面，依次点击`Settings`-->`Secrets`-->`New repository secret`

     ![2.png](./image/2.png)

   + `Name`中填入`COOKIE`，将抓包到的`Cookie`粘贴到`Value`中，点击`Add secret`添加

     ![3.png](./image/3.png)

     注意：

     + Name的框中只能填`COOKIE`，不要填其他
     + 如果有多个 Cookie，不同账号的`Cookie`值之间用`#`分隔，如：`Cookie1#Cookie2#Cookie3`
4. 启用Action

   + 回到自己的项目页面，点击上方的`Actions`，允许启动 workflows

     ![4.png](./image/4.png)

     ![5.png](./image/5.png)

   + 再点击左侧的`uestc_temperature_report`，再点击`Run workflow`

     ![6.png](./image/6.png)

以上，项目部署完毕

+ 项目会在每日凌晨 0:30 左右进行自动上报，也可重新创建Action手动触发上报

+ 在`Actions`页面点击`uestc_temperature_report`-->`build`-->`Run Main`查看运行日志

  ![7.png](./image/7.png)

  ![8.png](./image/8.png)

  ![9.png](./image/9.png)

  





## **注意！！！**

+ Cookie 被储存在 Github 服务器中，仅供本项目使用。任何时候，开发者都无权获取您的 Cookie
+ 本项目仅用于交流学习目的，不会对您的任何损失负责，包括但不限于帐号异常，辅导员请喝茶，健康码泛红，考研失败，第三次世界大战等