> **小程序：**一种不需要下载安装皆是用的应用，实现【触手可及】的梦想，用户扫一扫或搜索即可打开的应用，体现用户【用完即走】的理念，用户不用担心是否安装太多应用的问题，应用将无处不在，担忧无需安装卸载。

**无需安装下载？**
其实只是限制了开发者上传安装包在1M以内，以目前网速，1M很快就下载完成，用户体会不到下载安装的过程。

native app、web app、hybrid app
-----------------------------

 - **native app**: 原生
 语言：Object C（IOS）
      Java(Android)
 页面：存放与本地
 优点：调用操作系统底层接口，性能好，可直接请求CPU资源
 弊端：实现一个应用程序，需要写两套语言；更新时要重新下载安装；
 
 - **web app**： web
  语言：html、js
  受限制于Ulwebview
  页面放于服务器,通过浏览器访问应用程序
  弊端：性能没有原生好，无法调用底层接口
  
 - **hybrid app** :混合
 语言：Object C(IOS) + html (视图层面用html写的)，容器、调用底层接口用IOS或Android语言写的
 优点：可调用底层接口，可以将web嵌入在里面，更新视图只更新html即可，不用更新整个应用；
 弊端：需要写两套；

**单页面应用**
目前web app一般写单页面应用，将所有资源全部加载出来，切换时通过路由，不用重新下载，web app因性能原因，做不了游戏。

**适合微信小程序的应用**
 1. 简单的，用完即走的应用
 2. 低频的应用
 3. 性能要求不高的应用

下载微信开发者工具
---------
参考[微信WEB开发者工具下载](https://jingyan.baidu.com/album/77b8dc7f9d341f6174eab6ee.html?picindex=1)

```
<!--index.wxml-->
<!-- view相当于html里的div，text相当于span，用text标签长按文字可复制，微信封装好的-->
<view class="container" hover-class='hover'>
  <view class="userinfo">
    <button wx:if="{{!hasUserInfo && canIUse}}" open-type="getUserInfo" bindgetuserinfo="getUserInfo"> 获取头像昵称 </button>
    <block wx:else>
      <image bindtap="bindViewTap" class="userinfo-avatar" src="{{userInfo.avatarUrl}}" mode="cover"></image>
      <text class="userinfo-nickname">{{userInfo.nickName}}</text>
    </block>
  </view>
  <view class="usermotto">
    <text class="user-motto">{{motto}}</text>
  </view>
</view>

```
