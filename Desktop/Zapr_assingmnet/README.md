Pre-requisites
We have have aws cli configured before so that terraform know how to interact aws  All together 18 resources will be deployed

1. VPC
2. Two public subnet
3. Route table and the route table association
4. Internet gateway(once created , it will get attached to VPC)
5. EKS-cluster (which contains Master node)
6. Node group (which contains worker node)
7. Security group
8. Ingress attached to SG
9. Two IAM rules for worker and Master node
10.  Five policy (2 for worker and 3 for master)

STEPS INCLUDED
=============

terraform init : it will download all the providers that are being used , like the plugins for aws providers
terraform plan : it will not apply anything, just show what resources are being created etc
terraform  apply: to provision all the resources



Notes
======
1. If we wish to change the name of the cluster we can change it elks-cluster.tf (the values being passed by variable.tf)
2. nodes group are defined in ems-worker.tf
3. Iam role for master defined in eks-cluster.tf
4. Iam role for worker defined in eks-worker.tf
5. Internet gateways defined in  vpc.tf
6. Route-tables defined in Vpc.tf
7. Security group defined in vac.tf
8. Info about region provided in provider.tf (if we wish to change the region we can change it from provider.tf)
9. We can increase the worker node by editing the scaling-config as per our need

**Once all the changes are done run the terraform plan

After installation we wont be able to view the output Kubernetes command for this we need too install IAM authenticator 
Now we can create/run our container (Example kubectl run nginx —image nginx)


