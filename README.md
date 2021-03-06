
# slidePage
Demo:http://lipten.link/projects/slidePage/demo.html?page=1

###-update-
新增url参数pege跳转指定页，优先于index参数.


###安装方法

####1、下载slidePage
利用bower安装
```
bower install slidePage
```
或者克隆到本地
```
git clone https://github.com/lipten/slidePage.git
```


####2、引用相关文件
```
<link rel="stylesheet" type="text/css" href="slidePage.css">        //插件必须样式
<link rel="stylesheet" type="text/css" href="page-animation.css">   //动画样式，可自己编写
```

####3、引用js文件
```
<script type="text/javascript" src="zepto.min.js"></script>         //zepto.js类库
<script type="text/javascript" src="slidePage.js"></script>         //slidePage主文件
```

####4、html结构
```
<div class="slidePage-container">
    <div class="item">
        <h2>page1</h2>
        <div class="step step1 fadeIn" data-delay="1000"></div>
        <div class="step step2 fadeIn"></div>
    </div>
    。。。
</div>
```


####5、初始化代码
```
slidePage.init();
```

## Doc
slidePage.init(options);

options:(default)

<pre>
{
    'index' : 1,
    'before' : function(index){},
    'after' : function(index){},
    'useArrow' : true,
    'useAnimation' : true,
    'useMusic' : {
        'autoPlay' : true,
        'loopPlay' : true,
        'src' : 'http://mat1.gtimg.com/news/2015/love/FadeAway.mp3'
    }
 };
</pre>
####index
初始进入的索引页面，值为1时从第一页开始，默认为1

####before
触发页面滚动前的回调，参数index为滚动前的页面索引号
####after
触发页面滚动后的回调，参数index为滚动后的页面索引号
####useArrow
使用自带样式的下箭头提示图标
####useAnimation
开启或关闭动画
####useMusic
使用音乐，并有音乐图标提示用户控制播放

###使用动画
<pre>
&lt;div class="step slideRight" data-delay="1300"&gt;&lt;/div&gt;
</pre>
在想要动画控制的元素上加上step类，并加上css动画类名即可使用动画，data-delay属性控制动画延时播放(默认为100毫秒);
此项目还为您准备了一套css动画：page-animation.css，可自由更改或添加您想要的动画，

####动效列表:
<pre>
[
    fadeIn,                 //渐显动画
    fadeFlash,              //闪烁动画
    flaxLine,               //伸展线条(基于父容器的宽度伸到100%)
    borderFlash,            //闪烁边框(红色边框)
    forceDown,              //重力砸下的动画(不是弹跳动画)
    slideLeft,              //从左边渐现移动出现
    slideRight,             //从右边渐现移动出现
    slideUp,                //从上边渐现移动出现
    slideDown,              //从下边渐现移动出现
    rotateIn,               //旋转渐现出现
    zoomIn,                 //缩放渐显出现
    heartBeat,              //若隐若现
    rollInLeft,             //从左边旋转渐现
    rollInRight             //从右边旋转渐现
]
</pre>
