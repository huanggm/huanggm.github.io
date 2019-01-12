git
nvm
node
npm

zsh  yum install zsh  apt-get install zsh
oh-my-zsh
curl
wget

python
go

centos: yum
Debian: apt-get : apt-get install git :  apt-get update && apt upgrade







yum install -y wget
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
yum clean all
make clean
yum makecache
yum update
yum install -y gcc gcc-c++ make openssl-devel vim* bison bison-devel zlib-devel mhash-devel ncurses-devel libxml2-devel libcurl-devel bzip2-devel readline-devel libedit-devel sqlite-devel libjpeg-turbo-devel libpng-devel freetype-devel autoconf automake mkfontscale mkfontdir fontconfig git zsh finger

sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | zsh
source ~/.zshrc
nvm install v8

wget https://dev.yorhel.nl/download/ncdu-1.13.tar.gz
tar zxvf ncdu-1.13.tar.gz
cd ncdu-1.13
./configure && make && make install

https://graphviz.gitlab.io/pub/graphviz/stable/SOURCES/graphviz.tar.gz
tar zxvf graphviz.tar.gz
cd graphviz-2.40.1
./configure && make && make install

[ag](https://github.com/ggreer/the_silver_searcher)
yum install the_silver_searcher
apt-get install silversearcher-ag

[tig](http://jonas.nitro.dk/tig/INSTALL.html)

[cloc](http://cloc.sourceforge.net/#apt-get)
npm install -g cloc

yum -y install epel-release
yum install python-pip
pip install --upgrade pip

pip install --upgrade httpie

[pv](https://www.tecmint.com/linux-funny-commands/)
yum install pv			[On RedHat based Systems]
sudo apt-get install pv	        [On Debian based Systems]
echo "Tecmint[dot]com is a community of Linux Nerds and Geeks" | pv -qL 10


[cmatrix](https://github.com/abishekvashok/cmatrix/releases)
wget https://github.com/abishekvashok/cmatrix/archive/1.2.tar.gz
tar zxvf 1.2.tar.gz
./configure && make && make install

[python多版本共存](https://github.com/pyenv/pyenv)
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bash_profile
exec "$SHELL"

[rvm](http://www.rvm.io/)
[rvm.io](https://rvm.io/rvm/security)
curl -sSL https://rvm.io/mpapis.asc | gpg --import -
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
curl -sSL https://get.rvm.io | bash -s stable

rvm requirements
rvm list known
rvm list
rvm install 2.4
rvm use 2.4 --default

[ruby](https://ruby-china.org/wiki/install_ruby_guide)
ruby -v
gem -v
gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/
gem install bundler
gem install rails
rails -v

## 网上看见的-debian系统
sudo apt-get install -y nginx-common nginx-extras


还差php nginx redis mysql mongodb memcache lua go jdk
