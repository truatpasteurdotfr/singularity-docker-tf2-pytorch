BootStrap: docker
From: tensorflow/tensorflow:latest-gpu
# https://hub.docker.com/r/tensorflow/tensorflow/


%post

export DEBIAN_FRONTEND=noninteractive
apt-get  update
apt-get -y install bash environment-modules

# 1) tars.pasteur.fr is running CentOS-6: no overlays
# you must create the mount points otherwise, you won't be able to run your container..
mkdir /pasteur
# 2) you also need to load the proper singularity version with:
# module add singularity/VERSION
#
# pytorch from pip for cuda/10.1 (as tf2 is 10.1 only)
# https://pytorch.org/


python3 -m pip install torch==1.6.0+cu101 torchvision==0.7.0+cu101 -f https://download.pytorch.org/whl/torch_stable.html


%environment
# do not use ~/.local python
PYTHONNOUSERSITE=1
export PYTHONNOUSERSITE
#
