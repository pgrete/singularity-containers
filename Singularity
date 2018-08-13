################################################################################
# Basic bootstrap definition to build CentOS 7 container from Docker container
################################################################################
 
BootStrap: docker
From: nvidia/cuda:9.0-runtime-centos7
 
################################################################################
# Copy any necessary files into the container
################################################################################
%files
#~/my_file /path/in/container
 
%post
################################################################################
# Install additional login shells for users that need them
################################################################################
#yum -y install tcsh ksh zsh
 
################################################################################
# Install additional packages
################################################################################
#yum -y install vim
curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.rpm.sh | bash
yum -y install wget gitlab-runner numpy bc hwloc
yum groupinstall 'Development Tools'
wget http://developer.download.nvidia.com/compute/cuda/repos/rhel7/x86_64/cuda-repo-rhel7-9.0.176-1.x86_64.rpm
yum clean all
yum -y install cuda-libraries-dev-9-0.x86_64 cuda-nvml-dev-9-0.x86_64 cuda-minimal-build-9-0.x86_64 cuda-command-line-tools-9-0.x86_64 cuda-core-9-0=9.0.176.3-1 cuda-cublas-dev-9-0=9.0.176.4-1

 
################################################################################
# Create directories to enable access to common HPCC mount points
################################################################################
mkdir -p /mnt/home
mkdir -p /mnt/research
mkdir -p /mnt/dfs17
mkdir -p /mnt/ffs17
mkdir -p /mnt/local
mkdir -p /mnt/ls15
mkdir -p /opt/software

