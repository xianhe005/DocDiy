# Android Studio2.3 源码提示修正

------


> * 简述：
修改Android Studio2.3的Docment提示方式，使之关联源码，防止无休止地Fetching Docment。


Android Studio2.3版本更新以后会自动根据用户设置的sdk路径，在配置文件jdktable.xml中为每个下载的api版本生成javadoc（文档）和javasource（源码）的配置，并且当用户没有下载到doc时，默认设为网址链接：http://developer.android.com/reference/"。配置文件形如：

    <javadocPath>
          <root type="composite">
            <root type="simple" url="http://developer.android.com/reference/" />
          </root>
        </javadocPath>
        <sourcePath>
          <root type="composite" url="file://D:/Android/android-sdk/sources/android-25"/>
        </sourcePath>

当使用用户Android Studio2.3写代码时，代码的文档提示会从此网址上查找，网络不好的情况下就会一直fetching Docment。这个问题的解决方法就是将javadoc的路径重定向为源码的路径，只是Android的API版本众多，配置有些麻烦。当然，嫌麻烦可以只配置下载的最后一个版本。

这亦是开发这个小工具的因缘。


[注] Android Studio和eclipse不同，没有像eclipse那样，既可以显示doc的提示，显示源代码的注释，Android Studio目前默认就只有Doc这种提示方式。

------

> * 预览：



打开工具：

![1](https://github.com/Mingyueyixi/DocDiy/blob/master/preview/0.jpg)

全部修改为网络Docment链接：

![2](https://github.com/Mingyueyixi/DocDiy/blob/master/preview/1.jpg)

全部修改为本地源码链接：

![3](https://github.com/Mingyueyixi/DocDiy/blob/master/preview/2.jpg)


