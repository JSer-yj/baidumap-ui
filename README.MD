> ui-map.js源码大部分转载至[https://github.com/anypossiblew/ui-map-baidu]   
> 在原ui-map.js的基础上，根据项目需要，新增了toolbar控制，来更好的选择需要展示的地图控件   
> 去掉了uiMapInfoWindow directive，通过自定义来展示信息窗口
## 使用示例
> 安装：   
bower install baidumap-ui --save


> html页面：
```html
<div ui-map-async-load>
  <div id="map_canvas"
    ui-map="serveMap"
    ui-event="{'map-click': 'addMarker($event, $params)', 'map-zoomend': 'setZoomMessage(serveMap.getZoom())' }"
    ui-options="mapOptions"
    class="bdmap-size" ></div>
</div>
```

> angular component：
```javascript
$scope.mapOptions = {
  ngCenter: {         //中心坐标
    lng: 116.404,
    lat: 39.915
  },
  toolbar:{
    mapTypes:[],      //地图类型
    scale:true,       //比例尺
    navigation:true,  //缩放平移
    cityList: true    //省市列表
  },
  ngZoom: 12,         //缩放比例
  overview: true,     //缩略地图
};
```

> angular module注入ui.map依赖：
```javascript
angular.module('myAppModule', ['ui.map']);
```

> module config中加入加载地图链接所需要的参数：
```javascript
myAppModule.config(['uiMapLoadParamsProvider', function (uiMapLoadParamsProvider) {
    uiMapLoadParamsProvider.setParams({
        v: '2.0', // 版本号
        ak:'xxxx' // 密钥
    });
}]);
```
