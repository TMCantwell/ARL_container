BootStrap: yum
OSVersion: 7
MirrorURL: http://mirror.centos.org/centos-%{OSVERSION}/%{OSVERSION}/os/$basearch/
Include: yum wget

%post -c /bin/bash
yum -y update
yum -y install yum-utils
yum -y groupinstall development
yum -y install https://centos7.iuscommunity.org/ius-release.rpm
yum -y install curl
yum -y install epel-release
yum -y install git
curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.rpm.sh | bash
yum -y install git-lfs
git lfs install
yum -y install python36u-devel python36u-pip python36u-tkinter python-virtualenv python-virtualenvwrapper
export WORKON_HOME=$HOME/.virtualenvs
source /usr/bin/virtualenvwrapper.sh
yum -y install graphviz
yum -y install openmpi mpi4py-openmpi
yum -y install cfitsio-devel
pip3 install pipenv
virtualenv -p python3.6 /arlvenv
alias start-arlvenv="source /arlvenv/bin/activate"
. /arlvenv/bin/activate
pip install pytest
pip install pylint
pip install mpi4py
pip install jupyter
pip install matplotlib
git clone https://github.com/SKA-ScienceDataProcessor/algorithm-reference-library
chmod 755 algorithm-reference-library
cd algorithm-reference-library
pip install -r requirements.txt
python setup.py install
git-lfs pull
export PYTHONPATH=/algorithm-reference-library:$PYTHONPATH
add2virtualenv /algorithm-reference-library


%environment
alias start-arlvenv="source /arlvenv/bin/activate"
export PYTHONPATH=/algorithm-reference-library:$PYTHONPATH
export XDG_RUNTIME_DIR=""
