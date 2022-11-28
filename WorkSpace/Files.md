# 文件

SmartNoteBook为用户提供文件的上传与管理功能，上传完成后可同步至notebook模型文件目录，在代码块中通过路径进行访问。

SmartNoteBook的文件存储机制：分为两级

* 通过Workspace文件管理上传后，会将文件传输到MinIO分布式存储的公共区域

![](/assets/file.png)

* 通过NoteBook的数据资源同步，可以根据需要将MinIO公共区域的资源文件同步至Node节点使用

![](/assets/tbwj.png)

# 新建目录

在`WorkSpace文件`标签页，点击右上角`新建文件夹`，即可新建目录。

![](/assets/folder.png)

# 上传文件

在`WorkSpace文件`标签页，点击右上角`上传文件`，弹出选择文件窗口。


![](/assets/upfile.png)然后选择要上传的文件（单个文件大小不超过10M\)![](/assets/upfiles.png)

# 下载文件

在`WorkSpace文件`标签页，找到需要下载的文件，单击`操作`列的`...`，然后点击`下载`即可。

![](/assets/dw.png)

# 删除文件（夹）

在`WorkSpace文件`标签页，找到需要删除的文件（夹），单击`操作`列的`...`，然后点击`删除`即可。

![](/assets/del.png)







