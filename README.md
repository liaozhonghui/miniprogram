# 云开发 quickstart

这是云开发的快速启动指引，其中演示了如何上手使用云开发的三大基础能力：

- 数据库：一个既可在小程序前端操作，也能在云函数中读写的 JSON 文档型数据库
- 文件存储：在小程序前端直接上传/下载云端文件，在云开发控制台可视化管理
- 云函数：在云端运行的代码，微信私有协议天然鉴权，开发者只需编写业务逻辑代码

## 参考文档

- [云开发文档](https://developers.weixin.qq.com/miniprogram/dev/wxcloud/basis/getting-started.html)

## iconfont 自定义图标方案：5 种解决方案

```xml
<icon type="success" size="100rpx" style="background: grep"></icon>
```

单位： rpx, px 单位,

1. 图片
2. sprite 图片
3. css 绘制方式
4. 使用矢量字体 font-family 样式 iconfont.cn->svg
5. svg 矢量文件 sketch/在线 ps 文件 -> imageTobase64
   svg-> base64 的图片源而生成文件(www.sojson.com/image2base64.html)

### 真机的 icon 不正常显示？

兼容性引起的，`ttf` 和 `woff` 格式的字体， 换成 svg 的数据嵌入

### 资源怎么下载? weui 组件库

[weui 的设计元素](https://developers.weixin.qq.com/miniprogram/design/#设计)
[源码](https://git.weixin.qq.com/rxyk/weapp-practice/repository/archive.zip?ref=2.1-icon-514)

#### 问题：iconfont.cn 用自定义的方式在小程序中使用?

## Progress 进度条：如果实现一个环形进度条

```xml
<progress
    show-info
    bindtap="onTapProgressBar"
    stoke-width="2"
    percent="{{percentValue}}"
    active-mode="forwards"
    active
    bindactiveend="onProgressActiveEnd"
></progess>
```

颜色规范: https://developers.weixin.qq.com/miniprogram/design/#字体

问题 1：如何实现一个下载文件并显示动态进度条的值？（每次用 setData 进行更新）
问题 2：progress 已经产生的进度条如何设置圆角?
(直接修改源码样式)WeappCode/package.nw/js/vendor/wx-components.css

```css
.wx-progress-inner-bar {
  width: 0;
  height: 100%;
}
.wx-progress-inner-bar {
  border-radius: 5px;
}
```

问题 3：已经加载完成的 process,怎么点击按钮再重新加载呢？（直接调用 2 此 setData）

```js
<view class="canvasBox>
</view>

```
