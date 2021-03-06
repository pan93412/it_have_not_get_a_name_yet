# 软件包和软件包管理器


## 软件包管理器是个啥？

软件包是对于一种软件所进行打包的方式。一般来说一个软件包包含这些内容呐~

* 软件的源代码或可执行文件.

* 一些供其它应用 ( 例如软件包管理器 ) 解析的元数据. (例如软件的名称,描述,版本,等等......)

* 一组用来执行安装前后事务的脚本.

而软件包管理器,当然就是来安装/卸载/更新软件包的一组应用程序咯~

软件包管理器是在电脑中自动安装、配制、卸载和升级软件包的工具组合，
在各种系统软件和应用软件的安装管理中均有广泛应用。

一般来说,一个软件包管理器有这样的功能:

* 从软件仓库中查询软件包的信息,并在需要时下载.

* 同时处理软件包需要的其它软件 ( 常常称作"依赖" )

* 验证下载的文件的完整性 ( 例如通过散列值或是数字签名 )

* 通过归档工具解开软件包,然后把文件安放到正确的位置上.

* 其它方便用户的功能 ( 例如软件包组,自动检查更新等等 )

## 为啥需要个软件包管理器?

首先大家先来回忆一下在 Windows 里是如何装软件的呗~

* 打开搜索引擎搜索一下

* 找到个没被墙的下载网站.....

* 从网页上数十个硕大而带有欺骗性的广告的缝隙中找到真正的下载链接.

* 然后下载......

* 下完以后运行,挑掉一堆勾😂😂,一路下一步直到完成 \_(:з」∠)\_

是不是很痛苦? 不过通过软件包管理器,汝就可以把安装软件的过程简化到 "安装某个软件" 就可以啦~

而且大多数软件包管理器都是从特定的软件仓库下载软件包,一般不用担心会夹带私货等问题 o(\*￣3￣)o

## 大家经常说的软件源,镜像源是啥?

软件包管理器会自动上网去下载软件,但他可不是四处瞎找,而是去固定的地方找。

这个固定的地方有个名字,叫做软件源。那里专门提供各种打包好的软件以及相关的信息介绍,供软件包管理器们下载。

这样的软件源有很多,遍布世界各地,软件包管理器应该去哪个呢?其实他自己也不知道,

他需要一个列表,一个软件源列表。软件包管理器工作的时候,就会去一个软件源列表记录的地方去下载软件。

有的人可能离的挺近,去默认的源就很方便,有的人去默认的源可能就很费劲,没准得绕过半个地
球才行。默认的源不够快,自然就需要找个快一点的源来代替。

然后世界各地的 GNU/Linux 用户们就会去建设不同的镜像源来方便本地的 GNU/Linux 用户呐~ ( 例如有爱的崔土豪 :fref:`cuihao` ~)


典型的软件包管理器的工作方式 \_(:з」∠)\_
-------------------------------------------

咱来举个安装软件包的栗子~

    用户 : 我想安装foo
    
    软件包管理器 : 先让咱在软件仓库里找一下 (\´・ω・\`)
    
    如果找不到的话,软件包管理器就会告诉用户 "咱找不到汝说的 foo 软件包呐~"
    
    如果找的到的话:
        
        "咱在软件仓库里找到 foo 了呐~,不过 foo 说要带上它的助手 baz 才会来嘛~
        
        ( 就是说要安装 foo 需要同时安装它的依赖项 baz )
        
        如果用户同意了的话,软件包管理器就会去软件仓库把 foo 和 baz 带回来 
        ( 也就是下载这两个软件包 )
        
        接着软件包管理器会检查下载来的软件包是否和数据库中的描述 (散列值 ) 一致,
        如果相同的话就会开始安装啦~
        
    在安装结束后,软件包管理器一般都会把具体过程写到自己的日记 (日志) 里方便以后使用呗~
    
当然啦,不同的软件包管理器有不同的表现呐~
