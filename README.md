# Install vim from source on Centos
- 移除旧版本`sudo yum remove vim`
- 安装库
  ```shell
  sudo yum install -y ruby ruby-devel lua lua-devel luajit \
  luajit-devel ctags git python python-devel \
  python3 python3-devel tcl-devel \
  perl perl-devel perl-ExtUtils-ParseXS \
  perl-ExtUtils-XSpp perl-ExtUtils-CBuilder \
  perl-ExtUtils-Embed libX11-devel
  ```
- 下载源码`git clone clone https://github.com/vim/vim.git`
- `cd ./vim/src`
- 编译
  ```shell
  1. ./configure --with-features=huge --enable-python3interp --enable-pythoninterp --with-python-config-dir=/usr/lib/python2.7/config-x86_64-linux-gnu/ --enable-rubyinterp --enable-luainterp --enable-perlinterp --with-python3-config-dir=/usr/lib/python3.5/config-3.5m-x86_64-linux-gnu/ --enable-multibyte --enable-cscope --prefix=/usr/local/vim/
  2. make && make install 
  ```
  
  > 其中 ./configure 主要是为了生成支持python的makefile，--prefix 选项是保存最终编译好的vim二进制文件和库的目录
  
- 最终的编译好的vim路径在`/usr/local/vim/bin`之中,可以通过`export PATH=$PATH:/usr/local/vim/bin`指定vim的加载路径
- `vim --version`查看编译好的vim 版本信息

