# jspvz
Not my work!!!!!Cloned from http://www.lonelystar.org/

转载自http://www.lonelystar.org/

原始来源说明：

```
JSPVZ源代码 | 当前版本号：v12.10.25
作者：LonelyStar
大小：36.3M(包含很多兼容各种浏览器的音乐素材)
语言：简体中文
类型：休闲益智
授权：开源
环境：单机或服务器
简介：本游戏是使用HTML和JavaScript制作，为了兼容，IE6/7/8背景音乐用的是swf且没有音效,其余浏览器用的是mp3或ogg格式,有丰富音效
调用：欢迎非营利性下载和改编
```
```
代码调用说明：
本程序允许使用在个人或者单位网站上使用，但是请勿将本程序用于盈利目的！以下为程序说明，请需要修改代码的站长注意！
本程序是js+html代码，下载包未提供后台代码，但是提供了接口可以供后台调用。
js目录下的Cfunction.js文件中:
$User.Visitor.SaveLvl，在下载版中默认为0。1表示允许调用程序默认的存盘函数，但是下载版里未提供存盘的后台文件，所以设置为0表示不调用默认的存盘程序。一般请勿修改。
$User.Visitor.SaveLvlCallBack，程序中默认为null，该函数为提供给站长调用自定义函数的回调函数。当游戏每玩过一关后，会判断该函数是否存在，为null则不执行，如果是规定格式的自定义函数则执行该函数并且传递几个参数给该函数。
如果站长需要加一个回调函数在过关的地方，可以按照以下格式把函数定义写在index.htm末尾：
```
```
$User.Visitor.SaveLvlCallBack=function(o){
/*
参数o为一个json对象,它的属性为：
UserName:用户的游戏名
SunNum:剩余的阳光数量
Lvl:关卡的名字，冒险模式传递的是数字，其他传递的是英文名。比如第一关是1，“僵尸快跑！”则是'ZombieRun'
T:游戏关卡持续的时间，时间单位是游戏内部的数字，如果换算成秒要除以100，比如传递的是1000，那么秒数是10秒
*/
//这里写站长自己的处理代码，可以是前端代码也可以是传递参数给后台页面
}
```
调用示范：
```
```
$User.Visitor.SaveLvlCallBack=function(o){
  Ajax('/asp/SaveUserLevel.asp?UserName='+o.UserName+'&SunNum='+o.SunNum+'&Lvl='+o.Lvl+'&T='+(Math.floor(o.T/100)));
//其中Ajax为假设的自定义函数
}
```
