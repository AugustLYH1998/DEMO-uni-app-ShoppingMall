# uni-app小程序品优购商城项目
uni-app小程序品优购商城项目

初始化项目 
```js
npm install
```

开发工具 HBuilderX
scss/sass 编译

uni-app 结构分析
```js
┌─components        uni-app组件目录
│ └─comp-a.vue      可复用的a组件
├─pages             业务页面文件存放的目录
│ ├─index
│ │ └─index.vue     index页面
│ └─list
│ └─list.vue        list页面
├─static            存放应用引用静态资源（如图片、视频等）的目录，注意：静态资源只能存放于此
├─main.js           Vue初始化入口文件
├─App.vue           应用配置，用来配置小程序的全局样式、生命周期函数等
├─manifest.json     配置应用名称、appid、logo、版本等打包信息
└─pages.json        配置页面路径、页面窗口样式、tabBar、navigationBar 等页面类信息
```

由于平台的限制，小程序项目中不支持 axios，而且原生的 wx.request() API 功能较为简单，不支持拦截器等全局定制的功能。
因此，建议在 uni-app 项目中使用 @escook/request-miniprogram 第三方包发起网络数据请求。
请参考 @escook/request-miniprogram 的官方文档进行安装、配置、使用
官方文档：https://www.npmjs.com/package/@escook/request-miniprogram

```js
npm install @escook/request-miniprogram
```
## 首页

![image](https://user-images.githubusercontent.com/60884610/217739137-0878b93a-c52a-4f04-b3b9-d907760cf4b9.png)

![image](https://user-images.githubusercontent.com/60884610/217746169-db400d07-2903-479c-92ad-0247990a42ec.png)

业务逻辑
1. 使⽤tabbar 实现底部导航功能
2. 使⽤⾃定义组件的⽅式 实现 头部搜索框
3. 加载 轮播图 数据
4. 加载 导航 数据
5. 加载 楼层 数据


### 首页-商品列表
![image](https://user-images.githubusercontent.com/60884610/217739415-01f72d54-5f80-4dc1-aa9f-4d897b31cbde.png)

# 搜索
业务逻辑
1. 获取输⼊框的值进⾏搜索和渲染
2. 点击 取消 按钮时 清除输⼊状态，修改⻚⾯模样
3. 输⼊值改变时，为了提⾼性能，使⽤ 防抖 技术
4. 搜索历史的新增、清空


![image](https://user-images.githubusercontent.com/60884610/217756306-2280e758-39af-49e4-86a1-43d365431700.png)

![image](https://user-images.githubusercontent.com/60884610/217756317-0e19d3ee-f3c8-4dce-a610-5de5a5815817.png)




# 分类
业务逻辑
1. 加载分类⻚⾯数据
2. 点击左侧菜单，右侧数据动态渲染


![image](https://user-images.githubusercontent.com/60884610/217739257-53757bcc-2af8-4d51-90b4-94bf4aa77d4a.png)

![image](https://user-images.githubusercontent.com/60884610/217757321-55c1365d-c0ec-4f1c-b653-583fcb7ed2d7.png)


## 分类-商品列表

业务逻辑
1. 加载商品列表数据
2. 启⽤下拉⻚⾯功能
1. ⻚⾯的json⽂件中开启设置 enablePullDownRefresh:true
2. ⻚⾯的js中，绑定事件 onPullDownRefresh
3. 启⽤上拉⻚⾯功能 onReachBottom ⻚⾯触底事件
4. 加载下⼀⻚功能

![image](https://user-images.githubusercontent.com/60884610/217739767-1ea2d4d2-e9b6-437d-b272-d2c2dd1c8e8a.png)

![image](https://user-images.githubusercontent.com/60884610/217747816-5aef05fc-5b73-49b7-8fa2-f4ca080668e8.png)


## 商品-详情页
业务逻辑
1. 渲染商品详情数据
2. 点击图⽚，调出图⽚画廊，进⾏预览
3. 加⼊购物⻋

![image](https://user-images.githubusercontent.com/60884610/217748315-ab0bf82b-7578-49ea-a8ee-cf5c910d9788.png)

![image](https://user-images.githubusercontent.com/60884610/217748385-8b0ef6c7-a749-4780-95b8-2679f72a00db.png)


# 购物车页面
业务逻辑
1. 渲染购物⻋数据
2. 添加收货地址
3. 修改商品数量
4. 单选和全选功能

![image](https://user-images.githubusercontent.com/60884610/217752409-2603f6c4-6eb8-4ee8-b1e7-52bdc90b0ad2.png)

# 添加收货地址

![image](https://user-images.githubusercontent.com/60884610/217752481-f804204f-47eb-4021-bd52-07a4a462e5a0.png)


# 支付页面

1. 获取微信收货地址
2. 渲染购物⻋中要结算的商品
3. 实现⽀付
1. 获取微信的登录信息
2. 获取⾃⼰后台返回的⽀付相关参数
3. 调⽤微信接⼝实现 ⽀付
4. ⽀付成功创建订单
5. 跳转到订单⻚⾯


![image](https://user-images.githubusercontent.com/60884610/217752977-b9d1754e-5fb3-416c-85f4-e5e534650169.png)

![image](https://user-images.githubusercontent.com/60884610/217753956-735515ca-1b08-442a-b544-37e92ee0476a.png)



# 一键登录

![image](https://user-images.githubusercontent.com/60884610/217743879-4e49e5c5-b031-4412-b93b-0faad2c0ff45.png)

![image](https://user-images.githubusercontent.com/60884610/217754015-a3b2243b-67a7-409f-951e-9dc779165086.png)

