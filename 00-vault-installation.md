

## Update yum on Centos
Update yum utilities - 

    sudo yum -y install vault
    sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo
    sudo sed -i s/\$releasever/7/g /etc/yum.repos.d/hashicorp.repo



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

## Store the env variables
Open another terminal and collect and store somewhere VAULT_ADDR, Unseal Key and Root token from the utput and save it somewhere safe
   
     Unseal Key: wpmMqONasIkCrBJv01fcrrA8HhTbnF+IhZ+vCw0=
     Root Token: s.Afex2WcTqVT1tv4WydfasfN5

Export these variables 

    export VAULT_ADDR='http://127.0.0.1:8200'
    export VAULT_DEV_ROOT_TOKEN_ID="s.Afex2WcTqVT1tv4WydfasfN5"
    
  ## Check the Vault status 
  Check the status of the Vault 
    
        [root@ip-172-31-46-86 ~]# vault status
        Key             Value
        ---             -----
        Seal Type       shamir
        Initialized     true
        Sealed          false
        Total Shares    1
        Threshold       1
        Version         1.4.3
        Cluster Name    vault-cluster-036b
        Cluster ID      ad90d754-305b-71c0e1-07ca1e953434
        HA Enabled      false




  
