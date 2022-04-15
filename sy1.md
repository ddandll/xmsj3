 # 实验一 课程所需软件安装
 
 
 ## 一. 安装Andriod Studio4.1以上版本
 
    1. 到官网下载安装包
    2. 一直下一步
    3. 完成安装
    4. 打开并尝试运行
    如下图成功：
   https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/andriod%20studio.png
   

## 二.  安装Jupyter Notebook（安装Anaconda）

    1. 前往官方下载页面下载。有两个版本可供选择：Python 3.6 和 Python 2.7，选择版之后根据自己操作系统的情况点击“64-Bit Graphical Installer”或“32-Bit Graphical Installer”进行下载。

    2. 完成下载之后，双击下载文件，启动安装程序。

    注意：
    ① 如果在安装过程中遇到任何问题，那么暂时地关闭杀毒软件，并在安装程序完成之后再打开。

    ② 如果在安装时选择了“为所有用户安装”，则卸载Anaconda然后重新安装，只为“我这个用户”安装。

    3. 选择“Next”。

    4. 阅读许可证协议条款，然后勾选“I Agree”并进行下一步。

    5. 除非是以管理员身份为所有用户安装，否则仅勾选“Just Me”并点击“Next”。

    6. 在“Choose Install Location”界面中选择安装Anaconda的目标路径，然后点击“Next”。

    注意：
    ① 目标路径中不能含有空格，同时不能是“unicode”编码。

    ② 除非被要求以管理员权限安装，否则不要以管理员身份安装。

    7. 在“Advanced Installation Options”中不要勾选“Add Anaconda to my PATH environment variable.”

    8. 点击“Next”。

    9. 进入“Thanks for installing Anaconda!”界面则意味着安装成功，点击“Finish”完成安装。

    10. 验证安装结果。可选以下任意方法：

    ① “开始 → Anaconda3（64-bit）→ Anaconda Navigator”，若可以成功启动Anaconda Navigator则说明安装成功。
    
    https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/ana1.png

    ② “开始 → Anaconda3（64-bit）→ 右键点击Anaconda Prompt → 以管理员身份运行”，在Anaconda Prompt中输入 conda list ，可以查看已经安装的包名和版本号。若结果可以正常显示，则说明安装成功。
    
    https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/ana2.png
    


## 三. 使用Anaconda Navigator启动Notebook

### 1. 启动Anaconda Navigator导航界面，并从导航界面启动Jupyter Notebook。
https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/anaconda%20navigator.png
https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/jupyte.png


### 2. Notebook启动之后，默认的Files列出了用户文件夹的项目，那么如何更改默认加载的目录呢？

1. 生成配置文件
在开始菜单里找到并打开Anaconda Prompt，输入如下命令，然后执行。

    jupyter notebook --generate-config


然后就可以看到配置文件生成的目录了

https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/%E6%94%B9%E5%9C%B0%E5%9D%801.png
https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/%E6%94%B9%E5%9C%B0%E5%9D%804.png

2. 打开生成的配置文件:

找到并修改如下配置项:

修改前: #c.NotebookApp.notebook_dir = ‘’

删除前面的 # 号，在后面的单引号里输入要设置的目录路径，保存关闭。

https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/%E6%94%B9%E5%9C%B0%E5%9D%805.png

3. 在win开始菜单中找到jupyter notebook快捷图标，更多>>打开文件位置>>鼠标右键点击Jupyter Notebook (Anaconda3)>>属性
删除最后面的 “%USERPROFILE%/” 点击确定


4.再次打开jupyter-notebook发现工作目录已经变成刚才设定的工作目录了。
https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/%E6%94%B9%E5%9C%B0%E5%9D%802.png

### 3. 新建一个Notebook（Python 3），查看界面布局，并尝试写一些文本和代码。

https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/%E5%88%9B%E5%BB%BA1.png
https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C1/%E5%88%9B%E5%BB%BA2.png
