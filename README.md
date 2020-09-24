# EzCheckInSchool
最简单的完美校园自动健康打卡，基于Github Actions免服务器运行。

- 多人打卡👨‍👩‍👧‍👦
- 仅需学号姓名🎫
- 随机校内经纬度🗺️
- 打卡结果微信推送💬
- 随机温度(36.2℃-36.5℃)🌡
- 打卡时间:06:35,13:05,21:35🕑

**Github Actions定时任务可能出现几分钟的误差，可能由于完美校园崩溃而导致打卡失败**


## 更新日志

部分老版本可能存在打卡失败 `Gateway timeout 504` 错误，建议更新新版本。

2020.9.16 21:35 更新多用户版，使用WxPusher，致谢[@themanforfree](https://github.com/themanforfree)

2020.9.14 12:40 使用方法优化

## 使用方法

首先，点击页面上方`Star`和`Fork`，此时你将得到复   制的项目

![Star and fork](https://s1.ax1x.com/2020/09/16/w22nDx.png)

点击下方链接微信扫码关注，以便获取打卡结果推送

[Wechat QRCode](http://wxpusher.zjiecode.com/api/qrcode/FHFBNBtuM9q4rmR2AS2okzHcBEoh9pFa1JsseEb0PXixltPGFh3UFaw0qwLH4sSJ.jpg)

关注后点击我的->我的UID，获取每个人的WxPusher UID

![WxPusher UID](https://s1.ax1x.com/2020/09/16/w2W6H0.png)

接下来你需要设置`Secret` Fork的项目->Settings->Secret->New Secret

![New Secert](https://s1.ax1x.com/2020/09/17/wR4IOJ.png)

打开完美校园健康打卡，参照打卡页面上方个人信息及如下表格设置


**每人一行，全部输入完后以end结尾**

|Name|Value|
| :-----| :-----|
|`USER_IN`|`姓名,学号,学院-专业-班级,WxPusher UID`<br/>`......`<br/>`end`|

每行信息按顺序如下，以英文逗号隔开

|No|Type|Example|
| :-----| :---- | :---- |
|1|`姓名`|`小明`|
|2|`学号`|`201912340101`|
|3|`学院-专业-班级`|`理学院-应用物理学-应物1901`|
|4|`WxPusher UID`|`UID_abcdefghijklm`| 

以上信息应添加的Secert为

![Single User](https://s1.ax1x.com/2020/09/17/wR4Tm9.png)

若有多人需要打卡，

![Multi User](https://s1.ax1x.com/2020/09/17/wR45y4.png)

以上步骤完成后

Fork的项目->Action->I understand... 开启Actions

回到项目主页，修改[README.md](/README.md)随便加几个空格即可

**首次开启若不在打卡时间将会重打早间卡作为测试**

设置完成打卡后打卡时间内会每天自动打卡三次，第一次使用请观察效果。

**注意：本项目默认学校为河南工业大学，其他学校请自行抓包修改代码。**

|Method|URL|修改|
| :-----| :---- | :---- |
|`POST`|`https://reportedh5.17wanxiao.com/sass/api/epmpics`|`main.py`|
|`POST`|`https://reportedh5.17wanxiao.com/api/passcard/queryOrg`|`response.json`|

### 捐赠
最后，如果觉得这个项目对你有帮助的话

![Donate](https://s1.ax1x.com/2020/09/15/wcPVqP.png)

## 友情链接

https://github.com/YooKing/HAUT_autoCheck - 学习Python语法参考

https://github.com/LovelyWhite/Haut-AutoCheckin - iOS捷径版

https://github.com/themanforfree/EzCheckInSchool-MultiUser - 多用户想法

