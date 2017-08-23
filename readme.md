## 移动端相关概念

#### 1、移动端简介

#### 2、移动端测试环境

  1. pc端chrom模拟环境测试
  2. 真机测试（手机与电脑里文件关联方法）

#### 3、像素概念

  1. 设备独立像素
  2. 设备像素
  3. 像素比
  4. 普通屏与高清屏的概念
  5. 普通屏与高清屏在移动端的区别

#### 4、viewport

viewport的各个参数的概念以及设置方式
#### 5、像素比

像素比与设计图的关系
 
## 移动端适配方案
1、百分比适配
2、viewport适配（两种适配方案）
3、rem适配（两种适配方案）
4、弹性布局适配
5、移动端布局中的注意问题
1、body的overflow问题
2、固定定位问题
6、移动端样式重置

淘宝的viewport设置
window.devicePixelRatio 屏幕像素比
```
(function() {
  var scale = 1 / window.devicePixelRatio;
  var meta = document.createElement('meta');
  meta.name = 'viewport'
  meta.content = 'initial-scale=' + scale + ',minimun-scale=' + scale + ',maximum-scale=' + scale;
  document.head.appendChild(meta)
})()
```
rem适配
```
(function() {
  var html = document.documentElement;
  var width = html.getBoundingClientRect().width;
  html.style.fontSize = width / 16 + "px"
    // iphone5下 1rem = 20px 
})()
```
样式重置
```
body {
  font-family: Helvetica;
  margin: 0;
}

body * {
  -webkit-text-size-adjust: 100%;
  -webkit-user-select: none;
}

a,
button,
input {
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0)
}

button,
input {
  -webkit-appearance: none;
  border-radius: 0;
}

a {
  text-decoration: none;
}

input {
  outline: none;
  vertical-align: middle;
}
```
