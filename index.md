# 小程序实战 - 美团点评核心功能实现(布局)

## 介绍
本教程是对大家学习完小程序基础 API 之后，提供的小程序综合实战教程，该教程分为 布局 + 功能，添加两部分，布局部分主要涉及主要内容如下：

1. 小程序的基本配置
2. 利用 rpx 等相对单位适配不同机型
3. 小程序中的模板使用
4. 视图中的图标处理及注意事项
5. 无限列表使用时的注意事项
6. css3 相关方法在小程序中的使用


## 前置知识点说明

- 浮动、定位等布局基础知识点
- 熟悉小程序基本开发配置
- 熟悉小程序基本组件使用
- css3 弹性盒模型
- css3 怪异盒模型
- css3 圆角、阴影、线性渐变
- css3 @font-face 自定义字体
- 移动端相对单位适配使用

## 学前测试题

1. 在使用 `<scroll-view srcoll-y></scroll-view>` 这个组件时，必须要设置的样式是？

	A：width
	B：height
	C: overflow-x:hidden;
	D：overflow-y:hidden;

	正确答案: B	

2. 在使用`<text></text>`组件时，下拉哪些样式单独添加是无效的(多选)?

	A: width
	B: height
	C: background
	D: color

	正确答案: A,B

3. 添加了下列那条样式之后，给子元素添加 `margin:auto` 可以有垂直居中的效果?

	A: 无须添加任何样式
	B: 添加任何样式都实现不了该需求
	C: diaplay: table-cell
	D: display: flex

	正确答案: D

4. 根据下列说明，计算当前 .box 的内容宽度

	当前屏幕宽度: 375px
	
	.box {
		box-sizing: border-box;
		width: 200rpx;
		padding: 10rpx;
		border: 1px solid #000;
	}

	A: 100px  B: 198px  C: 88px D: 98px

5. 在小程序中跳转页面应该使用？

	A：`<a href="/page/index"></a>`

	B: `<navigator href='/page/index'>北京</navigator>` 	 

	C: `<navigator url='/page/index'>北京</navigator>` 

	D: `<link to="/page/index"></link>`

6. 在小程序中，设置链接按下时的样式设置应该是在什么里设置?

	A: `.navigator-hover{}`

	B: `navigator:hover{}`

	C: `.a-hover{}`

	D: `a:hover{}`

7. 下列结构中，.wrap 最终的高度是多少

	wxml:
	`	
		<view class='wrap'>
			<view class='row'>
				<view class='ceil1'></view>
				<view class='ceil2'></view>
			</view>		
		</view>	
	`	
	wxss:
	`
		.wrap {
			width: 500rpx;
		}		
		.row {
			padding: 20rpx 0;
		}
		.ceil1 {
			float: left;
			width: 100rpx;
			height: 100rpx;
		}
		.ceil2 {
			float: left;
			width: 200rpx;
			height: 200rpx;
		}
	`

	A: 200rpx B: 100rpx C: 40rpx  D: 0

	正确答案: C

8. 在对照下列结构，可以找到最后一个`<text></text>`写法正确的选择器是(多选)?
	
	`	
		<view class='wrap'>
			<text>1</text>
			<view>2</view>
			<text>3</text>
			<text>4</text>
			<view>5</view>
			<text>6</text>
		</view>	
	`		

	A: .wrap text:nth-child(6){}
	B: .wrap text:nth-of-type(6){}
	C: .wrap text:last-child{}
	D: .wrap text:last-of-type{}

	正确答案: A,C,D

9. 下列结构中，.view和.view2 直接的距离最后是多少

	wxml:
	`	
		<view class='wrap'>
			<view class='view'></view>
			<view class='view2'></view>
		</view>	
	`	
	wxss:
	`
		.view {
			width: 100rpx;
			height: 100rpx;
			margin: 50rpx;
		}
		.view2 {
			width: 100rpx;
			height: 100rpx;
			margin: 60rpx;
		}		
		
	`

	A: 110rpx B: 60rpx C: 50rpx D: 0

	正确答案: B

10. 下列结构中，.view、.view2、.view3 层叠显示顺序是?

	wxml:
	`	
		<view class='wrap'>
			<view class='view'>
				<view class="view3"></view>
			</view>
			<view class='view2'></view>
		</view>	
	`	

	wxss:
	`	
		.wrap {
			position: relative;
		}
		.view {
			position: relative;
			z-index: 1;
		}
		.view2 {
			position: absolute;
			z-index: 2;
		}
		.view3 {
			position: absolute;
			z-index: 3;
		}		

	`

	A: .view在最下层，.view3 在最上层
	B: .view在最下层，.view2 在最上层
	C: .view2在最下层，.view3 在最上层
	D: .view3在最下层，.view 在最上层

	正确答案: B


## 课程大纲

- 小程序基本配置

	- 项目视图介绍
	- 小程序注册流程
	- 小程序引入本地图片的注意事项

- 首页导航布局	

	- 利用弹性盒模型 (flex) 进行自适应等分间距布局

- 商铺列表结构
	
	- `<scroll-view></scroll-view>` 小程序上滑加载更多的列表的结构实现
	- 小程序中，公共样式表引入方式 `@import`

- 商铺列表样式
	
	- 小程序引入本地背景图处理 - dataURL
	- 评分布局实现
	- 小程序模板 <template></template> 使用

- 商铺分类

	- 阿里字体图标选择 
	- 小程序引入本地字体资源
	- fontIcon 字体图标使用

- 商铺分类筛选菜单及排序菜单

- 商品详情

- 用户中心及登录备用页面
	- 获取用户信息的相关准备

- 城市索引列表布局
	
	- 垂直居中屏幕的索引导航制作


