

By default Vault enables a secret engine called kv at a path secret/
Other secret engines are -  
- kv
- AWS 
- database 

Enable the ks secret at path /kv 
   
      vault secrets enable -path=kv kv
      Success! Enabled the kv secrets engine at: kv/

