安装Anaconda科学计算环境，控制好python版本


解决多python环境下，python版本切换的工具--pyenv应运而生。
同时，另外一个工具virtualenv则提供了一种功能， 就是将一个目录建立为一个虚拟的python环境， 


Unix系统下pyenv安装与使用:
1.安装pyenv
$ git clone https://github.com/yyuu/pyenv.git ~/.pyenv     #使用 git 把 pyenv 下载到家目录
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc     #然后需要修改环境变量，使用 Bash Shell 的输入

$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(pyenv init -)"' >> ~/.bashrc     #最后添加 pyenv init

$ exec $SHELL -l     #输入命令重启 Shell,然后就可以重启pyenv

查看pyenv可安装的版本列表
$ pyenv install --list

該命令将列出pyenv可以安装的列表：
2.7.8   # Python 2最新版本 
3.4.1   # Python 3最新版本
anaconda-2.4.0  # 支持Python 2.6和2.7
anaconda3-2.0.1 # 支持Python 3.3和3.4

安装指定的python版本。
$ pyenv install 3.4.1  #该命令会从github上下载python的源代码安装

anaconda-2.4.0（python2.7环境） 和 anaconda3-2.4.0（python3.4环境）。
可以选择都安装，之后可以使用pyenv进行版本的切换。

注：
这里利用pyenv命令安装的python版本都安装在~.pyenv/versions文件夹下，当然，如果你从图形界面进入Ubuntu的用户主目录下可能看不见.pyenv文件夹，这时候，你可以使用ls -a看到隐藏的文件夹。

使用pip安装的包完成之后，可能需要对数据库进行更新:
pyenv rehash

卸载指定的python版本：
pyenv uninstall x.x.x

python版本查看：
pyenv versions

python版本切换：
全局版本切换：
pyenv global anaconda-2.4.0

局部环境的切换：在test文件夹下希望切换到python3.4.1:
pyenv local python3.4.1

python virtualenv  #创建纯净虚拟环境

安装插件pyenv-virtualenv：
参考文章：http://www.tiny-coder.com/home-article-51.html
pyenv-virtualenv插件安装：项目主页：https://github.com/yyuu/pyenv-virtualenv
pyenv virtualenv是pyenv的插件，为UNIX系统上的Python virtualenvs提供pyenv virtualenv命令。

git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bash_profile
source ~/.bash_profile
这个插件将安装在主文件夹下的.pyenv文件夹中。

创建一个2.7.1的虚拟环境：
pyenv virtualenv 2.7.1 env271
再需要创建虚拟环境的文件夹下创建虚拟环境。
这个环境的真实目录位于：~/.pyenv/versions/

切换和使用新的python虚拟环境：
pyenv activate env271

pyenv deactivate
那如果要删除这个虚拟环境呢
rm -rf ~/.pyenv/versions/env271/

或者卸载：
pyenv uninstall env271


2.Anaconda科学计算包的使用：
使用conda list查看anaconda安装自带的包：
conda list

注：
使用conda list命令的环境时python版本切换到anaconda版本下，不然，这个命令无法来查询。

给anaconda安装包：
conda install ××××

[package-name]=x.x #指定包的版本


3.多个Python版本并存，尤其是2.x和3.x的并存。
这个通过virtualenv可以做到。Anaconda也正是通过其实现的。
下面用conda创建一个名叫python2的版本为python2.7的环境。

conda create -n python2 python=2.7

直接用conda install并用-n指明安装到的环境，这里自然就是python2。
像virtualenv那样，先activate，然后在虚拟环境中安装。

conda create -n py34 python=3.4 anaconda

打开pycharm，打开preference --> project --> project interpreter-->
Windows系统切换
首先当然是安装你需要的两个不同版本的python，我安装的是2.7和3.4的，两个版本安装顺序无所谓，但是后面安装的会变成默认的（因为我是后安装的python 3.4，它就变成了默认的python）。

然后去python27文件夹下面把python.exe改名python2.exe，然后就可以在命令行下通过python或者py来调用3.x，python2来调用2.x。

另外pip的话直接使用 pip2 或者 pip3 就可以了。

virtualenv：
sudo pip install virtualenv

为你的项目创建孤立的Python环境：
mkdir my_project_venv
virtualenv --distribute my_project_venv


通过下面的命令，激活虚拟环境：
cd my_project_venv
source bin/activate
使用source命令启动activate脚本之后，你的命令行提示符应该会变成这样：
(my_project_venv)$  虚拟环境的名称会添加在$提示符的前面。

现在运行下面的命令，关闭虚拟环境：
(my_project_venv)$ deactivate

首先，我们来看看如果我们在终端输入python或者pip，系统会使用哪个执行文件。
$ which python
/usr/bin/python
$ which pip
/usr/local/bin/pip

参考：
pyenv
Python多版本共存之pyenv
yyuu/pyenv-github
用pyenv 和 virtualenv 搭建单机多版本python 虚拟开发环境
lixm/pybooklet-github
使用 pyenv 和 Miniconda 管理 Python 科学计算环境
Python 2.X 3.X 多版本共存
一篇文章入门Python生态系统
用pyenv和virtualenv搭建python虚拟环境