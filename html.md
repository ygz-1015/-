[**网页HTML代码大全**](http://www.cnblogs.com/bile/archive/2012/08/15/2640276.html)

**1.****结构性定义**

文件类型 <HTML>（放在档案的开头与结尾）</HTML> 

文件主题 <TITLE></TITLE> （必须放在「文头」区块内）

文头 <HEAD></HEAD> （描述性资料，像是「主题」）

文体 <BODY></BODY> （文件本体）

（由浏览器控制的显示风格）

标题 <H1>（从1到6，有六层选择）</H1> （从1到6，有六层选择）

标题的对齐 <H? ALIGN=LEFT|CENTER|RIGHT></H?>

区分 <DIV></DIV>

区分的对齐 <DIV ALIGN=LEFT|RIGHT|CENTER|JUSTIFY></DIV>

引文区块 <BLOCKQUOTE></BLOCKQUOTE> （通常会内缩）

强调 <EM></EM> （通常会以斜体显示）

特别强调 <STRONG></STRONG> （通常会以加粗显示）

引文 <CITE></CITE> （通常会以斜体显示）

码 <CODE></CODE> （显示原始码之用）

样本 <SAMP></SAMP>

键盘输入 <KBD></KBD>

变数 <VAR></VAR>

定义 <DFN></DFN> （有些浏览器不提供）

地址 <ADDRESS></ADDRESS>

大字 <BIG></BIG>

小字 <SMALL></SMALL>

与外观相关的标签（作者自订的表现方式）

加粗 <B></B>

斜体 <I></I>

底线 <u></u> （尚有些浏览器不提供）

删除线 <S></S> （尚有些浏览器不提供）

下标 <SUB></SUB>

上标 <SUP></SUP>

打字机体 <TT></TT> （用单空格字型显示）

预定格式 <PRE></PRE> （保留文件中空格的大小）

预定格式的宽度 <PRE WIDTH=?></PRE>（以字元计算）

向中看齐 <CENTER></CENTER> （文字与图片都可以）

闪耀 <BLINK></BLINK> （有史以来最被嘲弄的标签）

字体大小 <FONT SIZE=?></FONT>（从1到7）

改变字体大小 <FONT SIZE=+|-?></FONT>

基本字体大小 <BASEFONT SIZE=?> （从1到7; 内定为3）

字体颜色 <FONT COLOR="#

$$"></FONT>



说明 <!-- *** --> （浏览器不会显示）

<!--修改滚动条-->

<style type="text/css">

body {

scrollbar-face-color: #330033;

scrollbar-shadow-color: #FFFFFF;

scrollbar-highlight-color: #FFFFFF;

scrollbar-3dlight-color: #FFFFFF;

scrollbar-darkshadow-color: #FFFFFF;

scrollbar-track-color: #330033;

scrollbar-arrow-color: #FFFFFF;

}

</style>

<!--修改滚动条结束-->

将上面的代码放在叶子代码的<head></head>之间,颜色可根据自己的需要修改。

滚动条的代码意思如下：

Scrollbar-Face-Color为滚动条表面颜色设定；

Scrollbar-Track-Color为滚动条底板颜色设定；

Scrollbar-Darkshadow为滚动条下边和右边边沿颜色设定；

Scrollbar-Highlight-Color为滚动条上斜面和左斜面颜色设定；

Scrollbar-Shadow-Color为滚动条下斜面和右斜面颜色设定；

Scrollbar-3Dlight-Color为滚动条上边和左边的边沿颜色设定；

Scrollbar-Arrow-Color为滚动条两端箭头颜色设定。

<!> 跑馬燈

<marquee>...</marquee>普通捲動

<marquee behavior=slide>...</marquee>滑動

<marquee behavior=scroll>...</marquee>預設捲動

<marquee behavior=alternate>...</marquee>來回捲動

<marquee direction=down>...</marquee>向下捲動

<marquee direction=up>...</marquee>向上捲動

<marquee direction=right></marquee>向右捲動

<marquee direction=’left’></marquee>向左捲動

<marquee loop=2>...</marquee>捲動次數

<marquee width=180>...</marquee>設定寬度

<marquee height=30>...</marquee>設定高度

<marquee bgcolor=FF0000>...</marquee>設定背景顏色

<marquee scrollamount=30>...</marquee>設定捲動距離

<marquee scrolldelay=300>...</marquee>設定捲動時間

1)贴图：<img src="图片地址"> 

2)加入连接：<a href="所要连接的相关地址">写上你想写的字</a> 

3)在新窗口打开连接：<a href="相关地址" target="_blank">写上要写的字</a> 

4)移动字体(走马灯)：<marquee>写上你想写的字</marquee> 

5)字体加粗：<b>写上你想写的字</b> 

6)字体斜体：<i>写上你想写的字</i> 

7)字体下划线: <u>写上你想写的字</u>

8)字体删除线: <s>写上你想写的字</s>

9)字体加大: <big>写上你想写的字</big> 

10)字体控制大小：<h1>写上你想写的字</h1> (其中字体大小可从h1-h5,h1最大，h5最小) 

11)更改字体颜色：<font color="#value">写上你想写的字</font>(其中value值在000000与ffffff(16位进制)之间 

12)消除连接的下划线：<a href="相关地址" style="text-decoration:none">写上你想写的字</a> 

13)贴音乐：<embed src="音乐地址" width="宽度" height="高度" autostart=false>  14)贴flash: <embed src="flash地址" width="宽度" height="高度"> 

15)贴影视文件：<img dynsrc="文件地址" width="宽度" height="高度" start=mouseover>  

16)换行：<br>

 17)段落：<p>段落</p> 

18)原始文字样式：<pre>正文</pre> 

19)换帖子背景：<body background="背景图片地址">

 20)固定帖子背景不随滚动条滚动：<body background="背景图片地址" body bgproperties=fixed> 

21)定制帖子背景颜色：<body bgcolor="#value">(value值见10) 

22)帖子背景音乐：<bgsound="背景音乐地址" loop=infinite> 

23)贴网页：<iframe. src="相关地址" width="宽度" height="高度"></iframe>

​	1、店铺音乐代码:音乐网址" loop="-1">

​	 2、图片制作代码：＜img src="这里放图片地址"＞

​	 3、公告图片代码：＜img border="0" src="这里放图片地址" /＞或＜img src="这里放图片地址"/＞

​	 4、悬浮挂饰代码：＜img src="这里放图片地址" style="left:20px; position: relative; top:0px" /＞

​	 5、商品分类代码:＜img src="这里放图片地址"/＞ 

​	6、字体大小代码:＜font size="2"＞这里放要处理的文字，可用3、4、5等设置大小＜/font＞

​	7、字体颜色代码:＜font color="red"＞这里放要处理的文字，可以换成blue,yellow等＜/font＞ 

​	8、文字链接代码:＜a href="网页地址"＞链接的文字，在分类栏里用时链接的网页地址必须缩短＜/a＞ 

​	9、移动文字代码:＜marquee＞从右到左移动的文字＜/marquee＞ 

​	10、背景音乐代码：＜bgsound loop="-1" src="这里放音乐地址"＞＜/bgsound＞ 

​	11、图片附加音乐代码：＜img border=0 src="这里放图片地址" dynsrc="这里放音乐地址"＞ 

​	12、浮动图片代码:＜img alt="1" height="150" src="这里放图片地址"/＞ 

公告图片的代码：公告挂饰：店铺分类代码:背景音乐代码：换行代码 计数器代码颜色代码： 1白色 #FFFFFF 2红色#FF0000 3绿色#00FF00 4蓝色#0000FF 5牡丹红#FF00FF 6青色 #00FFFF 7黄色#FFFF00 8黑色#000000 9海蓝#70DB93 10巧克力色#5C3317 11蓝紫色 #9F5F9F 12黄铜色#B5A642 13亮金色#D9D919 14棕色#A67D3D 15青铜色 #8C7853 162号青铜色 #A67D3D 17士官服蓝色 #5F9F9F 18冷铜色 #D98719 19铜色 #B87333 20珊瑚红 #FF7F00 21紫蓝色 #42426F 22深棕 #5C4033 23深绿 #2F4F2F 24深铜绿色 #4A766E 25深橄榄绿 #4F4F2F 26深兰花色 #9932CD 27深紫色 #871F78 28深石板蓝 #6B238E 29深铅灰色 #2F4F4F 30深棕褐色 #97694F 32深绿松石色 #7093DB 33暗木色 #855E42 34淡灰色 #545454 35土灰玫瑰红色 #856363 36长石色 #D19275 37火砖色#8E2323 38森林绿 #238E23 39金色 #CD7F32 40鲜黄色 #DBDB70 41灰色 #C0C0C0 42铜绿色 #527F76 43青黄色 #93DB70 44猎人绿 #215E21 45印度红 #4E2F2F 46土黄色 #9F9F5F 47浅蓝色 #C0D9D9 48浅灰色 #A8A8A8 49浅钢蓝色 #8F8FBD 59浅木色 #E9C2A6 60石灰绿色 #32CD32 61桔黄色 #E47833 62褐红色 #8E236B 63中海蓝色 #32CD99 64中蓝色 #3232CD 65中森林绿 #6B8E23 66中鲜黄色 #EAEAAE 67中兰花色 #9370DB 68中海绿色 #426F42 69中石板蓝色 #7F00FF 70中春绿色 #7FFF00 71中绿松石色 #70DBDB 72中紫红色 #DB7093 73中木色 #A68064 74深藏青色 #2F2F4F 75海军蓝 #23238E 76霓虹篮 #4D4DFF 77霓虹粉红 #FF6EC7 78新深藏青色 #00009C 79新棕褐色 #EBC79E 80暗金黄色 #CFB53B 81橙色 #FF7F00 82橙红色 #FF2400 83淡紫色 #DB70DB 84浅绿色 #8FBC8F 85粉红色 #BC8F8F 86李子色 #EAADEA 87石英色 #D9D9F3 88艳蓝色 #5959AB 89鲑鱼色 #6F4242 90猩红色 #BC1717 91海绿色 #238E68 92半甜巧克力色 #6B4226 93赭色 #8E6B23 94银色 #E6E8FA 95天蓝 #3299CC 96石板蓝 #007FFF 97艳粉红色 #FF1CAE 98春绿色 #00FF7F 99钢蓝色 #236B8E 100亮天蓝色 #38B0DE 101棕褐色 #DB9370 102紫红色 #D8BFD8 103石板蓝色 #ADEAEA 104浓深棕色 #5C4033 105淡浅灰色 #CDCDCD 106紫罗兰色 #4F2F4F 107紫罗兰红色 #CC3299 108麦黄色#D8D8BF 109黄绿色 #99CC32

简单常用HTML代码大全（修改网页必备）网页常用HTML代码大全 超链接，用的最多： 点击在当前页打开网站 <a href="http://www./">这是我的网站</a> 效果：[这是我的网站](http://wwv.renren.com/xn.do?ss=10791&rt=1)  点击弹出网站 <a href="http://www./" target="_blank">这是我的网站</a> <br>这个是向下一行，比如 欢迎光临我的网站<br>希望开心 演示效果就是： 欢迎光临我的网站 希望开心 <p>向下一大行，比如 欢迎光临我的网站<p>希望开心 演示效果就是： 欢迎光临我的网站 希望开心 <b>这是粗体字 比如 <b >我的网站</ b> 演示效果：**我的网站**  我的网站这是字体的颜色BLUE是蓝，RED是红 演示 忽视右键 <body > 或 <body style="overflow-y:hidden"> 如何几秒后转到别的页面？  <META. HTTP-EQUIV="Refresh" C>  点击关闭窗口 <a href="javascript.:top.window.close();">点击关闭窗口</a>！ 请问如何去掉主页右面的滚动条？ <body scroll="no"> <body style="overflow-y:hidden"> 如何做到让一个网页自动关闭. <html> <head> <OBJECT id=closes type="application/x-oleobject" classid="clsid:adb880a6-d8ff-11cf-9377-00aa003b7a11"> <param name="Command" value="Close"> </object> </head> <body > 这个窗口会在10秒过后自动关闭,而且不会出现提示. </body> 如何在不刷新页面的情况下刷新css? <style> button{ color:#000000;} </style> <button nclick=document.styleSheets[0].rules[0].style.color=''''red''''>点击按钮直接修改style标签里button选择符使按钮改为红色</button> 请问如何让网页自动刷新？  在head部记入<META. HTTP-EQUIV="Refresh" c>其中20为20秒后自动刷新，你可以更改为任意值。  如何让页面自动刷新？ 方法一，用refresh  HTML 代码片段如下: <head>  <meta. http-equiv="refresh" c> </head>  5表示刷新时间 [Ctrl+A 全部选择 提示:你可先修改部分代码，再按运行] 方法二，使用setTimeout控制  <img src=/logo.gif> <script> function rl(){ document.location.reload() } setTimeout(rl,2000) </script>  如何让超链接没有下划线 在源代码中的<HEAD>…</HEAD>之间输入如下代码： <style. type="text/css"> <!-- a { text-decoration: none} --> </style> 请问如何去掉IE的上下滚动条？ <body style=''''overflow:scroll;overflow-y:hidden''''> </body> 怎样才能把RealPlayer文件在网页做一个试听连接？  <embed height=25　src=51js.rm type=audio/x-pn-realaudio-plugin width=50 autostart="false" c> 如何用html实现浏览器上后退按钮的功能？ <a href="java script.:history.go(-1)">点击后退</a> 或者 <script> history.back() </script>  请问怎么在网页中改变鼠标的箭头形状？ HTML 代码片段如下: <body> <a href="#" style="cursor: auto;">auto</a><br> <a href="#" style="cursor: crosshair ">crosshair </a><br> <a href="#" style="cursor: default ">default </a><br> <a href="#" style="cursor: hand ">hand </a><br> <a href="#" style="cursor: move ">move </a><br> <a href="#" style="cursor: e-resize ">e-resize </a><br> <a href="#" style="cursor: ne-resize ">ne-resize </a><br> <a href="#" style="cursor: nw-resize">nw-resize</a><br> <a href="#" style="cursor: n-resize">n-resize</a><br> <a href="#" style="cursor: se-resize">se-resize</a><br> <a href="#" style="cursor: sw-resize">sw-resize</a><br> <a href="#" style="cursor: s-resize">s-resize</a><br> <a href="#" style="cursor: w-resize">w-resize</a><br> <a href="#" style="cursor: text">text</a><br> <a href="#" style="cursor: wait">wait</a><br> <a href="#" style="cursor: help">help</a><br> </body>  怎样不使用页面的缓存？即每一次打开页面时不是调用缓存中的东西 <META. HTTP-EQUIV=" ragma" C>  页面打开时自动弹出一个窗口的代码怎么写？ HTML 代码片段如下: <html> <head> <title>Untitled Document</title> <meta. http-equiv="Content-Type" c> <script. language="<B style="color:black;background-color:#A0FFFF">javascript</B>"> <!-- function MM_openBrWindow(theURL,winName,features) { //v2.0 　window.open(theURL,winName,features); } //--> </script> </head> <body bgcolor="#FFFFFF" text="#000000" > </body> </html> 如何让我的页面出现一个会讲话的小人？Merlin HTML 代码片段如下: <HTML> <HEAD> <TITLE>默林</TITLE> <META. http-equiv=Content-Type c> </HEAD> <BODY> <p><OBJECT id=sims classid=CLSID45FD31B-5C6E-11D1-9EC1-00C04FD7081F> 　</OBJECT>  　<SCRIPT> var MerlinID; var MerlinACS; sims.Connected = true; MerlinLoaded = LoadLocalAgent(MerlinID, MerlinACS); Merlin = sims.Characters.Character(MerlinID); Merlin.Show(); Merlin.Play("Surprised"); Merlin.Speak("大家好"); Merlin.Play("GestureLeft"); Merlin.Think("我是默林！"); Merlin.Play("leased"); Merlin.Think("可爱吗？"); Merlin.Play("GestureDown"); Merlin.Speak("哈哈！"); Merlin.Hide(); function LoadLocalAgent(CharID, CharACS){ LoadReq = sims.Characters.Load(CharID, CharACS); return(true); } </SCRIPT> </p> <p> </p> <p>看此效果必须装有office2000！！！</p> </BODY> </HTML> 在页面中如何加入不是满铺的背景图片,拉动页面时背景图不动  HTML 代码片段如下: <html><head> <STYLE> body　 {background-image:url(logo.gif); 　　　　 background-repeat:no-repeat; background-position:center } </STYLE> </head> <body bgproperties="fixed" > </body> </html> [Ctrl+A 全部选择 提示:你可先修改部分代码，再按运行] background-repeat:no-repeat; 是讓背景圖不占滿整個頁面 body bgproperties="fixed" 是拉動scroll時背景圖不動  文本输入框什么属性能实现不可输入？  HTML 代码片段如下: <input type="text" name="textfield" disabled> 或者 <input type="text" name="textfield" readonly> 如何禁止自己的页面在别人的框架里打开？ 把以下代码加至你的<head>区  <script> if (window.top!=self){  window.top.location=self.location } </script>  如何实现首页全屏幕显示？ HTML 代码片段如下: <html> <body><script. language="<B style="color:black;background-color:#A0FFFF">javascript</B>">  var coolw=642 var coolh=400 var coolhuang=window.open("http://www.","coolhuang","width="+coolw+",height="+coolh+", fullscreen=1,toolbar=0,location=0,directories=0,status=0,menubar=0,scrollbars=0,resizable=0")  window.close() </script></body></html>  如何监听一个窗口被关闭了？ HTML 代码片段如下: <body > 如何禁止Ctrl+N？  HTML 代码片段如下: <body nkeydown=return(!(event.keyCode==78&&event.ctrlKey))> 如何把页面加入用户的收藏夹？  HTML 代码片段如下: <a href="<B style="color:black;background-color:#A0FFFF">javascript</B>:window.external.AddFavorite(''''[http://www.](http://wwv.renren.com/xn.do?ss=10791&rt=1)'''',''''无忧脚本'''')">收藏无忧脚本</a> 如何在我的页面中加入背景音乐？  IE: <bgsound src="*.mid" loop=infinite> NS:<embed src="*.mid" autostart=true hidden=true loop=true> *.mid你的背景音乐的midi格式文件   关于页面转换效果 <meta. http-equiv="page-enter" c> 或  <meta. http-equiv="page-exit" c>  说明：Transition=23是随机效果，另可以选0-22任一数字固定某个效果  如何设定打开页面的大小 HTML 代码片段如下: <body ><!--(width，height)--> 怎样双击滚屏，单击停止？ HTML 代码片段如下: <html> <head> <title>新網頁1</title> </head> <body> <script. language"<B style="color:black;background-color:#A0FFFF">javascript</B>"> var currentpos,timer; function initialize() {  timer=setInterval("scrollwindow()",10); } function sc(){ clearInterval(timer); } function scrollwindow() {  currentpos=document.body.scrollTop; window.scroll(0,++currentpos);  if (currentpos != document.body.scrollTop) sc(); }  document.onmousedown=sc document.ondblclick=initialize </script> <p>a</p><p>a</p><p>a</p><p>aa</p><p>aa</p><p>aa</p> <p>aa</p><p>aa</p><p>aa</p><p>aa</p><p>aa</p><p>aa</p> <p>aa</p><p>aa</p><p>aa</p><p>aa</p><p>aa</p><p>aa</p> <p>aa</p><p>aa</p><p>aa</p><p>aa</p><p>a</p> </body> </html> 如何让body中的文字不被选中？  HTML 代码片段如下: <body  >aaa</body> 如何让弹出的窗口不能关闭？  在新开的窗口中加入如下代码 <body nunload=open(location.href)> </body>  如何让浏览器在保存页面时保存失败？ HTML 代码片段如下: <NOSCRIPT> <<B style="color:black;background-color:#ffff66">IFRAME</B> SRC="*.html"> </<B style="color:black;background-color:#ffff66">IFRAME</B>>  </NOSCRIPT>  表单中如何用图片按钮实现 reset? <html>  <head> <script> function aaa(){  document.forms[0].reset() } </script> </head>  <body> <form> <textarea rows="2" name="S1" cols="20"></textarea> <input type="submit" values="提交" name="B1"> <image src="logo.gif" nclick=aaa()> </form>  </body></html>

 

进入网页时弹出的信息对话框 <body > 关闭窗口后弹出对话框 <body > 
告别提示 <body nUnload= alert("再见，感谢你的访问！")>

只要你肯干,没有什么不能成功的.

1。忽视右键 　 <body ncontextmenu="return false"> 　 或 　 <body style="overflow-y:hidden"> 

2。加入背景音乐 　 IE:<bgsound src="*.mid" loop=infinite> 　 NS:<embed src="*.mid" autostart=true hidden=true loop=true> 　 </embed> 　 *.mid你的背景音乐的midi格式文件 *

*3。简单的window.open方法 　 <a href="#" 　 nclick="javascript:window.open(文件路径/文件名,newwindow, 　 toolbar=no,scrollbars=yes,resizable=no,top=0,left=0, 　 width=400,height=300);">文字或图片</a> 　 参数解释： 　 <SCRIPT. LANGUAGE="javascript"> js脚本开始； 　 window.open 弹出新窗口的命令； 　 文件路径/文件名 弹出窗口的文件名； 　 newwindow 弹出窗口的名字（不是文件名），非必须，可用空代替； 　 width=400 窗口宽度； 　 height=300 窗口高度； 　 top=0 窗口距离屏幕上方的象素值； 　 left=0 窗口距离屏幕左侧的象素值； 　 toolbar=no 是否显示工具栏，yes为显示； 　 menubar，scrollbars 表示菜单栏和滚动栏。 　 resizable=no 是否允许改变窗口大小，yes为允许； 　 location=no 是否显示地址栏，yes为允许； 　 status=no 是否显示状态栏内的信息（通常是文件已经打开），yes为允许； 　 </SCRIPT> js脚本结束 

*4。简单的页面加密 　 <script. LANGUAGE="javascript"> 　 <!-- 　 function loopy(){ 　　 var sWord =""; 　　 while(sWord!="login"){sWord=prompt("请输入你的登陆密码");} 　　 alert("登陆成功！"); 　 } 　 loopy() 　 //--> 　 </script> 

*5。拉动页面时背景图不动 　 <style> 　 body{background-image:url(logo.gif); 　 background-repeat:no-repeat;background-position:center} 　 </style> 

*6。让浏览器在保存页面时保存失败 　 <NOSCRIPT><iframe. src="*.html"></iframe></NOSCRIPT> 

7。随机替换图片 　 <script> 　 document.write(<img src="img/+parseInt(Math.random()*(5)) 　 +.gif"height="40" width="50"> 　 </script> 　 图片文件名为0.gif 1.gif 2.gif 3.gif 4.gif 

8。窗口定时关闭 　 先将如下代码网页文件的区： 　 <script. language="javascript"> 　 function closeit() { setTimeout("self.close()",10000) //毫秒 } 　 </script> 　 然后再在<body>标内加入如：<body nload="closeit()"> 

9。网页自动关闭 　 <html> 　 <head> 　 <object id=closes type="application/x-oleobject" 　 classid="clsid:adb880a6-d8ff-11cf-9377-00aa003b7a11"> 　 <param name="Command" value="Close"> 　 </object> 　 </head> 　 <body nload="window.setTimeout(closes.Click(),10000)"> 　 这个窗口会在10秒过后自动关闭,而且不会出现提示. 　 </body> 　 </html> 

10。网页自动刷新 　 在head部记入 　 <META. HTTP-EQUIV="Refresh" content="20"> 　 其中20为20秒后自动刷新，你可以更改为任意值。 

11。网页自动转页 　 <META. HTTP-EQUIV="Refresh" CONTENT="时间(秒);URL=地址"> 

12。保持layer在最前面，而不被Iframe、Object所覆盖 　 在Layer中再插Iframe. 或 Object 设z-Index值 　 <div z-Index:2><object xxx></object> ＃ 前面 　 <div z-Index:1><object xxx></object> ＃ 后面 　 <div id="Layer2" style="position:absolute; top:40;width:400px; 　 height:95px;z-index:2"> height=100% width=100%> 　 <iframe. width=0 height=0></iframe> 　 </div> 　 <div id="Layer1" style="position:absolute; top:50;width:200px; 　 height:115px;z-index:1"> 　 <iframe. height=100% width=100%></iframe> 　 </div> 

13。返回上一页 　 <a href=javascript:history.back(1)>『返回上一页』</a> 

14。关闭窗口 　 <a href=javascript:self.close()>『关闭窗口』</a> 

15。关于iframe的透明背景 　 <IFRAME. ID="iFrame1" SRC="iframe.htm" 　 allowTransparency="true" 　 style="background-color: green"></IFRAME> 

16. ncontextmenu="window.event.returnValue=false" 将彻底屏蔽鼠标右键      <table border ncontextmenu=return(false)><td>no</table> 可用于Table 
17. <body nselectstart="return false"> 取消选取、防止复制 
18. onpaste="return false" 不准粘贴 19.oncopy="return false;" ncut="return false;" 防止复制

 

20. <link rel="Shortcut Icon" href="favicon.ico"> IE地址栏前换成自己的图标

 

21. <link rel="Bookmark" href="favicon.ico"> 可以在收藏夹中显示出你的图标

 

22. <input style="ime-mode:disabled"> 关闭输入法

 

23. 永远都会带着框架 <script. language="JavaScript"><!-- if (window == top)top.location.href = "frames.htm"; //frames.htm为框架网页 // --></script>

 

24. 防止被人frame.

 

<SCRIPT. LANGUAGE=JAVASCRIPT><!-- if (top.location != self.location)top.location=self.location; // --></SCRIPT>

 

25. 网页将不能被另存为

 

<noscript><iframe. src=*.html></iframe></noscript>

 

26. 查看网页源代码

 

<input type=button value=查看网页源代码 onclick="window.location = "view-source:"+ "http://www.pconline.com.cn"">

 

27.删除时确认

 

<a href="javascript:if(confirm("确实要删除吗?"))location="boos.asp? &areyou=删除&page=1"">删除</a>

 

28.屏蔽功能键Shift,Alt,Ctrl <script> function look(){ 
if(event.shiftKey) alert("禁止按Shift键!"); //可以换成ALT　CTRL } 
document.onkeydown=look; </script> 

29. 网页不会被缓存 

<META. HTTP-EQUIV="pragma" CONTENT="no-cache"> <META. HTTP-EQUIV="Cache-Control" CONTENT="no-cache, must-revalidate"> <META. HTTP-EQUIV="expires" CONTENT="Wed, 26 Feb 1997 08:21:57 GMT"> 或者<META. HTTP-EQUIV="expires" CONTENT="0">

 

30.怎样让表单没有凹凸感？ <input type=text style="border:1 solid #000000"> 
或 <input type=text style="border-left:none; border-right:none; border -top:none; border-bottom: 1 solid #000000"></textarea> 
31.不要滚动条? 让竖条没有: <body style="overflow:scroll;overflow-y:hidden"> </body> 让横条没有: 
<body style="overflow:scroll;overflow-x:hidden"> </body> 
两个都去掉？更简单了 <body scroll="no"> </body>

 

32.怎样去掉图片链接点击后，图片周围的虚线？

 

<a href="#" nFocus="this.blur()"><img src="logo.jpg" border=0></a>

 

33.电子邮件处理提交表单

 

<form. name="form1" method="post" action="mailt****@***.com" enctype="text/plain"> <input type=submit> </form>

 

34.在打开的子窗口刷新父窗口的代码里如何写？ window.opener.location.reload()

 

35.如何设定打开页面的大小 <body nload="top.resizeTo(300,200);"> 
打开页面的位置<body nload="top.moveBy(300,200);">

 

36.在页面中如何加入不是满铺的背景图片,拉动页面时背景图不动 <STYLE> body 
{background-image:url(logo.gif); background-repeat:no-repeat; 
background-position:center;background-attachment: fixed} 
</STYLE>

 

37. 检查一段字符串是否全由数字组成 <script. language="Javascript"><!-- 

function checkNum(str){return str.match(//D/)==null} 
alert(checkNum("1232142141")) alert(checkNum("123214214a1")) // --></script>

 

38. 获得一个窗口的大小 document.body.clientWidth; document.body.clientHeight

 

39. 怎么判断是否是字符 if (/[^/x00-/xff]/g.test(s)) alert("含有汉字"); else alert("全是字符"); 

40.TEXTAREA自适应文字行数的多少 <textarea rows=1 name=s1 cols=27 npropertychange="this.style.posHeight=this.scrollHeight"> 
</textarea>

 

41. 日期减去天数等于第二个日期 <script. language=Javascript> function cc(dd,dadd) { //可以加上错误处理 var a = new Date(dd) a = a.valueOf() 

a = a - dadd * 24 * 60 * 60 * 1000 a = new Date(a) 
alert(a.getFullYear() + "年" + (a.getMonth() + 1) + "月" + a.getDate() + "日") 
} cc("12/23/2002",2) </script>

 

42. 选择了哪一个Radio <HTML><script. language="vc"> function checkme() for each ob in radio1 if ob.checked then window.alert ob.value 

next end function </script><BODY> <INPUT name="radio1" type="radio" value="style" checked>Style. <INPUT name="radio1" type="radio" value="barcode">Barcode <INPUT type="button" value="check" nclick="checkme()"> 
</BODY></HTML> 
43.脚本永不出错 <SCRIPT. LANGUAGE="JavaScript"> <!-- Hide function killErrors(){return true;} window.onerror = killErrors; // --> </SCRIPT>

 

44.ENTER键可以让光标移到下一个输入框 <input nkeydown="if(event.keyCode==13)event.keyCode=9">

 

45. 检测某个网站的链接速度： 把如下代码加入<body>区域中: <script. language=Javascript> tim=1 setInterval("tim++",100) b=1 var autourl=new Array() autourl[1]="[www.njcatv.net](http://wwv.renren.com/xn.do?ss=10791&rt=1)" 

autourl[2]="javacool.3322.net" autourl[3]="[www.sina.com.cn](http://wwv.renren.com/xn.do?ss=10791&rt=1)" 
autourl[4]="[www.nuaa.edu.cn](http://wwv.renren.com/xn.do?ss=10791&rt=1)" 
autourl[5]="[www.cctv.com](http://wwv.renren.com/xn.do?ss=10791&rt=1)" 
function butt(){ document.write("<form. name=autof>") for(var i=1;i<autourl.length;i++) document.write("<input type=text name=txt"+i+" size=10 value=测试中

 

……> =》<input type=text name=url"+i+" size=40> =》<input type=button value=GO

 

onclick=window.open(this.form.url"+i+".value)><br>") 
document.write("<input type=submit value=刷新></form>") } 
butt() function auto(url){ document.forms[0]["url"+b].value=url 
if(tim>200) {document.forms[0]["txt"+b].value="链接超时"} else 
{document.forms[0]["txt"+b].value="时间"+tim/10+"秒"} b++ } function run(){for(var i=1;i<autourl.length;i++)document.write("<img src=http://"+autourl+"/"+Math.random()+" width=1 height=1 nerror=auto("http://"+autourl+"")>")} run()</script> 

46. 各种样式的光标 auto ：标准光标 default ：标准箭头 hand ：手形光标 wait ：等待光标 text ：I形光标 vertical-text ：水平I形光标 no-drop ：不可拖动光标 not-allowed ：无效光标 

help ：?帮助光标 all-scroll ：三角方向标 move ：移动标 crosshair ：十字标 
e-resize n-resize nw-resize w-resize s-resize se-resize 
sw-resize

47、禁止鼠标右键，把Demo的图片全都设为表格的背景，表格的大小与图片的大小一样。这样做看起来是一样的，主要是防止鼠标经过图片时会出现另存的按钮。禁止鼠标右键的代码很简单：<script. LANGUAGE="JavaScript"> function click() { if (event.button==2) {alert('呵呵，不好意思，你甭想使用右键**图片：）'); } } document.onmousedown=click</script>





