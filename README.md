一.ios 添加静态库的过程
1.1 创建一个工程路劲 可以直接使用git仓库文件名 
1.2 打开xcode 界面 点击“file ” 然后是“new ---> workspace” 
1.3 选择project ---> cocoa touch static libray 创建子模块到 1.1路径下
1.4打开1.2步骤中的xx.xcworkspace 工程 点击左侧 选择“add files to ...”
1.5选择需要添加的子工程的**.xcodeproj文件 ，确定
1.6依次操作
1.7建立一个窗口工程，file ---> new -->workspace--->single view app
1.8 到此工程就集合进了好几个子工程，可以正常运行了；

二 加入子工程到窗口工程
2.1窗口工程 link binary with libraries 添加子工程
2.2 build setting ---> header search paths  导入依赖的子工程库地址，（**.workspace这一段文件路径需要删除掉）
2.3 这样添加的子工程就可以跑起来了，也能引用了

三 子工程创建继承文件
3.1比如创建基于UIview的子文件，需要对外引用的话 
build phases ---> copy files  添加新创建的 .h文件
<!--点击build phases 上方的➕号，添加new headers phase-->
3.2创建分类，因为子工程的分类不会被预编译，所以添加的方法运行时会报错的
选择窗口工程 build setting -->other link .. -->other link flags :-ObjC

四 CoCoPods
4.1基于cocopod引用三分库
![avatar](/Users/hu/Desktop/80D139A25241140F4BEEFDE0F23AF216.jpg)






