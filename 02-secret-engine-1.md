
## Secret Engines 

By default Vault enables a secret engine called kv at a path secret/
Other secret engines are -  
- kv
- AWS 
- database 


Enable the kv secret at path kv/ 
   
      vault secrets enable -path=kv kv
      Success! Enabled the kv secrets engine at: kv/
      
- It is same as 
      
      vault secrets enable kv 

- List all the secret engines 

      vault secrets list
      Path          Type         Accessor              Description
      ----          ----         --------              -----------
      cubbyhole/    cubbyhole    cubbyhole_980ef0cb    per-token private secret storage
      identity/     identity     identity_0681b249     identity store
      kv/           kv           kv_dec31d3e           n/a
      secret/       kv           kv_02d14949           key/value secret storage
      sys/          system       system_2331176a       system endpoints used for control, policy and debugging

## Disable the secret engine

    vault secrets disable kv
    Success! Disabled the secrets engine (if it existed) at: kv/

Check for the previous secrets stored in kv
