# 长安大学校园导航小程序
(等我最近把数据库连上之后就开源）

# 一、**详细设计**

## 1.1系统开发环境及开发工具**

Win10 22H2 x64版本

微信开发者工具 Stable 1.06.2310080

## 1.2主页面功能设计**

### 1.2.1界面设计
![wps1](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/1d6fcfad-74ac-4483-a17b-81c7ebd84f63)


这个界面是一个手机截图，背景为校园景色，上方是长安大学的标志和文字，显示时间为20:25。界面的主体内容集中在屏幕中央，列出了几个核心功能板块。整体设计简洁明了，用户能够快速找到所需信息。

主界面包括“长大简介”和“逛逛长大”两个功能按钮。

### 1.2.2功能实现过程

（1）天气预报功能：

通过调用百度地图API（bmap-wx.min.js）获取实时天气信息。

在success回调函数中，提取返回的天气数据并在页面上显示，包括城市、PM2.5、日期、温度、天气描述和风力等信息。

天气信息显示在index.wxml文件中的名为weather的<view>中。

（2）用户信息获取：

小程序在页面加载时，判断用户是否已经授权获取其信息。

如果用户已经授权，将用户信息显示在页面上。

如果用户未授权，根据不同版本的兼容性进行处理，最终通过wx.getUserInfo获取用户信息。

（3）页面结构和样式：

index.wxml文件定义了小程序的页面结构，包括背景图、Logo、天气预报、长大简介和逛逛长大等模块。

样式方面，index.wxss文件中定义了各个模块的位置、大小和样式，包括首页背景图、Logo位置、天气预报样式以及长大简介和逛逛长大的位置等。

圆形按钮的样式通过_sxau_go和_sxau_intro类定义，包括大小、颜色、字体等。

（4）页面跳转：

使用navigator组件实现页面之间的跳转，其中长大简介和逛逛长大分别链接到sxauintro和sxauguide页面。

总体来说，这个小程序提供了获取天气信息、展示学校介绍和导览功能。实现过程涉及调用百度地图API、处理用户授权、定义页面结构和样式以及实现页面跳转等方面的开发。

## **1.3“长大简介”功能设计**

### 1.3.1界面设计
![wps4](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/483546d4-7dc6-4a04-a437-7d5637ec6083)
![wps3](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/82e02f91-dae1-453b-9ef8-c0476301cee5)
![wps2](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/598d7cf0-76e6-482c-b2c1-d3596710ae9b)


### 1.3.2功能实现过程

（1）视频展示功能：

在页面中使用<video>标签展示长安大学的相关视频。

视频通过src属性指定了视频的链接。

设置了视频的控制按钮（controls）和自动播放（autoplay）等属性。

（2）地图导航功能：

使用navigator组件创建了一个可点击的地图导航按钮，点击后跳转到sxauguide页面。

通过_sxauintro_go类定义了按钮的样式，包括大小、颜色、字体等。

（3）文字介绍功能：

页面中使用了<text>、<div>等标签展示了长安大学的详细介绍，包括校名、英文名、学校的历史、学科设置、师资队伍、科研成果、国际合作等内容。

通过在<text>、<div>等标签中设置不同的样式，如字体大小、颜色、行距等，美化了文字的呈现效果。

（4）样式设置：

在sxauintro.wxss文件中定义了视频区、地图导航按钮、文字介绍等部分的样式。

通过设置各个元素的大小、边距、字体样式等，使页面呈现出整体美观的效果。

总体来说，该页面通过视频、地图导航按钮和文字介绍等形式，生动地展示了长安大学的校园风貌、学科实力和国际化办学特色。实现过程涉及了小程序中视频展示、页面跳转、样式设置等方面的开发。

## **1.4“逛逛长大”功能设计**

### 1.4.1界面设计
![wps5](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/7ebe466e-523a-4cc9-a052-655d132f243c)
![wps6](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/ee8da6bf-ccde-4cfd-bdc3-0a91d97649ea)
![wps7](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/2e32f5e9-a66f-40f4-ba2f-8a472e6b7aea)
![wps8](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/7ffec2b8-16bc-4336-8eb7-685b2624f38f)

![wps11](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/0eea592d-24c6-471d-80d4-9633be9d9c4d)
![wps10](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/5ddffbda-07a3-4f68-bbb9-c5cd8a46e558)
![wps9](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/7b9e0de3-f3d5-419c-9bd9-4707709d42d9)

### 1.4.2功能实现过程

功能介绍：

（1）地图导航功能： 代码中应该包含了实现地图导航的功能，用户可以使用该小程序在长安大学校园中进行导航。

（2）位置定位： 可能有代码用于获取用户当前位置，以便在地图上正确显示用户所在位置。

（3）路径规划： 可能包含路径规划算法，帮助用户找到从一个地点到另一个地点的最优路径。

 

实现过程：

地图数据： 实现地图导航首先需要地图数据，这可能包括长安大学校园的地图信息，建筑物位置，道路网络等。

用户位置获取： 代码可能包括获取用户设备的位置信息，比如 GPS 数据。

地图显示： 应该有代码用于在用户界面上显示地图，并标注用户当前位置。

交互逻辑： 用户可能可以输入目的地或者点击地图上的某个位置，代码需要处理这些输入，触发路径规划和导航功能。

路径规划算法： 如果包含路径规划功能，可能使用了一些算法，比如 Dijkstra 算法或 A* 算法来找到最短路径。

导航指引： 可能有代码生成导航指引，告诉用户何时转弯，前进多远等信息。

# 二、**使用说明**

首先打开小程序，进入即主页面：
![wps12](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/57832256-6f57-4c25-8083-6bb5d0aa6dec)



点击右上角![wps13](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/5aa5b724-9fa8-48ba-be6e-f7697ea7e7ad)即可关闭程序。


点击“长大简介”按钮![wps14](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/54833ee2-c2b7-4f12-9f8c-c5cde48f4f44)，即可跳转进入长大简介界面。
![wps15](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/df9e770d-155c-4779-a1ae-3ed31faeba01)

如图所示，可观看长大介绍视频，也可观看文字介绍。

用户可通过手指滑动屏幕，来调整文字内容，如图：
![wps16](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/8214cbf0-2930-4425-bd50-d182fd5d1dc6)

点击“逛逛长大”，或“地图导航”可跳转至导航界面，如：
![wps18](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/bf27bd1d-d9fb-4b4a-a0af-a128ecc47c39)
![wps17](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/91e70bba-2878-45fa-9c98-04fe8e8c64a8)
![wps19](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/ad34de85-6c51-4f3a-88ea-043c832b7664)


界面上方条状滑动条可以选择地点类别，
![wps20](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/5107d30b-3a39-45b8-84be-f6bd74760590)

中间为腾讯地图，用户可放大缩小，
![wps21](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/810f584d-bfd3-4537-9599-21d95e73aeb9)

下方为手绘长安大学渭水校区平面图。
![wps22](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/941ee8c6-e713-405b-aae2-8bdf2a4d2a39)

点击条状栏，选定地点，如校门，
![wps23](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/44c2744b-94bd-4627-a824-3208e53624ed)
![wps24](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/e3fafced-61a8-4ec8-91ec-3ba3a380ff9f)

校门位置显示至地图中，下方有校门的具体名称，用户可选择前往。点击![wps25](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/f7dbab0b-aa0a-4737-9143-890d9bcc8588)按钮，调用腾讯地图api。跳转至腾讯地图界面，

![wps26](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/cad0d78a-1ec2-483a-9d2e-60353186decb)

其他地点与此类似，在此不做介绍。


点击![wps27](https://github.com/yanyanlai/CHD-Navigation-Mini-Program/assets/110188868/40ba75e9-a0de-45b9-a3aa-8e05c49a438d)，返回前一界面。
