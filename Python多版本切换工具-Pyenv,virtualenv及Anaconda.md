��װAnaconda��ѧ���㻷�������ƺ�python�汾


�����python�����£�python�汾�л��Ĺ���--pyenvӦ�˶�����
ͬʱ������һ������virtualenv���ṩ��һ�ֹ��ܣ� ���ǽ�һ��Ŀ¼����Ϊһ�������python������ 


Unixϵͳ��pyenv��װ��ʹ��:
1.��װpyenv
$ git clone https://github.com/yyuu/pyenv.git ~/.pyenv     #ʹ�� git �� pyenv ���ص���Ŀ¼
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc     #Ȼ����Ҫ�޸Ļ���������ʹ�� Bash Shell ������

$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
$ echo 'eval "$(pyenv init -)"' >> ~/.bashrc     #������ pyenv init

$ exec $SHELL -l     #������������ Shell,Ȼ��Ϳ�������pyenv

�鿴pyenv�ɰ�װ�İ汾�б�
$ pyenv install --list

ԓ����г�pyenv���԰�װ���б�
2.7.8   # Python 2���°汾 
3.4.1   # Python 3���°汾
anaconda-2.4.0  # ֧��Python 2.6��2.7
anaconda3-2.0.1 # ֧��Python 3.3��3.4

��װָ����python�汾��
$ pyenv install 3.4.1  #��������github������python��Դ���밲װ

anaconda-2.4.0��python2.7������ �� anaconda3-2.4.0��python3.4��������
����ѡ�񶼰�װ��֮�����ʹ��pyenv���а汾���л���

ע��
��������pyenv���װ��python�汾����װ��~.pyenv/versions�ļ����£���Ȼ��������ͼ�ν������Ubuntu���û���Ŀ¼�¿��ܿ�����.pyenv�ļ��У���ʱ�������ʹ��ls -a�������ص��ļ��С�

ʹ��pip��װ�İ����֮�󣬿�����Ҫ�����ݿ���и���:
pyenv rehash

ж��ָ����python�汾��
pyenv uninstall x.x.x

python�汾�鿴��
pyenv versions

python�汾�л���
ȫ�ְ汾�л���
pyenv global anaconda-2.4.0

�ֲ��������л�����test�ļ�����ϣ���л���python3.4.1:
pyenv local python3.4.1

python virtualenv  #�����������⻷��

��װ���pyenv-virtualenv��
�ο����£�http://www.tiny-coder.com/home-article-51.html
pyenv-virtualenv�����װ����Ŀ��ҳ��https://github.com/yyuu/pyenv-virtualenv
pyenv virtualenv��pyenv�Ĳ����ΪUNIXϵͳ�ϵ�Python virtualenvs�ṩpyenv virtualenv���

git clone https://github.com/yyuu/pyenv-virtualenv.git ~/.pyenv/plugins/pyenv-virtualenv
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bash_profile
source ~/.bash_profile
����������װ�����ļ����µ�.pyenv�ļ����С�

����һ��2.7.1�����⻷����
pyenv virtualenv 2.7.1 env271
����Ҫ�������⻷�����ļ����´������⻷����
�����������ʵĿ¼λ�ڣ�~/.pyenv/versions/

�л���ʹ���µ�python���⻷����
pyenv activate env271

pyenv deactivate
�����Ҫɾ��������⻷����
rm -rf ~/.pyenv/versions/env271/

����ж�أ�
pyenv uninstall env271


2.Anaconda��ѧ�������ʹ�ã�
ʹ��conda list�鿴anaconda��װ�Դ��İ���
conda list

ע��
ʹ��conda list����Ļ���ʱpython�汾�л���anaconda�汾�£���Ȼ����������޷�����ѯ��

��anaconda��װ����
conda install ��������

[package-name]=x.x #ָ�����İ汾


3.���Python�汾���棬������2.x��3.x�Ĳ��档
���ͨ��virtualenv����������AnacondaҲ����ͨ����ʵ�ֵġ�
������conda����һ������python2�İ汾Ϊpython2.7�Ļ�����

conda create -n python2 python=2.7

ֱ����conda install����-nָ����װ���Ļ�����������Ȼ����python2��
��virtualenv��������activate��Ȼ�������⻷���а�װ��

conda create -n py34 python=3.4 anaconda

��pycharm����preference --> project --> project interpreter-->
Windowsϵͳ�л�
���ȵ�Ȼ�ǰ�װ����Ҫ��������ͬ�汾��python���Ұ�װ����2.7��3.4�ģ������汾��װ˳������ν�����Ǻ��氲װ�Ļ���Ĭ�ϵģ���Ϊ���Ǻ�װ��python 3.4�����ͱ����Ĭ�ϵ�python����

Ȼ��ȥpython27�ļ��������python.exe����python2.exe��Ȼ��Ϳ�������������ͨ��python����py������3.x��python2������2.x��

����pip�Ļ�ֱ��ʹ�� pip2 ���� pip3 �Ϳ����ˡ�

virtualenv��
sudo pip install virtualenv

Ϊ�����Ŀ����������Python������
mkdir my_project_venv
virtualenv --distribute my_project_venv


ͨ�����������������⻷����
cd my_project_venv
source bin/activate
ʹ��source��������activate�ű�֮�������������ʾ��Ӧ�û���������
(my_project_venv)$  ���⻷�������ƻ������$��ʾ����ǰ�档

�����������������ر����⻷����
(my_project_venv)$ deactivate

���ȣ���������������������ն�����python����pip��ϵͳ��ʹ���ĸ�ִ���ļ���
$ which python
/usr/bin/python
$ which pip
/usr/local/bin/pip

�ο���
pyenv
Python��汾����֮pyenv
yyuu/pyenv-github
��pyenv �� virtualenv �������汾python ���⿪������
lixm/pybooklet-github
ʹ�� pyenv �� Miniconda ���� Python ��ѧ���㻷��
Python 2.X 3.X ��汾����
һƪ��������Python��̬ϵͳ
��pyenv��virtualenv�python���⻷��