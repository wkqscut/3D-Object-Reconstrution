1.  211/66/7/48

2.  # 基于 python3.6 创建一个名为test_py3 的环境
    conda create --name test_py3 python=3.6 
    # 激活 test 环境
    source activate test_py3
    
3. 先执行 python setup.py build
   然后执行 python setup.py install
   
4. 安装到本地自定义目录  xx.sh --prefix=$HOME/local

5.  conda create -n caffetmp -c conda-forge caffe
    source activate caffetmp
    python -c 'import caffe'
(/home/lab-wang.kaiqi/anaconda2/envs/caffetmp)

6.  conda create -n py2 python=2.7
    activate py2
    deactivate

7,  wget:   
    wget -b -i url.txt -c >; log.txt
    -b 后台执行Wget；
    -i inputfiles 从文本文件内读取地址列表；
    -c 断点下传；
    -Y, –proxy=on/off  打开或关闭代理
    -r, –recursive  递归下载－－慎用!
    (多线程下载工具Axel
    axel [OPTIONS] url1 [url2] [url…]
    -n x  指定线程数（x 必须为大于 0 的数字）
    -o x  指定另存为目录（x 必须为本地目录）
    -s x  指定下载速度（x 必须为大于 0 的数字，单位是 bytes/s）
    -q    静默模式，无任何输出信息
    -V    软件版本)
    
8.  ./configure --prefix=$HOME/local
    export PATH=/home/lab-wang.xxxx/local/bin:$PATH

9. Linux下非root用户安装软件的一般流程：
    1)获取源代码，一般是wget方式，ubuntu可以使用apt-get source来获取源代码。
    2)解压源代码，一般使用tar -zxvf xxx.tar.gz即可
    3)切换到解压后的目录，运行 ./configure。其选项可以通过 ./configure –help来获取，非root用户下最重要的应该是定义安装目录，即应该定义 ./configure –prefix=/path/to/bin， 对于一些依赖库，可能还需要使用 ./configure  –prefix=xxx –with-xx-dir=xxx这种形式。
    4)接着是编译源代码和安装软件： make &&  make install。这两条命令可以分开来用，因为编译的时候可以指定参数 -j来并行编译，这样能够加快编译进度。。
    5)更新path路径。使用export PATH=/path/to/bin:$PATH，这句话在shell窗口运行只在本次会话中有效，可以将其写到.bashrc或者.bash_profile里面使其对当前用户有效。
    6)如果安装的是动态链接库，则需要更新动态链接库路径： export LD_LIBRARY_PATH=/path/to/library:$LD_LIBRARY_PATH，同样是export命令，最好将其写在.bashrc这类文件下面以便登陆的时候自动调用。
    

10.  BadDrawable (invalid Pixmap or Window parameter)
     add this line QT_X11_NO_MITSHM=1 in ~/.profile file
     
     
11.  sudo shutdown -r now

12. sudo apt-get clean  #删除没有用的deb软件安装包
    sudo apt-get autoclean
    
13. luarocks install --local xxx
	
14. conda install lua=5.2 lua-science -c alexbw

15. /home/lab-cai.xxxx/lab-wang.xxxx/caffe/build/install/include/caffe
>>> import sys 
>>> sys.path.append("/home/lab-cai.jinmiao/lab-wang.kaiqi/caffe/python")
>>> sys.path.append("/home/lab-cai.jinmiao/lab-wang.kaiqi/caffe/python/caffe")
>>> import caffe

16. $ wget -i filename.txt  此命令常用于批量下载的情形，把所有需要下载文件的地址放到 filename.txt 中，然后 wget 就会自动为你下载所有文件了。
    $ wget -c http://example.com/really-big-file.iso  这里所指定的 -c 选项的作用为断点续传。
    
17. require "python"
pg = python.globals()
pos = pg.import("os")
x = pos.listdir(".")
print(x)

18. sudo mount /dev/sde  /data2
vi /etc/fstab

19. echo xfce4-session >~/.xsession   # 远程桌面
