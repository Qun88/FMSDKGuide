# Fengmap JavaScript SDK  开发指南

## 什么是FengMap JavaScript SDK

Fengmap JavaScript SDK是一套基于 WebGL 和 HTML5 技术的浏览器应用程序接口。您可以使用该 SDK 开发适用于 web 端的地图应用，通过调用地图接口，您可以轻松访问蜂鸟公开地图资源、私有云端地图资源、离线地图数据，快速构建功能丰富、交互性强、适用于各个行业的室内地图类应用程序，或者快速将室内地图集成到您的应用程序中。

如果您有移动端 webapp 开发需要，Fengmap JavaScript SDK还可以帮助您方便快速的开发适用于移动端浏览器、微信、QQ的应用程序，或者将室内地图完美的集成到您的 webapp 中。

## 基本

本指南是面向 Web 开发者在建立 Fengmap 地图应用时使用的快速入门指南。

## 准备开发环境

您可以下载安装并使用 Visual studio、Eclipse、Sublime Text、Webstorm 等常用web开发工具。

## 准备SDK

您可以从蜂鸟云平台相关下载中按需下载Fengmap JavaScript SDK开发资源，其中示例下载内容包括：地图显示、事件、覆盖物、控件、搜索、路径规划、模拟导航等。

可通过官网浏览在线体验：[在线体验](http://developer.fengmap.com/fmAPI/help-fmdemo.html#FMDemo) 参考相关功能

可通过下载链接：[SDK下载](http://developer.fengmap.com/develop-js-download.html)在相关页面获取最新版本及历史版本SDK

可通过在线接口文档链接：[在线接口文档](http://developer.fengmap.com/docs/js/v2.6.0_alpha/index.html)访问在线接口文档参考相关接口

## 基础数据下载及准备

通过资源下载，自用数据可付费后进行下载

## 获取FengMap SDK 密钥

### 密钥的意义

如需使用 Fengmap JavaScript SDK，您必须在蜂鸟云控制台上创建您的应用项目，并添加可用的JavaScript SDK密钥。您需要的SDK密钥类型是JavaScript SDK密钥。
请注意：

1、蜂鸟云平台中的一个应用程序对应唯一一个Fengmap JavaScript key以及应用名称（appName）且全平台唯一。

2、Fengmap JavaScript SDK 需验证 key 和 appName ，保证当前 web 应用程序运行的域名在该 key 对应的白名单内，同时当前web应用程序名称和 appName 一致，且该 web 应用程序使用的 Fengmap 地图为相应用户已发布的地图。

### 如何获取密钥(key)

可根据如下步骤获取Fengmap JavaScript SDK 密钥：

1.登录蜂鸟云账号。

![登录蜂鸟账号](\MarkdownPics\登录蜂鸟账号.png)

2.通过蜂鸟云 ->开发
-> 创建应用，创建一个新应用。如果您之前已经创建过应用，跳过这个步骤。

![通过蜂鸟云](\MarkdownPics\通过蜂鸟云.png)

3、在创建的应用上点击“添加key”按钮，在弹出的对话框中依次：输入key名称、选择SDK平台、输入白名单。如下图所示：

![在创建的应用上点击添加key](\MarkdownPics\在创建的应用上点击添加key.png)

4、完成对话框填写并阅读同意蜂鸟云服务条款之后，点击确定即可完成密钥申请。如下图所示：

![read2](\MarkdownPics\完成对话框填写并阅读2.png)

## 配置工程

开发者可通过 Sublime Text、Eclipse、Visual Studio等html文本编辑器编写 web 程序和站点。在项目中添加 Fengmap JavaScript SDK 文件，在页面代码中添加 fengmap.min.js 引用，结合HTML，JavaScript等前端技术即可实现对 Fengmap 地图web端的展示与应用等功能。本章节介绍使用 Fengmap JavaScript SDK 的开发流程。

### 创建web站点

该站点需包含以下文件：

• 存放 JavaScript SDK 库即 fengmap.min.js 的 lib 文件夹。
• 前端展示的html页面。
• 存储离线 Fengmap 数据文件夹data（可选文件，注：使用离线数据时候必须存在）。
下图为一个 helloFengMap 的站点目录结构示例：

![image](\MarkdownPics\helloFengMap的站点目录结构示例.png)

### 编写html页面代码

在 helloFengMap.html 页面引入Fengmap JavaScript SDK 库，并添加地图显示代码。可根据Hello Fengmap 指导编写简单显示fengmap地图页面代码。

## 发布站点

页面完成后发布至 tomcat 服务器或 IIS 服务器，浏览器中输入正确的地址即可浏览页面。

注：地图数据格式为*.fmap文件类型。主题数据是包含*.theme配置文件和*.fmi公共设施图标的文件夹。
如果站点发布到IIS或Tomcat时发生浏览错误，可以尝试设置站点的MIME类型解决。".fmap"的MIME类型为"application/octet-stream",".fmi"的MIME类型为"image/png",".theme"的MIME类型为"text/plain"。如下图所示：

![image](\MarkdownPics\注：地图数据格式为.png)

## 开发建议

指南中讲解详细程度很难照顾基础不同的开发者，阐述风格也很难兼容每个读者，但是案例源码都可以解决这些问题。对于初次使用FengMap SDK的开发者，一定要把案例源码和开发指南结合起来学习，这样才能更好的理解。

## 开发条件

本指南是面向 Web开发者在建立Fengmap地图应用时使用的快速入门指南。

## 引入方式

从 2.5 版本开始，Fengmap SDK 提供了新的模块化加载 Javascript 库文件的方式，您可根据项目的不同应用场景，有选择性的加载不同的模块，从而降低资源占用，提升加载效率。拆分后模块分别为核心模块（fengmap.core）、控件模块(fengmap.control)、计算模块（fengmap.analyze）和导航模块(fengmap.navi)。

### 模块化功能说明

核心模块 fengmap.core，使用 Fengmap SDK 所必须的核心功能模块，需要在其他模块前引用。包含常规渲染和数据解析，以及通用功能，如：地图显示、事件、覆盖物、搜索查询等功能，如果您的地图仅用于大屏展示，只引入核心模块即可满足需求；

计算模块 fengmap.analyze，及导航模块 fengmap.navi， 如果除基础展示外，还要使用路径分析计算、真实定位导航或模拟导航功能，必须再加载该模块；

控件模块 fengmap.control， 如果要使用 SDK 内置的地图控件，须在核心功能模块基础上加载该模块，主要包含楼层控件、指北针、相机切换、信息窗等控件；

### 常规页面引入方式

全模块引入方式

```javascript
<!-- 引入fengmap -->
<script src="lib/fengmap.core.min.js"></script>
<script src="lib/fengmap.control.min.js"></script>
<script src="lib/fengmap.analyzer.min.js"></script>
<script src="lib/fengmap.navi.min.js"></script>
```

地图核心组件引入方式

```javascript
<!-- 引入fengmap -->
<script src="lib/fengmap.core.min.js"></script>
```

地图控件模块引入方式

```javascript
<!-- 引入fengmap -->
<!--fengmap.control控件模块需依赖于fengmap.core模块使用-->
<script src="lib/fengmap.core.min.js"></script>
<script src="lib/fengmap.control.min.js"></script>
```

地图计算、导航模块引入方式

```javascript
<!-- 引入fengmap -->
<!--fengmap.analyzer计算模块、
    fengmap.navi导航模块一般组合使用，依赖于fengmap.core核心模块-->
<script src="lib/fengmap.core.min.js"></script>
<script src="lib/fengmap.analyzer.min.js"></script>
<script src="lib/fengmap.navi.min.js"></script>
```

### npm框架引入方式

Vue/React框架下的引入方式

```javascript
import fengmap from "fengmap";  //全量包
// or 按需引入
import fengmap from "fengmap/build/plugins/fengmap.core.min"; //核心包
import "fengmap/build/plugins/fengmap.control.min"; //控件
// 导航需要引入以下两个包：
import "fengmap/build/plugins/fengmap.analyzer.min"; //路径分析类
import "fengmap/build/plugins/fengmap.navi.min"; //导航类
```

## 浏览器支持

在浏览器中，Fengmap 可以使用 WebGL 来渲染场景。支持 Google Chrome 9+、Firefox 4+、Opera 15+、Safari 5.1+、Internet Explorer 11 和 Microsoft Edge。你可以点击[链接](https://caniuse.com/#feat=webgl)来查阅各个浏览器对 WebGL 的支持性。

如需在 CS 中应用 Fengmap 可以考虑内嵌一个浏览器到应用程序中，但是同样的内嵌的浏览器组件不推荐使用 IE 内核的浏览器，基于 WebGL 的情况不IE浏览器10.0以下的版本。

## 创建地图

### 初始化Fengmap SDK

引入 Fengmap JavaScript SDK 库，在您的地图展示页面文件中添加如下代码完成对 Fengmap SDK 的初始化：

```javascript
<script src="lib/fengmap.min.js">  </script>
```

### 设置地图容器

在地图展示页面中添加显示地图的页面元素。如下所示：

```javascript
<div id="fengMap"></div>
```

### 渲染地图

初始化FMMap对象，使用Fengmap JavaScript SDK 内默认的蜂鸟服务器上的地图和主题，并根据蜂鸟提供的地图数据ID打开地图。

```javascript
var fmapID = '10347'; //mapId
var map = new fengmap.FMMap({
    container: document.getElementById('fengMap'),
    appName:'蜂鸟研发SDK_2_0',           //开发者应用名称
    key:'57c7f309aca507497d028a9c00207cf8',  //开发者申请应用下web服务的key
});

//根据ID打开地图
map.openMapById(fmapID);
```

### 地图初始化参数

地图初始化参数配置示例

```javascript
    var mapOptions = {
                //必要，地图容器
                container: document.getElementById('fengMap'),
                //必要，地图应用名称，通过蜂鸟云后台创建
                appName: '蜂鸟研发SDK_2_0',
                //必要，地图应用密钥，通过蜂鸟云后台获取
                key: '57c7f309aca507497d028a9c00207cf8'
                //离线加载时地图数据位置
                //mapServerURL: './data/' + fmapID,
                //离线加载时地图主题数据位置
                //mapThemeURL: './data/theme',
                //设置主题，如不添加，默认2001
                defaultThemeName: '2001',
                //设置地图初始二维还是三维状态
                defaultViewMode: fengmap.FMViewMode.MODE_3D,
                //初始聚焦楼层ID
                defaultFocusGroup：1,
                //设置两楼层间的高度
                defaultGroupSpace: 20,
                //设置初始化比例尺
                defaultMapScale：800,
                //设置比例尺范围
                mapScaleRange:[600,1200],
                //对不聚焦图层启用透明设置 默认为true
                focusAlphaMode: true,
                //是否支持单击模型高亮，false为单击时模型不高亮
                modelSelectedEffect: false
                //设置倾斜角，默认倾斜角为60度
                defaultTiltAngle: 30
            };
```

具体可设定参数如下 :

| 属性名称         | 数据格式    | 描述                                                         |
| :--------------- | :---------- | :----------------------------------------------------------- |
| container        | HTMLElement | 加载地图html容器,必填。                                      |
| appName          | string      | 必填,可通过蜂鸟云平台->我的应用->创建应用                    |
| key              | string      | 必填,key可通过蜂鸟云平台->我的应用->创建应用->添加key添加    |
| mapServerURL     | string      | 设置地图数据的路径，如不设置，则从蜂鸟视图服务器上获取在线地图 |
| mapThemeURL      | string      | 设置主题数据的路径，如不设置，则从蜂鸟视图服务器上获取在线主题 |
| defaultThemeName | string      | 设置默认主题名称，默认为‘2001’，设置后主题对应文件夹路径为：options.mapThemeURL+options.defaultThemeName。 |
|useStoreApply|boolean|开启支持主题中模型的自定义样式，默认为true。  |
|defaultVisibleGroups|array | 初始显示楼层ID数组。 |
|defaultFocusGroup|int |初始聚焦楼层ID。 |
|defaultViewCenter|json|初始化地图中心点坐标。如：{x:12961580.734922647,y:4861883.567717729} |
|modelSelectedEffect|boolean|支持单击模型高亮，false为单击时模型不高亮 |
|modelHoverEffect|boolean|支持悬停模型高亮或拾取，false为悬停时模型不高亮。默认值：false |
|modelHoverTime|boolean |悬停时间触发时间，默认1000,参数数值表示毫秒时长。 |
|focusAlphaMode|boolean |是否对不聚焦图层启用透明设置 默认为true |
|focusAlpha|float|对不聚焦图层启用透明设置 默认为0.1。值范围为 0-1。此属性只有当options.focusAlphaMode = ture是有效 |
|focusAnimateMode|boolean|是否开启聚焦图层切换的动画显示。默认true |
|defaultViewMode|fengmap.FMViewMode|初始二维还是三维状态， | |fengmap.FMViewMode.MODE_2D&#124;&#124;fengmap.FMViewMode.MODE_3D ,默认3维显示。|
|viewModeAnimateMode|boolean|是否启用2D，3D模式切换时的动画效果。默认true |
|moveToAnimateMode|boolean|是否启用拾取地图物体时相机的移动动画效果。 默认true。 |
|scaleToAnimateMode|boolean|是否启用地图物缩放的动画效果。 默认true。 |
|defaultMapScaleLevel|number|设置地图初始显示比例尺级别。范围为1-29之间的整数值。如29级的比例尺为1:1厘米。 |
|mapScaleLevelRange|array|设置比例尺级别可缩放范围， 通常室内地图使用到的范围为16级到23级。即：[16,23]。 |
|defaultMapScale|number|设置地图初始显示自定义比例尺级别。如设置1000，为1:1000（厘米）的显示状态。defaultMapScale的优先级比defaultMapScaleLevel的优先级高。 |
|mapScaleRange|array|设置自定义比例尺范围，单位（厘米），如[200,4000]。 |
|compassOffset|array|设置初始指南针的偏移量，默认为[28, 20],左：28px,上：20px。 |
|compassSize|number |设置指南针大小,默认50px。 |
|defaultGroupSpace|number|设置初始地图的楼层间距,默认50。 |
|enabledPanRange|boolean|是否开启平移地图范围限制,默认为false |
|tile|boolean|是否访问分层数据,默认为false。 |
|defaultBackgroundColor|int | string|默认背景颜色: 0xff00ff, '#00ff00' |
|defaultBackgroundAlpha|int|默认背景透明度: 0 ~ 1 |
|defaultControlsPose|number|地图默认旋转角度，默认为-15度。 |
|defaultLabelLanguage|fengmap.FMLanguageType|默认label的语言类型，显示英文或者中文 |

## 地图加载

在地图加载时可通过离线加载或在线加载的形式区分进行地图加载，默认在线加载

### 在线加载

在线调用的方法无需设置相应的文件位置，通过配置mapID、appName地图应用名称及key地图应用密钥实现地图调用

### 离线加载

离线加载需指定地图数据所在的路径，建议放置于工程中data下，在mapOptions中通过指定mapurl、themeurl设定调用

```javascript
//地图数据位置
mapServerURL: './data/' + fmapID,
//主题数据位置
mapThemeURL: './data/theme',
```

## 添加控件

Fengmap JavaScript SDK 提供多个控件。控件与地图之间存在交互。

注：除指北针控件外，其余控件的创建都在loadComplete事件之后，因为控件需在地图加载完成后，才能与地图有交互。

### 楼层控件

Fengmap JavaScript SDK 提供两种类型的楼层切换控件，scrollGroupsControl和buttonGroupsControl。该两种楼层控件只在显示样式上有区别

创建楼层控件1（包括楼层按钮和单/多楼层切换按钮）

```javascript
//楼层控制控件配置参数
var ctlOpt = new fengmap.controlOptions({
    position: fengmap.controlPositon.RIGHT_TOP,//默认在右上角
    showBtnCount: 7,  //默认显示楼层的个数
    allLayer:false,   //初始是否是多层显示，默认单层显示
    needAllLayerBtn: true, //是否显示多层/单层切换按钮
    //位置x,y的偏移量
    offset: {
        x: -20,
        y: 20
    }
});
var groupControl;
//地图加载完成回掉方法
map.on('loadComplete', function () {
    //创建楼层(按钮型)，创建时请在地图加载后(loadComplete回调)创建。
    groupControl = new fengmap.scrollGroupsControl(map, ctlOpt);
});
```

 创建楼层控件2（只有楼层按钮，不带楼层切换按钮）

```javascript
//楼层控制控件配置参数
var ctlOpt = new fengmap.controlOptions({
    position: fengmap.controlPositon.RIGHT_TOP,//默认在右下角
    showBtnCount: 7,  //默认显示楼层的个数
    //位置x,y的偏移量
    offset: {
        x: -20,
        y: 20
    }
});
var groupControl;
//地图加载完成回掉方法
map.on('loadComplete', function () {
    //创建楼层(按钮型)，创建时请在地图加载后(loadComplete回调)创建。
    groupControl = new fengmap.buttonGroupsControl(map, ctlOpt);
});
```

楼层控件交互事件。楼层控件楼层变化时会回调楼层变化方法。该方法放在创建楼层控件之后。

```javascript
//通过楼层切换控件切换聚焦楼层时的回调函数
//groupControl 即为楼层控件对象
groupControl.onChange(function(groups,allLayer){
    //groups 表示当前要切换的楼层ID数组,
    //allLayer表示当前楼层是单层状态还是多层状态。
    //...
});
```

### 放大/缩小控件

Fengmap JavaScript SDK 提供放大、缩小控件，放大、缩小控件按钮点击时会根据比例尺级别放大和缩小地图，并提供回调方法。

 创建控件。参考代码如下：

```javascript
//放大、缩小控件配置
var ctlOpt1 = new fengmap.controlOptions({
    position: fengmap.controlPositon.LEFT_TOP, //位置 左上角
    //位置x,y的偏移量
    offset: {
        x: 20,
        y: 60
    }
});
//放大、缩小控件
//map为FMMap对象，初始化需在地图加载后完成。
var zoomControl = new fengmap.zoomControl(map, ctlOpt1);
```

控件交互，通过按钮放大、缩小控件进行放大、缩小时，会回调当前的比例尺级别。

```javascript
map.on('scaleLevelChanged', function (d) {
    console.log('当前级别：', map.scaleLevel);
});
```

### 单/多层楼层切换控件

Fengmap JavaScript SDK 提供单/多层楼层，通过该控件可操作地图的单层或多层显示，并回调方法，返回当前控件类型和对应的操作值。

创建控件。参考代码如下：

```javascript
//单/多层楼层控件配置
var toolControl = new fengmap.toolControl(map,{
    allLayer:false, //设置初始单楼层状态。
    viewModeButtonNeeded:false, //设置为false,表示只显示楼层切换按钮。
    //点击按钮的回调方法,返回type表示按钮类型,value表示对应的功能值
    clickCallBack:function(type,value){
        // console.log(type,value);
    }
});
```

### 2D/3D切换控件

Fengmap JavaScript SDK 提供2D、3D切换控件，通过控件可操作地图的2D或3D显示，并回调方法，返回当前控件类型和对应的操作值。

创建控件。参考代码如下：

```javascript
//2D、3D控件配置
var toolControl = new fengmap.toolControl(map,{
    init2D:false,   //初始化2D模式
    groupsButtonNeeded:false,   //设置为false表示只显示2D,3D切换按钮
    //点击按钮的回调方法,返回type表示按钮类型,value表示对应的功能值
    clickCallBack:function(type,value){
        // console.log(type,value);
    }
});
```

### 指北针控件

Fengmap JavaScript SDK 提供指北针控件，通过开关设置其显示或隐藏，默认隐藏，并监听指北针点击事件。
初始化指北针位置。参考代码如下：

```javascript
//初始化指北针位置
map = new fengmap.FMMap({
    container : document.getElementById('fengMap'),    //渲染dom
    compassOffset:[20,20],          //初始指北针的偏移量，[左，上]
    compassSize: 48,                //指北针大小默认配置
    appName:'蜂鸟研发SDK_2_0',               //开发者申请应用名称
    key:'57c7f309aca507497d028a9c00207cf8',  //开发者申请应用下web服务的key
});
```

显示指北针。参考代码如下：

```javascript
//显示指北针
map.showCompass = compassVisible;
```

点击指北针事件。参考代码如下：

```javascript
// 如：点击指南针事件, 使角度归0
map.on('mapClickCompass', function() {
       map.rotateTo({
        to: 0,           //设置角度
        duration: .3,      //动画持续时间，默认为。3秒
        callback: function() {             //回调函数
            // console.log('rotateTo complete!');
        }
    })
});
```

### 气泡信息框

Fengmap JavaScript SDK 提供气泡信息框功能，根据传入的地图坐标或屏幕坐标在地图相应位置添加气泡信息框,气泡信息框里的内容可自定义填充HTML元素。

初始化气泡信息框。参考代码如下：

```javascript
//信息框控件大小配置
var ctlOpt = new fengmap.controlOptions({
    mapCoord: {
        //设置弹框的x轴
        x: event.target.x,
        //设置弹框的y轴
        y: event.target.y,
        //设置弹框位于的楼层
        groupID: 1
    },
    //设置弹框的宽度
    width: 200,
    //设置弹框的高度
    height: 100,
    marginTop: 10,
    //设置弹框的内容
    content: '这是一个信息框'
});
```

显示气泡信息框。参考代码如下：

```javascript
//添加弹框到地图上
var popMarker = new fengmap.FMPopInfoWindow(map, ctlOpt);
```

关闭气泡信息框。参考代码如下：

```javascript
// 关闭气泡信息框。
popMarker.close();
```

### 自定义控件

Fengmap JavaScript SDK 地图支持自定义组件供实现相关功能

自定义组件添加：

```javascript
    <div id="btnsSwitch" class="btnsSwitch">
        <span onClick="changeMode(this)"></span>
    </div>
```

自定义组件功能实现：

```javascript
    function changeMode(domObj) {
        if (planarFlag) {
            //切换地图为三维模式
            if (map) {
                map.viewMode = fengmap.FMViewMode.MODE_3D;
            }
        } else {
            //切换地图为二维模式
            if (map) {
                map.viewMode = fengmap.FMViewMode.MODE_2D;
            }
        }
    }
```

## 地图操作相关事件

Fengmap JavaScript SDK 地图事件有地图加载完成事件、点击事件、缩放级别事件、地图状态更新事件等。

### 地图加载完成事件

地图在完成对fmap地图文件的渲染后回调loadComplete事件，该事件表示地图已渲染完成。注：地图渲染完成后调用地图方法获取或设置地图状态生效，若在loadComplete之前改变地图的状态可能不生效。事件代码如下：

```javascript
// 地图加载完成事件
map.on('loadComplete', function() {
  console.log('Map loadComplete!');
});
```

### 精模加载完成事件

地图内存在精细化模型时，地图在完成对精模文件的渲染后回调gltfLoaded事件，该事件表示精模已在家完成，代码如下：

```javascript
// 精模加载完成事件
map.on('gltfLoaded', function() {
  console.log('gltf in Map loadComplete!');
});
```

## 操作地图

### 点击事件

地图点击事件会监听地图中所有地图元素，当点击某个地图元素的时候，会返回拾取到的地图元素对象。

```javascript
//点击地图事件
map.on('mapClickNode', function (event) {
    var clickedObj = event.target;
    switch (target.nodeType) {
        case fengmap.FMNodeType.FLOOR:
            break;
        case fengmap.FMNodeType.MODEL:
            break;
        case fengmap.FMNodeType.IMAGE_MARKER:
            break;
        case fengmap.FMNodeType.TEXT_MARKER:
            break;
        case fengmap.FMNodeType.POLYGON_MARKER:
            break;
        case fengmap.FMNodeType.FACILITY:
            break;
    }
});
```

### 缩放级别事件

当缩放地图时，Fengmap JavaScript SDK 提供监听缩放事件。 如下所示：

```javascript
// 地图缩放级别变化事件，返回当前level值，level范围为1-29
map.on('mapScaleLevelChanged', function(level) {
  console.log('map scaleLevel Changed!',level);
});
```

### 地图状态更新事件

Fengmap JavaScript SDK 提供地图状态更新事件，即每次地图状态的更新即会回调此事件。设置如下：

```javascript
var callback = function() {
    //刷新地图后操作
};
// 监听地图状态更新事件
map.on('update', callback);
// 移除监听地图状态更新事件
map.off('update', callback);
```

### 楼层切换事件

楼层控件交互事件。楼层控件楼层变化时会回调楼层变化方法。该方法放在创建楼层控件之后。

```javascript
//通过楼层切换控件切换聚焦楼层时的回调函数
//groupControl 即为楼层控件对象
groupControl.onChange(function(groups,allLayer){
    //groups 表示当前要切换的楼层ID数组,
    //allLayer表示当前楼层是单层状态还是多层状态。
    //...
});
```

## 地图数据查询

Fengmap JavaScript SDK支持对数据模型（Model）、公共设施(facility)、自定义标注(Marker)等地图元素的搜索分析。本模块是对查询地图元素的调用接口说明。

### 信息查询

Fengmap JavaScript SDK支持对数据模型（Model）、公共设施(facility)、自定义标注(Marker)等地图元素的搜索分析。本模块是对查询地图元素的调用接口说明。

### 创建搜索分析对象

获取地图加载后搜索分析属性即可

```javascript
var searchAnalyser = new fengmap.FMSearchAnalyser(map);
```

### 创建搜索请求体对象

通过搜索体对象，用户可以设置一个或多个检索条件，如楼层条件（groupID），类型条件（type）,ID条件（ID）等。

```javascript
//默认针对所有类型的地图元素的查询
var searchReq = new fengmap.FMSearchRequest();
```

groupID查询

```javascript
searchReq.groupID = 1; //查询出楼层ID= 1的所有地图元素，包括model,label,facility,marker等。

```

FID查询。根据FID查询如果匹配，结果有且只有1条记录

```javascript
searchReq.FID = '10347018'; //查询出所有楼层的地图元素中FID= '10347018'的对象,FID为地图内唯一标识。
```

name查询

```javascript
searchReq.name = 'APPLE'; //查询出所有楼层的地图元素中name='APPLE'的对象集合。
```

keyword查询

```javascript
searchReq.keyword = 'APP'; //查询出所有楼层的地图元素中name包含'APP'的对象集合。
```

TypeID查询公共设施

```javascript
searchReq.typeID = '190000'; //查询出所有楼层的地图元素中typeID='190000'的对象集合。
```

组合查询

```javascript
searchReq.groupID = 1;
searchReq.name = 'APPLE'; //查询元素groupID=1,且元素name值为'APPLE'的地图元素
```

### 查询分析

搜索分析对象执行query方法，传入分析参数对象，返回查询结果。代码如下所示：

```javascript
searchAnalyser.query(searchReq, function(result) {
    //result 为查询到的结果集。
    console.log(result);
});
```

## 周边检索

Fengmap JavaScript SDK提供周边查询的功能。本模块是对周边查询的调用接口说明。

### 初始化数据

周边检索方法需提供查询范围中心点、查询范围半径等参数。示例如下：

```javascript
//查询的楼层id
searchRequest.groupID = 1;
searchRequest.circle = {
    //查询范围中心点坐标
    center:{
        x: map.center.x,
        y: map.center.y
    },
    radius: 50  //查询范围半径
};
```

### 执行周边检索

搜索分析对象执行query方法。示例如下：

```javascript
sortRes = searchAnalyser.getQueryResult(searchRequest,["SINGLE","POLYGON"],map);
```

### 自有数据检索

Fengmap JavaScript SDK支持对数据模型（Model）、公共设施(facility)、自定义标注(Marker)等地图元素的搜索分析。自有数据的查询是您的业务数据。可通过地图数据内的某个字段与自有数据相关联，分两步查询：第一步先查询地图数据；第二步在根据地图数据关联业务数据字段查询对应自有数据。

注：本示例以*.fmap数据中的FID字段与自有数据中的FID关联为例，实际中也可通过其他字段关联与地图中的FID字段关联。地图中的FID字段为全地图唯一标识。

创建搜索分析对象

地图加载完成后向创建FMSearchAnalyser

```javascript
var searchAnalyser = new fengmap.FMSearchAnalyser(map);
```

创建搜索请求体对象

通过搜索体对象，如搜索FID=10347012的模型数据，设置如下所示：

```javascript
//默认针对所有类型的地图元素的查询
var searchReq = new fengmap.FMSearchRequest();
//查询出所有楼层的地图元素中FID= '10347012'的对象,根据FID查询如果匹配，结果有且只有1条记录。
searchReq.FID = '10347012';
```

### 地图数据查询分析

搜索分析对象执行query方法，传入分析参数对象，返回查询结果。代码如下所示：

```javascript
searchAnalyser.query(searchReq, function(result) {
    //result 为查询到的结果集。
    console.log(result);
});
```

### 自有数据查询分析

在地图数据查询分析的结果中得到数据的FID，做二次查询，比对自有数据的FID和数据中FID对应的条目得到自由数据匹配的结果。代码如下所示：

```javascript
//自有Json数据如下：
var data = [{
        "FID": "10347012",
        "NAME": "VANS",
        "TYPE": "100100",
        "FLOOR": "F1",
        "GROUP": "1"
    },
    {
        "FID": "10347013",
        "NAME": "茜丽杯子蛋糕",
        "TYPE": "170000",
        "FLOOR": "F1",
        "GROUP": "1"
    },
    {
        "FID": "10347015",
        "NAME": "LOHO",
        "TYPE": "190000",
        "FLOOR": "F1",
        "GROUP": "1"
    }];

//查询分析 根据FID只有1条结果对应
searchAnalyser.query(searchReq, function(result) {
    //result 为查询到的结果集。
    console.log(result);
    var model = result[0];
    for(var i = 0,len = data.length; i < len; i++)
    {
        if(data[i].FID==fid){
        //输出匹配到的自有数据
        console.log(data[i]);
        }
    }
});
```

## 添加/管理覆盖物

### 点标注

Fengmap JavaScript SDK 提供根据地图坐标点添加标注的功能。点标注可分为文字标注（TextMarker）、图片标注（ImageMarker）、定位标注（LocationMarker）。

### 文字标注

文字标注是用户可在指定坐标点位置添加自定义的文字。文字标注针对楼层的，添加文字标注需要三个参数：groupID（楼层ID）、x(地图坐标x)、y(地图坐标y),具体操作步骤如下：

添加文字标注前需要先获取指定楼层：

```javascript
var groupLayer = map.getFMGroup(groupID);
```

创建文字标注层并添加至指定楼层:

```javascript
var layer = new fengmap.FMTextMarkerLayer();   //实例化TextMarkerLayer
groupLayer.addLayer(layer);    //添加文本标注层到模型层。否则地图上不会显示
```

最后在文字标注层上添加文字标注（单个或多个）。

```javascript
//图标标注对象，默认位置为该楼层中心点
var tm = new fengmap.FMTextMarker({
    name: "这是一个文字标注",
    x: x,
    y: y,
    //文字标注样式设置
    fillcolor: "255,0,0", //填充色
    fontsize:20, //字体大小
    strokecolor: "255,255,0", //边框色
    alpha: 0.5   //文本标注透明度
});
layer.addMarker(tm);  //文本标注层添加文本Marker
tm.alwaysShow();    // 在marker载入完成后，设置 "一直可见"，不被其他层遮挡
```

### 图片标注

图片标注是用户可在指定坐标点位置添加自定义的图片标识。图片标注针对楼层，图片标注需要三个参数：groupID（楼层ID）、x(地图坐标x)、y(地图坐标y),具体操作步骤如下：

添加文字标注前需要先获取指定楼层。

```javascript
var groupLayer = map.getFMGroup(groupID);
```

创建图片标注层并添加到指定楼层上面。

```javascript
var layer = new fengmap.FMImageMarkerLayer();   //实例化ImageMarkerLayer
groupLayer.addLayer(layer);    //添加图片标注层到模型层。否则地图上不会显示
```

最后在图片标注层上添加图片标注（单个或多个）。

```javascript
//图标标注对象，默认位置为该楼层中心点
var im = new fengmap.FMImageMarker({
    x:x,
    y:y,
    url:'image/blueImageMarker.png',       //设置图片路径
    size:64,                               //设置图片显示尺寸
    height: 4                              //标注高度，大于model的高度
});
layer.addMarker(tm);  //图片标注层添加图片Marker
im.alwaysShow();  // 在图片载入完成后，设置 "一直可见"，不被其他层遮挡
```

### 定位标注

定位标注是用户可在指定坐标点位置添加自定义的图片标注。图片标注针对地图，一个地图可以添加多个定位标注。一般定位标注用于导航过程中位置的标识。添加定位标注需要三个参数：groupID（楼层ID）、x(地图坐标x)、y(地图坐标y)，具体步骤如下：

实例化定位标注对象。

```javascript
var locationMarker = new fengmap.FMLocationMarker({
    url:'image/pointer.png',
    size:86,  //设置图片显示尺寸
    height:10  //marker标注高度
});
```

添加定位标注对象到地图对象中。

```javascript
map.addLocationMarker(locationMarker);
```

设置定位标注在地图中的位置。

```javascript
locationMarker.setPosition({
    x:x,  //设置定位点的x坐标
    y:y,  //设置定位点的y坐标
    groupID:groupID  //设置定位点所在楼层
});
```

### 线标注

Fengmap JavaScript SDK 支持绘制线操作。用户可根据坐标点集绘制折线。

```javascript
var line = new fengmap.FMLineMarker();
//创建FMSegment点集，一个点集代表一条折线
var seg = new fengmap.FMSegment();
seg.groupId = gid;
seg.points = points;
//将FMSegment绘制到线图层上
line.addSegment(seg);
```

配置线型，颜色、线宽、透明度等

```javascript
var lineStyle = {
     //设置线的宽度
     lineWidth: 5,
     //是否开启平滑线功能
     smooth: true,
     //设置FMARROW线型线的颜色，十六进制颜色值
     //godColor: '#FF0000',
     //设置FMARROW线型线边线的颜色,十六进制颜色值
     //godEdgeColor: '#FF0000',
     //设置线的类型为导航线
     lineType: fengmap.FMLineType.FMARROW,
     //设置线上纹理贴图
     lineStyle.mapUrl：'./images/dash.png',
     noAnimate: true
                };
```

添加线标注至对应层

```javascript
//绘制线
map.drawLineMark(line, lineStyle);
```

### 面标注

Fengmap JavaScript SDK 支持自定义绘制图形，包括自定义绘制多边形、圆、矩形等图形。

### 多边形标注

Fengmap JavaScript SDK 支持绘制多边形操作。用户可根据坐标点集绘制多边形，注：多边形是针对楼层的，每一楼层可包含多个多边形。绘制多边形步骤如下：

添加模拟点坐标。

```javascript
//创建自定义多边形形状PolygonMarker所需的顶点数组
var coords=[ {x: 12961583, y: 4861865, z: 56},
    {x: 12961644, y: 4861874, z: 56},
    {x: 12961680, y: 4861854, z: 56},
    {x: 12961637, y: 4861819, z: 56},
    {x: 12961590, y: 4861835, z: 56}
];
```

创建多边形图层并添加到指定楼层上面。

```javascript
var groupLayer=map.getFMGroup(1);
//创建PolygonMarkerLayer
var layer =new fengmap.FMPolygonMarkerLayer();
groupLayer.addLayer(layer);
```

在多边形图层上面添加多边形标注。

```javascript
var polygonMarker = new fengmap.FMPolygonMarker({
    alpha: .5,             //设置透明度
    lineWidth: 1,      //设置边框线的宽度
    height: 6,    //设置高度*/
    points: coords //多边形坐标点
});

layer.addMarker(polygonMarker);  //文本标注层添加文本Marker
```

### 圆形标注

Fengmap JavaScript SDK 支持绘制圆形操作。用户可根据中心点坐标和半径绘制圆形，注：多边形是针对楼层的，每一楼层可包含多个多边形。绘制圆形步骤如下：

创建多边形图层并添加到指定楼层上面。

```javascript
var groupLayer=map.getFMGroup(1);
//创建PolygonMarkerLayer
var layer =new fengmap.FMPolygonMarkerLayer();
groupLayer.addLayer(layer);
```

在多边形图层上面添加圆形标注。

```javascript
var circleMarker = new fengmap.FMPolygonMarker({
    color: '#3CF9DF',  //设置颜色
    alpha: .3,             //设置透明度
    lineWidth: 3,      //设置边框线的宽度
    height: 6,  //设置高度
    //设置为圆形
    points:{
        type:'circle', //设置为圆形
        center: {x: 1.2961644E7, y: 4861874.0}, //设置此形状的中心坐标
        radius: 30,//设置半径
        segments: 40,//设置段数，默认为40段
    }
});

layer.addMarker(circleMarker);  //多边形图层上面添加圆形标注
```

### 矩形标注

Fengmap JavaScript SDK 支持绘制矩形操作。用户可根据中心点坐标和矩形高、宽绘制矩形，注：矩形是针对楼层的，每一楼层可包含多个矩形。绘制矩形步骤如下：

添加矩形中心点坐标和高宽。

```javascript
//创建自定义矩形PolygonMarker所需的中心点坐标和半径
var centerPnt = {x:1.2961583E7,y:4861865.0};
var w = 30,h = 30;
```

创建矩形图层并添加到指定楼层上面。

```javascript
var groupLayer=map.getFMGroup(1);
//创建PolygonMarkerLayer
var layer =new fengmap.FMPolygonMarkerLayer();
groupLayer.addLayer(layer);
```

在矩形图层上面添加矩形标注。

```javascript
var rectangleMarker = new fengmap.FMPolygonMarker({
    color: '#9F35FF',  //设置面颜色
    alpha: .3,             //设置透明度
    lineWidth: 1,      //设置边框线的宽度
    height: 6,  //设置高度
    points:{
        type: 'rectangle', //设置为矩形
        center: centerPnt,  //设置此形状的中心坐标
        width: w,
        height: h
    }
});
layer.addMarker(rectangleMarker);  //多边形图层上面添加矩形标注
```

面域设置颜色修改

上述的多边形、圆形、矩形面域在创建后可通过FMPolygonMarker下的方法对已创建的面域进行面颜色、边线颜色及面透明度和线宽进行修改

```javascript
rectangleMarker.setColor('#ff6622');//设置面域颜色
rectangleMarker.setLineColor('#FF00FF');//设置面域边线颜色
rectangleMarker.setAlpha(0.5);//设置面域透明度
rectangleMarker.setLineWidth(1);//设置面域边线宽度
```

### 热力图

Fengmap JavaScript SDK 提供绘制热力图功能。热力图是根据由多个地图坐标点及对应点的value值生成的可反映某种特性分布的图形。 生成热力图可分为以下几步：

创建热点数据

```javascript
//模拟的热点数据
var data = [
    {
        "x": 12961664.4327246,//坐标X
        "y": 4861863.64318839,//坐标Y
        "value": 100//热力值
    }, {
        "x": 12961625.166912202,
        "y": 4861878.46667244,
        "value": 50
    }, {
        "x": 12961593.651145201,
        "y": 4861879.42299472,
        "value": 50
    },  {
        "x": 12961616.4728035,
        "y": 4861857.492644815,
        "value": 100
    }
]
```

创建热力图对象，并添加热力点

```javascript
//热力图对象
var heatmapInstance = fengmap.FMHeatMap.create(map, {
    //热点半径
    radius: 20,
    //热力图透明度
    opacity: 0.5,
    //热力点value的最大值
    max: 100
    //渐变色值，可配置
    gradient: {
        0.00: "rgb(0,0,0)",
        0.25: "rgb(0,0,255)",
        0.50: "rgb(0,255,0)",
        0.75: "rgb(255,255,0)",
        1.00: "rgb(255,0,0)"
    }
});
//批量增加热点
heatmapInstance.addPoints(data);
```

应用热力图到指定楼层

```javascript
//热力图应用到对应楼层
var groupLayer = map.getFMGroup(map.focusGroupID);
groupLayer.applyHeatMap(heatmapInstance);
```

### DOM对象

Fengmap JavaScript SDK 提供添加自定义DOM 地图覆盖物到地图上。 用户可引入外部GIF文件，VIDEO文件，等做为DOM对象添加至地图中，添加DOM对象可分为如下几步：

添加DOM对象需先获取指定层。

```javascript
var groupLayer = map.getFMGroup(groupID)
```

创建domMarker图层并添加到指定楼层上面。

```javascript
//创建DomMarkerLayer
var dmLayer =new fengmap.FMDomMarkerLayer();
groupLayer.addLayer(dmLayer);
```

创建DOM对象。

```javascript
var domMarker = new fengmap.FMDomMarker({
  x: map.center.x + zf_x * Math.random() * 40,
  y: map.center.y + zf_y * Math.random() * 40,
  height: 5,
  domWidth: '30',
  domHeight: '30',
  domContent: '<div class="domContainer"><div class="dot"></div><div class="pulse"></div><div class="pulse-big"></div></div>',
  anchor: fengmap.FMMarkerAnchor.BOTTOM
 });
dmLayer.addMarker(domMarker);
```

### 动态模型对象

Fengmap JavaScript SDK 提供添加动态模型对象。 DOM对象可分为以下几步：

添加DOM对象需先获取指定层。

```javascript
//创建DomMarkerLayer
dmLayer = map.getFMGroup(map.focusGroupID).getOrCreateLayer('dynmodel');
```

创建domMarker图层并添加到指定楼层上面。

```javascript
 /* 添加模型 */
            dmMarker = new fengmap.FMDynamicModel(map, {
                //model路径
                url: './glb/fengniao.glb',
                //初始化模型展示比例
                scale: 5,
                //model坐标
                coord: initCoord,
                //更新过程回调
                update: function () { },
                //model加载完成回调函数
                callback: function () {
                console.log('动态模型加载完成回调！');
                //开始播放模型对象的骨骼动画
                dmMarker.startAction(dmMarker.getActionList()[0]);
                }
            });

```

添加动态模型

```javascript
//添加动态模型
dmLayer.addNodes(dmMarker);
```

## 定位坐标转换

在使用真实的定位系统时，如：WIFI定位，蓝牙定位等，就需要将定位系统所返回的定位坐标转化为fengmap地图坐标，这样就可以在fengmap地图中去根据真实的定位点去实时的改变地图中的Marker的位置。实现定位的功能。

Fengmap JavaScript SDK 中提供了一个专用于坐标转化的通用类fengmap.FMMapCoordTransformer类。它的应用逻辑是这样的，在定位系统中提取出定位区域矩形的4个角点。同时在fengmap地图中得到这4个角点对点的地图坐标。就可以实现定位坐标到地图坐标的转化。

### 创建转换器

```javascript
var trasformer = new fengmap.MapCoordTransform(locOrigion,locRange,mapParas);
```

### 转换器参数

```javascript
//来自定位系统的参数 定位的原点坐标 已经定位的范围,(矩形对角线的2个点)
var locOrigion = {'x':0,'y':0};//定位坐标原点
var locRange = {'x':100,'y':200};//定位范围
//根据定位四个角点的地图坐标点
var mapParas = [];
mapParas[0]={'x':13502836.4878,'y':3658566.5691};//定位原点地图坐标
mapParas[1]={'x':13503636.768,'y':3657259.108};//X轴终点地图坐标
mapParas[2]={'x':13502783.8819,'y':3656737.0984};//定位原点对角点地图坐标
mapParas[3]={'x':13501983.572,'y':3658044.467};//Y轴终点地图坐标
```

### 坐标转换

```javascript
//定位系统中的定位坐标
    var loc ={'x':45,'y':150}; //定位系统所返回的坐标点
//转换后的地图坐标
    var mapCoord = trasformer.transform(loc);
```

## 路径规划与导航

### 路径规划

Fengmap JavaScript SDK支持根据起点和终点坐标规划路线功能。

### 初始化路径分析对象

设置起、终点，在地图渲染后即loadComplete回调后，初始化路径分析对象。示例代码如下：

```javascript
//创建路径分析对象
var  naviAnalyser = new fengmap.FMNaviAnalyser();
//通过已加载的地图数据加载模型
naviAnalyser.init(map);//注意：此方法需保证map数据已加载完成，可在map的loadComplete事件后调用

//添加模拟起、终点
var naviCoords = [{
    x: 12961588.0371617,
    y: 4861847.72571208,
    groupID:6
},{
    x: 12961587.6306147,
    y: 4861847.72571208,
    groupID:6
};
```

### 路径分析

根据设置的起、终点和起、终点楼层进行路径分析，分析成功，返回路径经过的坐标点集。

```javascript
//根据已加载的fengmap.FMMap导航分析，判断路径规划是否成功
var analyzeNaviResult = naviAnalyser.analyzeNavi(naviCoords[0].groupID, naviCoords[0], naviCoords[1].groupID, naviCoords[1], fengmap.FMNaviMode.MODULE_SHORTEST);
if (fengmap.FMRouteCalcuResult.ROUTE_SUCCESS != analyzeNaviResult) {
    return;
}
//获取路径分析结果对象，所有路线集合
var results = naviAnalyser.getNaviResults();
//初始化线图层
var line = new fengmap.FMLineMarker();
for (var i = 0; i < results.length; i++) {
    var result = results[i];
    //楼层id
    var gid = result.groupId;
    //路径线点集合
    var points = result.getPointList();

    var points3d = [];
    points.forEach(function (point) {
        points3d.push({
            //x坐标点
            'x': point.x,
            //y坐标点
            'y': point.y,
            //线标注高度
            'z': 1
        });
    });
    //fengmap.FMSegment点集，一个点集代表一条折线
    var seg = new fengmap.FMSegment();
    seg.groupId = gid;
    seg.points = points3d;
    line.addSegment(seg);
}
//绘制线
//配置线型、线宽、透明度等
var lineStyle = {
    //设置线的宽度
    lineWidth: 6,
    //设置线的透明度
    alpha: 0.8,
    //设置线的类型为导航线
    lineType: fengmap.FMLineType.FMARROW,
    //设置线动画,false为动画
    noAnimate: false
};
map.drawLineMark(line, lineStyle);
```

### 获取路径描述信息

根据设置的起、终点和起、终点楼层进行路径分析，分析成功后，返回路径经过的坐标点集。同时可根据结果集获取路径描述等信息。

```javascript
//路径分析：传入起点和终点坐标和楼层ID进行楼层分析。
if (naviAnalyser.analyzeNavi(naviCoords[0].groupID, naviCoords[0], naviCoords[1].groupID, naviCoords[1],fengmap.FMNaviModule.MODULE_SHORTEST) == fengmap.FMRouteCalcuResult.ROUTE_SUCCESS) {
    var results = naviAnalyser.getNaviResults(); //得到路径分析后的结果集
    if (results.length == 0)
        return;

    var des = naviAnalyser.getRouteDescriptions(results);
    console.log(des);
}
```

### 定位导航

Fengmap JavaScript SDK 结合定位技术，可实现定位导航的功能。下面将就结合模拟定位点进行路径分析并模拟导航的功能以及真实导航展开说明。即导航类FMNavigation的使用说明。

### 模拟导航

初始化导航对象，设置起始模拟点，在地图渲染后即loadComplete回调后，初始化路径分析对象。示例代码如下：

```javascript
// 地图加载完执行画导航路径
var navi = new fengmap.FMNavigation({
    map: map,
    locationMarkerUrl: 'image/pointer.png', //导航中用到的定位标注图标
    locationMarkerSize: 24,  //设置Marker尺寸
    tiltAngle: 80,   //导航跟随倾斜角度
    scale: 282,  //模拟导航开始时地图的显示比例尺, 默认值为282,表示1:282的地图比例尺。对应比例尺级别21
    followPosition:true,    //模拟导航时是否地图跟随,默认true
    followAngle:true,       //模拟导航时是否改变地图角度，默认false
    lineMarkerHeight: 1,   //导航线与楼层之间的高度偏移设置。默认是1
    // 设置导航线的样式
    lineStyle: {
        lineType: fengmap.FMLineType.FMARROW,   // 导航线样式
        lineWidth: 10, // 设置线的宽度
        godColor: '#FF0000',   //设置线的颜色
        godEdgeColor: '#4a82d2',   //设置边线的颜色
    }
});
```

绘制导航线，模拟起始点，使用导航类绘制导航线。

```javascript
//起点终点坐标
var coord=[
    {x: 12961647.576796599, y: 4861814.63807118, groupID: 1},  //起点
    {x: 12961699.79823795, y: 4861826.46384646, groupID: 6}     //终点
];
//添加起点
navi.setStartPoint({
    x: coord[0].x,
    y: coord[0].y,
    groupID: coord[0].groupID,
    url: 'image/start.png',
    size: 64
});

//添加终点
navi.setEndPoint({
    x: coord[1].x,
    y: coord[1].y,
    groupID: coord[1].groupID,
    url: 'image/end.png',
    size: 64
});

// 画出导航线
navi.drawNaviLine();
```

获取导航描述信息，完成路径分析后，可根据路径结果获取路径描述信息。参考代码如下：

```javascript
// 设置导航中实时回调事件
navi.on('walking', function(data) {
    console.log('导航中');
    //获取某一段路线描述
    console.log(navi.naviDescriptions(data.index));
});
```

添加导航事件，导航中监听事件有导航中walking事件、导航完成complete事件、导航中跨层crossGroup事件。绑定事件示例如下：

```javascript
// 设置导航中实时回调事件
navi.on('walking', function(data) {
    console.log('导航中');
});

//导航完成事件
navi.on('complete', function() {
    console.log('导航完成');
});

//路径跨楼层事件
navi.on('crossGroup', function(group) {
    console.log('楼层发生变化');
});
```

导航的开始、暂停、继续与结束，模拟导航有开始、暂停、继续的方法，示例如下：

```javascript
//开始导航
navi.simulate();
//暂停导航
navi.pause();
//继续导航
navi.resume();
//结束导航
navi.stop();
```

### 真实导航

在使用真实的定位系统时，如：WIFI定位，蓝牙定位等，就需要将定位系统所返回的定位坐标转化为fengmap地图坐标，这样就可以在fengmap地图中去根据真实的定位点去实时的改变地图中的Marker的位置。实现真实定位。示例如下：

```javascript
// 先创建FMNavigation对象
var navi = new fengmap.FMNavigation({map: map})
// 如：定位坐标返回的坐标点
var theCoord = { x: 12956609.56, y: 4852487.1, groupID: 1 };
// 调用locate方法，此方法会触发walking事件
// 此方法要按定位设置的频率来循环设置
navi.locate(theCoord);
// 监听navi对象的walking 事件
navi.on('walking', function(data) {
    // 在返回的data中包括以下数据
    /*
    {
        remain: 到终点的剩余距离,
        walk: 已经走过的距离,
        distance: 定位点的路线偏移距离,
        distanceToNext: 是下一个转角处的距离,
        angle: 当前路线与正北方向的角度,
        index: 当前路段的索引,
        point: 定位点在路径约束后的点坐标,
        groupID, 当前的楼层id,
        index: 当前路段的索引
    }
    */
});
```

## 特效添加
