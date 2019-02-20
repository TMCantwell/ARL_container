Bootstrap: debootstrap
OSVersion: zesty
MirrorURL: http://old-releases.ubuntu.com/ubuntu/

%post
apt-get -y update
apt-get -y install apt-utils
apt-get -y install software-properties-common build-essential curl
add-apt-repository -y ppa:git-core/ppa
curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | bash
apt-get -y install git-lfs
git lfs install
apt-get -y install python3.6-dev python3-pip python3-tk virtualenv virtualenvwrapper
apt-get -y install graphviz
apt-get -y install libopenmpi-dev
apt-get -y install libcfitsio-dev
pip3 install pipenv
virtualenv -p python3.6 /arlvenv
alias start-arlvenv="source /arlvenv/bin/activate"
start-arlvenv
pip install bokeh
pip install pytest
pip install pylint
pip install mpi4py
git clone https://github.com/SKA-ScienceDataProcessor/algorithm-reference-library
cd algorithm-reference-library
pip install -r requirements.txt
python setup.py install
git-lfs pull
export PYTHONPATH=/algorithm-reference-library:$PYTHONPATH
add2virtualenv /algorithm-reference-library


%environment
alias start-arlvenv="source /arlvenv/bin/activate"
export PYTHONPATH=/algorithm-reference-library:$PYTHONPATH
