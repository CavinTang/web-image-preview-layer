# web-image-previe
&#8195;&#8195;&#8195;&#8195;主要是对[layer](http://www.layui.com/)的相册层进行了扩展,增加了一个工具条,主要还是参考了bugclose的图片预览。效果如下:<br>
![](https://github.com/CavinTang/web-image-preview-layer/raw/master/demo.png)

## 参数说明
名称 | 类型 | 说明
------|------|--------
photos|selector or json|可以是一个包含指定格式图片容器的选择器，也可以是一个包含图片的json对象，详细说明可以参考[layer photos](http://layer.layui.com/api.html#layer.photos)
tab|function|图片切换完成之后的回调函数，可选
needNavArrow|bool|是否显示图片上的切换箭头，可选，默认值：true
needToolbar|bool|是否显示操作工具条，可选，默认值：true

## 引用JS
1. 下载js
```bash
$ git clone https://github.com/CavinTang/web-image-preview-layer.git
$ cd web-image-preview-layer
```

2. 将layer目录拷贝到需要的项目目录下面
3. 添加JS引用
```html
<script src="layer/layer.js"></script>
<script src="layer/layer.yz.js"></script>
```

## 通过HTML加载
1. 先创建指定格式的HTML
```html
<div id="photosDemo" class="photos-demo">
    <!-- layer-src表示大图  layer-pid表示图片id  src表示缩略图-->

    <img layer-src="http://static.oschina.net/uploads/space/2014/0516/012728_nAh8_1168184.jpg" layer-pid=""
         src="http://static.oschina.net/uploads/space/2014/0516/012728_nAh8_1168184.jpg" alt="layer宣传图">
    <img layer-src="http://sentsin.qiniudn.com/sentsinmy5.jpg" layer-pid=""
         src="http://sentsin.qiniudn.com/sentsinmy5.jpg" alt="我入互联网这五年">
    <img layer-src="" layer-pid=""
         src="http://sentsin.qiniudn.com/sentsin_39101a660cf4671b7ec297a74cc652c74152104f.jpg" alt="微摄影">
    <img layer-src="http://sentsin.qiniudn.com/sentsinsan01.jpg" layer-pid=""
         src="http://sentsin.qiniudn.com/sentsinsan01.jpg" alt="三清山">
    <img layer-src="http://ww2.sinaimg.cn/mw1024/5db11ff4jw1ehcyirr6quj20q00ex42w.jpg" layer-pid=""
         src="http://ww2.sinaimg.cn/mw1024/5db11ff4jw1ehcyirr6quj20q00ex42w.jpg" alt="国足">
</div>
```

2. 初始化相册层
```javascript
new yzLayer().photos({
    photos: '#photosDemo',
    tab: function (pic, layero) {//optional, tab callback
        console.log('tab');
    }
});
```

## 通过JSON数据加载
```javascript
new yzLayer().photos({
    photos: {
        "title": "相册标题", //相册标题
        "id": 123, //相册id
        "start": 0, //初始显示的图片序号，默认0
        "data": [   //相册包含的图片，数组格式
            {
                "alt": "图片名1",
                "pid": '', //图片id
                "src": "http://static.oschina.net/uploads/space/2014/0516/012728_nAh8_1168184.jpg", //原图地址
                "thumb": "http://static.oschina.net/uploads/space/2014/0516/012728_nAh8_1168184.jpg" //缩略图地址
            },
            {
                "alt": "图片名2",
                "pid": '', //图片id
                "src": "http://sentsin.qiniudn.com/sentsinmy5.jpg", //原图地址
                "thumb": "http://sentsin.qiniudn.com/sentsinmy5.jpg" //缩略图地址
            }
        ]
    },
    tab: function (pic, layero) {//optional, tab callback
        console.log('tab');
    }
});
```

## 更多示例
- [layer photos](http://layer.layui.com/api.html#layer.photos)
- [layer](http://www.layui.com/)