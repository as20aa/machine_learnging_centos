# machine_learnging_centos
Configure environment for machine learning(关于如何在Centos中配置机器学习环境，中文说明在文档后半部分)
# English Part
# Require dependencies
* gcc/gcc-c++
* openssl openssl-devel
* zlib
* cmake
* Python3.6.6

# Install the dependencies above
```bash
yum update
yum upgrade
yum install gcc
yum install gcc-c++
yum -y install openssl openssl-devel
yum -y install zlib
yum install cmake
```
You can copy those bash above and paste them in your bash shell. If you are not login in as root, please ensure that you have encough privalege and add sudo before using those command.

Because the centos can't install python3.6 via yum. so we have to donwload the source and install manually.
```bash
# Download the python3.6.6 via wget
wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tgz
# unzip the tar package
tar -zxvf Python-3.6.6.tgz
cd Python-3.6.6
# install python3.6.6 to /usr/
./configure --prefix=/usr
# make the source
# change the Setup.dist file
sed -i -e s/#_ssl/_ssl/ -e'/_ssl/{n;s/#//;{n;s/#//;}}' Modules/Setup.dist
make
# install
make install
```
After installation, input python3 to check whether you enter the python shell.
# Install the python packages
## Packages needed to be installed
* numpy
* pandas
* scipy
* sklearn
* jieba
```bash
python3 pip install -U numpy pandas scipy sklearn jieba
```
# 中文部分
# 系统需安装软件
* gcc/gcc-c++
* openssl openssl-devel
* zlib
* cmake
* Python3.6.6
# 安装上述软件
```bash
yum update
yum upgrade
yum install gcc
yum install gcc-c++
yum -y install openssl openssl-devel
yum -y install zlib
yum install cmake
```
你可以将上述命令复制粘贴至linux的shell界面，并执行。如果你不是以管理员身份登录，可以在每行命令前加上sudo            
因为Centos不能直接通过yum安装python3.x的版本（yum本身依赖python2.x，故系统自带了python2.7的版本），我们需要重新下载一个python3.6.6的源码进行安装
```bash
# 用wget获取安装包
wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tgz
# 解压包
tar -zxvf Python-3.6.6.tgz
# 进入python3.6.6源码的目录下
cd Python-3.6.6
# 配置安装Python3到/usr目录下
./configure --prefix=/usr
# 配置安装文件
sed -i -e s/#_ssl/_ssl/ -e'/_ssl/{n;s/#//;{n;s/#//;}}' Modules/Setup.dist
# 编译源码文件
make
# 安装文件
make install
```
安装完成之后，可以在shell界面敲入python3查看是否安装成功
# 安装python包
## 需要安装的python包
* numpy
* pandas
* scipy
* sklearn
* jieba
```bash
python3 pip install -U numpy pandas scipy sklearn jieba
```