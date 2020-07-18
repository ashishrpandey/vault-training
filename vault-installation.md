

## Update yum on Centos
Update yum utilities - 

    sudo yum -y install vault
    sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo

Add the section below in  
/etc/yum.repos.d/hashicorp.repo


    [hashicorp]
    name=Hashicorp Stable - $basearch
    baseurl=https://rpm.releases.hashicorp.com/RHEL/7/$basearch/stable
    enabled=1
    gpgcheck=1
    gpgkey=https://rpm.releases.hashicorp.com/gpg

    [hashicorp-test]
    name=Hashicorp Stable - $basearch
    baseurl=https://rpm.releases.hashicorp.com/RHEL/7/$basearch/test
    enabled=0
    gpgcheck=1
    gpgkey=https://rpm.releases.hashicorp.com/gpg


## Install vault

    yum install vault -y 

## Verify 
  
    vault -version 
    vault -h 
    
## Install auto-completion
  
    vault -autocomplete-install
    exec $SHELL
    
Try writing "vault" followed by space and "tab"
The commnands will autocomplete . 


## Start the server 

    vault server -dev




  
