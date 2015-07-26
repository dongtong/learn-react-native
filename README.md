## 使用React Native构建iOS应用

- 本地Mobile应用

使用标准的工具针对特定的移动平台，如iOS构建应用，大幅提升用户体验。类似于用swift构建iOS应用, java构建android应用。


- React

React是facebook针对开发Web页面中View的一个JavaScript库（注意不是框架，更不是MVC框架）。它的中心主要集中在视图(View),不涉及应用如何架构，如果想了解如何架构应用，可以了解一下facebook 的Flux和Relay框架。React通过观察虚拟DOM(Virtual DOM),来实现根据需要来更新真实DOM，而不需要整体渲染真实DOM,这样的效率会更高一些。虚拟DOM允许在服务端生成，然后发送最终的HTML到浏览器端渲染，真样会解决SPA(Single Page Application) SEO问题。一般服务端可以使用Node,Clojure或者其他可以在服务端运行JavaScript引擎的语言环境。React带有自有JSX模版，允许在JavaScript混入HTML,作为组件一部分。因为React由facebook开源，facebook本身有许多内部项目都在使用，所以不用担心项目的支持问题。

- React Native

React Native使开发人员可以用JavaScript和React基于本地平台构建世界级的应用。

Github项目地址是: https://github.com/facebook/react-native

使用React Native可以很容易地构建与原生iOS应用相同用户体验的应用(只是目前性能方面还有待提升)，即使没有太深的Web开发经验也可以实现。React Native在不久的将来也会支持Android平台。

UI是基于100%本地iOS控件(UIKit)不会有违和感以及性能问题(表示怀疑)! 

使用熟悉的语言和库(JavaScript, React),不需要UIKit经验即可开发。

使用Web熟悉的工作流可以让你在模拟器(simulator)中直接刷新即可看到改动效果(如Grunt, Gulp, Webpack...).

当然调试可以使用chrome开发者工具来调试React代码，或者使用chrome的React插件调试。

使用类似CSS style语法修改View的展示。React Native会将样式转化为本地控件样式。

使用FlexBox布局React Native应用。

- React Native如何工作?


	  JSX -> JavaScript -> JavaScriptCore -> Objective-C
	  
### 安装React Native

访问http://facebook.github.io/react-native/docs/getting-started.html

1. 安装Xcode, Homebrew(http://brew.sh), iojs(watchman npm), flow

   去apple官网下载xcode IDE, 访问homebrew官网安装。安装完成后，安装iojs, 这里使用nvm(https://github.com/creationix/nvm)安装node和iojs，这样可以使用nvm切换不同的环境。
   
   
     	curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.25.4/install.sh | bash   
     	nvm install iojs
     	
   也可以安装node
   
   		nvm install stable
   		
   切换iojs和node可以使用
   
   		nvm use iojs
   
   
2. 安装React Native

	因为react native建议使用iojs，所以这里使用iojs.
   
   		npm install -g react-native-cli

3. 生成React Native 项目

	通过cli命令生成项目
	
		sudo react-native init RecycleTrash
		
	如果出现一直停滞不前的话，查找日志
	
		find /Users/mac -name builderror.log
		
	可以打开类似这样的日志
	
		vim /Users/mac/xcode64/Xcode.app/Contents/Developer/usr/share/xcs/xcsd/node_modules/socket.io/node_modules/socket.io-client/node_modules/ws/builderror.log
		
	一般是因为node版本有问题，根据提示安装对应的node版本
	

4. 在iOS模拟器中启动应用

	安装成功后，根据控制台提示，打开xcode工程
	
		Open /Users/mac/React/workspace/react-native/RecyleTrash/RecyleTrash.xcodeproj
		
	点击Run
	
	![rn-1.png](pics/rn-1.png)
		
	如果需要修改内容，可以打开index.ios.js修改，然后command + r刷新模拟器即可看到修改后的内容。
	
	![rn-2.png](pics/rn-2.png)
	
5. 使用Chrome开发者工具调试

	运行项目，打开浏览器访问http://localhost:8081/debugger-ui,得到以下界面:
	
	![rn-3.png](pics/rn-3.png)
	
	command + d选择'Debug in Chrome'
	
	![rn-4.png](pics/rn-4.png)
	
	然后在source tab中debug
	
	![rn-5.png](pics/rn-5.png)
	
6. 运行Github上React Native项目的实例程序以及查看文档

   首先下载项目:
   
   		git clone git://github.com/facebook/react-native.git
   		cd react-native
   		cd Examples
   		subl .
   
   可以看到一些比较有意思的示例程序
   
   ![rn-6.png](pics/rn-6.png)
   
   查看文档可以访问 http://facebook.github.io/react-native/docs/getting-started.html
   		
   	