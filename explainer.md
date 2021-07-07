# MiniApp UI Componets Explainer 
## Authors
Zitao Wang (Huawei)
## 1. Introduction

### What is this?
MiniApps are made of high-level building blocks called UI Components, which allow developers to quickly construct the UI for a MiniApp.
### Why should we care?
For MiniApp, there are some pre-standard implementations and wildly used. But these implementations may follow different vendor-specific development guidelines for developing MiniApp UI components. And some of them are defining their own markup languages (WXML, SWAN, AXML), specific event handling, data-binding and rending methods. For example:

- Wechat WXML:
```html
  <!--wxml-->
  <view wx:if="{{view == 'WEBVIEW'}}"> WEBVIEW </view>
  <view wx:elif="{{view == 'APP'}}"> APP </view>
  <view wx:else="{{view == 'MINA'}}"> MINA </view>
```
- Baidu SWAN:
```html
<!-- template-demo.swan-->
<template name="tag-card">
    <view>
        <text>标签: {{tag}}</text>
        <text>昵称: {{nickname}}</text>
    </view>
</template>

<template name="person-card">
    <view>
        <text>位置: {{pos}}</text>
        <text>姓名: {{name}}</text>
    </view>
</template>

<template name="team-card">
    <view s-for="item, index in teams">
        <text>球队: {{index}} - {{item}}</text>
    </view>
</template>

<template name="age-card">
    <view>
        <text>年龄: {{age}}</text>
    </view>
</template>
```
- Alipay AXML:
```.html
<!-- pages/index/index.axml -->
<view a:for="{{items}}"> {{item}} </view>
<view a:if="{{view == 'WEBVIEW'}}"> WEBVIEW </view>
<view a:elif="{{view == 'APP'}}"> APP </view>
<view a:else> alipay </view>
<view onTap="add"> {{count}} </view>
```
It may lead to repeated learning and repeated development by developers. Therefore, we propose to define a standard set of UI common components for MiniApp. That allows codes to easily migrate to different platforms, reduce repetitive development, and provide the same user experience.
