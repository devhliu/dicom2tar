Bootstrap: docker
From: ubuntu:xenial

%files
dicom2tar.py 

#------------------------------------
%post
#------------------------------------

export DEBIAN_FRONTEND=noninteractive
apt-get update && apt-get install -y --no-install-recommends apt-utils \
    sudo \
    git \
    wget \
    curl \
    zip \
    unzip \
    python2.7 \
    python-pip \
    rsync \
    openssh-client

pip install -U pip setuptools

git clone https://www.github.com/pydicom/pydicom.git
cd pydicom
git checkout 1314e86e3a96d0c226a03fb21136c0ff3c3ce7d3  #commit from Feb 1 2018
python setup.py install


%runscript 
exec /dicom2tar.py $@

