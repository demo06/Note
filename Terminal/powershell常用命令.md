# Windows PowerShell 常用命令

1、hostname：电脑在网络中的名称。
2、 pwd：打印工作目录。即输出目前的文件夹地址。
3、cd：更改路径。cd x（进入下一级目录x）；cdx/y/z（进入下几级目录z）；cd\（当前目录的根目录）；cd ..（返回上一级目录）；cd../../..（返回上几级目录，cd后一定要有空格）。
4、dir：列出路径下的内容。   Linux是ls
5、mkdir：创建路径。即创建新文件夹。mkdir -px/y/z（创建往下的多级目录）。
6、New-Item：创建空文件。格式：New-Itemx.txt -type file。
7、rmdir：删除路径。
8、rm：删除文件。
9、pushd：推送路径。即保存当前路径并转到一个新路径下。
10、popd：弹出路径。返回到之前pushd保存的路径。
11、cp：复制文件或路径。cp x.txt some/（复制文件x到some文件夹）；cp -recurse somenewplace（复制some文件夹，生成新文件夹newplace）。
12、mv：移动文件及路径。即重命名。
13、more：逐页显示整个文件。
14、type：打印输出整个文件。
15、exit：退出shell。
【下列代码日后研究】
16、 robocopy：更可靠的复制命令。
17、dir-r：寻找文件。
18、select-string：在文件中查找内容。
19、help：阅读手册。
20、helpctr：寻找恰当的手册页面。
21、echo：打印一些参数。
22、set：导出/设定一个新的环境变量。
23、runas：成为超级用户或root，危险命令！
24、attrib：修改文件的属性。
25、icacls： 显示或修改自由访问控制列表（Dacl）上指定的文件，并制定目录中的文件应用于存储的Dacl。
26、 forfiles：在一大堆文件上面运行一条命令。