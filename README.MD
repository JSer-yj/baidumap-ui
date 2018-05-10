## 使用示例

```html
<div ui-map-async-load>
  <div id="map_canvas"
    ui-map="serveMap"
    ui-event="{'map-click': 'addMarker($event, $params)', 'map-zoomend': 'setZoomMessage(serveMap.getZoom())' }"
    ui-options="mapOptions"
    class="bdmap-size" ></div>
</div>
```

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
