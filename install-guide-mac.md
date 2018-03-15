# NativeScript-Vue Mac OS安装篇


## 环境需求
<!-- TOC -->

- [NativeScript-Vue Mac OS安装篇](#nativescript-vue-mac-os安装篇)
    - [环境需求](#环境需求)
        - [Brew](#brew)
        - [Node.js](#nodejs)
        - [NativeScript CLI](#nativescript-cli)
        - [Xcode](#xcode)
        - [Android SDK](#android-sdk)
        - [android模拟器](#android模拟器)
        - [快速开始](#快速开始)

<!-- /TOC -->


### Brew
> macOS 缺失的软件包管理器，用于快速安装软件包
```bash
   $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Node.js
>  Node.js 是一个基于 Chrome V8 引擎的 JavaScript 运行环境, 推荐LTS版本 8.x
```bash
  $ brew install node@8
```

### NativeScript CLI
> NativeScript Node 客户端
```bash
 $ sudo  npm install -g nativescript
```

### Xcode
1. 下载安装XCode，前往[苹果开发者中心](https://developer.apple.com/download/)下载
2. 安装xcodeproj
```bash
    $ sudo gem install xcodeproj
``` 
3. 安装CocoaPods
```bash
    $ sudo gem install cocoapods
``` 

### Android SDK
1. [JDK 8+](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
2. android-sdk
```bash 
    $ brew cask install android-sdk
```
3. 环境变量
* 在`~/.bash_profile`添加
```bash 
    export JAVA_HOME=$(/usr/libexec/java_home)
    export ANDROID_HOME=/usr/local/share/android-sdk
    export JAVA_OPTS='-XX:+IgnoreUnrecognizedVMOptions --add-modules java.se.ee'
```
4. 安装Android SDK Platform 25 和 Build-Tools 25.0.2 +
```bash 
   $  $ANDROID_HOME/tools/bin/sdkmanager "tools" "platform-tools" "platforms;android-25" "build-tools;25.0.2" "extras;android;m2repository" "extras;google;m2repository"
```
    ps: 这一步会卡很久，因为在下载


### android模拟器

推荐 [genymotion](https://dl.genymotion.com/releases/genymotion-2.12.0/genymotion-2.12.0.dmg
)，看个人喜好




### 快速开始
> 装完换环境以后，新建个测试项目试试咯

* 用vue-cli快速新建项目，project-name指的`项目名称`
```bash
   sudo npm install -g @vue/cli @vue/cli-init
   vue init nativescript-vue/vue-cli-template <project-name>
   cd <project-name>
   npm install
```

* 运行App
```bash 
 $ npm run watch: <platform>
```
这里的platform可选`ios`和 `android`
