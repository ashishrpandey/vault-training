Create an AWS Account first 

    vault secrets enable -path=aws aws
    Success! Enabled the aws secrets engine at: aws/

Get the AWS Credentials 

    $ vault write aws/config/root \
        access_key=AKIAI4SGLQPBX6CSENIQ \
        secret_key=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 \
        region=us-east-1

    Success! Data written to: aws/config/root
    
Create an IAM Role

    vault write aws/roles/my-role \
            credential_type=iam_user \
            policy_document=-<<EOF
    {
      "Version": "2012-10-17",
      "Statement": [
        {
          "Sid": "Stmt1426528957000",
          "Effect": "Allow",
          "Action": [
            "ec2:*"
          ],
          "Resource": [
            "*"
          ]
        }
      ]
    }
    EOF
    Success! Data written to: aws/roles/my-role

Generate the secret

        $ vault read aws/creds/my-role
            Key                Value
            ---                -----
            lease_id           aws/creds/my-role/0bce0782-32aa-25ec-f61d-c026ff22106e
            lease_duration     768h
            lease_renewable    true
            access_key         AKIAJELUDIANQGRXCTZQ
            secret_key         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
            security_token     <nil>

Revoke the secret 

    $ vault lease revoke aws/creds/my-role/0bce0782-32aa-25ec-f61d-c026ff22106
    Success! Revoked lease: aws/creds/my-role/0bce0782-32aa-25ec-f61d-c026ff22106e
