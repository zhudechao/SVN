##Subversion源码安装
安装依赖

```
yum install expat-devel

```
下载源码

```
software]# wget https://mirror.olnevhost.net/pub/apache/subversion/subversion-1.14.0.tar.gz
```
编译安装

```
software]# wget https://mirrors.ocf.berkeley.edu/apache//apr/apr-1.7.0.tar.gz
./configure \
--prefix=/usr/local/apr-httpd/
make
make install

software]# wget https://mirror.olnevhost.net/pub/apache//apr/apr-util-1.6.1.tar.gz
./configure \
--prefix=/usr/local/apr-util-httpd \
--with-apr=/usr/local/apr-httpd/bin/apr-1-config

make
make install


software]# tar -zxvf subversion-1.14.0.tar.gz

./configure \
--prefix=/usr/local/subversion \
--with-apr=/usr/local/apr-httpd \
--with-apr-util=/usr/local/apr-util-httpd \
--with-lz4=internal \
--with-utf8proc=internal
```

出错

```
configure: error: Subversion requires SQLite
解决办法:
下载sqlite-amalgamation
把文件都放到subversion-1.14.0/sqlite-amalgamation 目录下
```