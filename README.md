# aws-eks-user-management
The workflow is as follows:
1. We execute the module "eks-cluster" which creates a custom vpc and an eks cluster.
2. With the module "create-user" we will create clusterRole, clusterRoleBinding, IAM user with the necessay permissions.
   After executing the module, then we can create a profile for the user -by firstly creating secret/access keys for the
   user on aws console. WE use these keys to configure/create a profile for the user. After which we then update the configmap/aws-auth
   with the user information. This makes it possible for the user to be authen ticated and authorised when he makes API call into the cluster.
   But what task he can accomplish/perform inside the cluster depends on the permissions defined in the clusterRole and clusterRoleBinding.
