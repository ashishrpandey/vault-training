
## Store a secret 
     vault kv put secret/mysecret company=zekeLabs
     

## Store multiple secrets
     vault kv put secret/mysecret company=zekeLabs location=bangalore
   
## Get those secrets 
    vault kv get  secret/mysecret
    
## Warning 
*********Always use files to store ******

## retrieve the secrets in a better way; for automation

     vault kv get -format=json secret/mysecret
     vault kv get -format=json secret/mysecret | jq -r .data.data.company
     
     
## Delete a key 

    vault kv delete secret/mysecret  
    
    


