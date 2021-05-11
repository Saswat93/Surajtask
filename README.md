## DONOT FORK THIS REPO , CLONE IT AND USE IT

## Usage

0) Edit `terraform.tfvars`. In particular, specify a valid AWS account.

1) Provision the infrastructure (and deploy the app on instance start):
    ```
    terraform init; terraform apply --auto-approve
    ```
    1.1) Case you change any part of the infrastructure, repeat step 1).

2) To tear down the infrastructure, run:
    ```
    terraform init; terraform destroy --auto-approve
    ```

<hr/>

## Notes



* this module **deploys one EC2** instance  
  * upon start, the machine runs the *deploy-hello-node.js* script, which  
  * pulls and runs the *[Hello-World docker app](https://hub.docker.com/repository/docker/saswatpattnaik21/suraj)*.
  * the instance is not configured with an SSH key, so logging into the instance is not possible.
* the app is **acessible via load-balancer** DNS.
* the app is accessible via instance public ip (will be removed in future versions). 
* AMI's are region specific
  * if you change the region, you must change the AMI
* this application is **not** covered by the AWS free tier.
  * destroy the resources as soon as you do not need them anymore  
