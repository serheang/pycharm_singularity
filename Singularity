Bootstrap: yum
OSVersion:7
MirrorURL: http://mirror.centos.org/centos/%{OSVersion}/os/$basearch/

Include: yum tar gzip

%label
  Maintainer setan
  Whatami pycharm-edu
  Version 2018.3
  URL https://download.jetbrains.com/python/pycharm-edu-2018.3.tar.gz

%environment
  export PATH=/usr/local/bin/:$PATH

%post
  yum update -y
  yum install -y epel-release
  yum install -y wget tar gzip which
  yum install -y libXext libXrender libXtst libXi freetype 
  yum install -y python36 python36-pip
  yum install -y python python-pip
  yum clean all
  yum clean metadata

  ## CLEANUP
  rm -f  pycharm-edu*.tar.gz
  rm -rf /opt/pycharm-edu-2018.3
  rm -f /opt/pycharm
  rm -f /usr/local/bin/pycharm
  rm -f /usr/local/bin/inspect

  ## INSTALL
  wget https://download.jetbrains.com/python/pycharm-edu-2018.3.tar.gz
  tar zxvf pycharm-edu-2018.3.tar.gz -C /opt
  ln -s /opt/pycharm-edu-2018.3 /opt/pycharm
  ln -s /opt/pycharm/bin/pycharm.sh /usr/local/bin/pycharm
  ln -s /opt/pycharm/bin/inspect.sh /usr/local/bin/inspect
  rm pycharm-edu-2018.3.tar.gz

%runscript
  echo "Run Pycharm"
  pycharm

%help
This is PyCharm in yum container.
