举例目录布局
-----------------------------------------------



    mirror/
        .res/                 <-- 只有镜子预览资源
        .gen/                 <-- 生成的镜像文件，不编辑
        debug/                <-- screen files for layouts in "src/debug/res"
            build_type.xml
        free/                 <-- screen files for layouts in "src/free/res"
            variant.xml
        freeDebug/
            variant.xml
        main/                 <-- screen files for layouts in "src/main/res"
            activity_main.xml
            image.png
            sample.xml
        paid/
            image.png
            sample.xml
            variant.xml
        paidDebug/
            flavor.xml
            image.png
        paidRelease/
            image.png
        release/
            build_type.xml
            sample.xml


例如，如果选定的变形是 paidRelease 那么 "paidRelease/image.png",
"release/build_type.xml", "release/sample.xml", "paid/variant.xml",
"main/activity_main.xml" 将推送到装置。

如果存在具有相同名称的文件在不同的目录中，镜像将发送最特定目录中的文件。 镜子假设的顺序相同Gradle/下载地址(按从最特定到最不特定的)： 
               variant > build type > flavor > main

我们使用一个简单的方式来合并镜子目录中的文件：只有将审议有关当前选定风味目录如果存在具有相同名称的文件路径或相对路径不同目录，只有将包括更具体的目录中的文件，其余的将被忽略。

下面是一个更广义的目录结构：

    mirror/
        .res/
        .gen/
        main/
屏幕具有示例数据的文件，
你把这里的文件或目录来帮助你构造你的样品数据，
风味特定的目录
生成类型特定的目录
变量的特定目录