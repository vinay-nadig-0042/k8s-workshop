# k8s-workshop
### Step 1 - Launch an EC2 Instance with Admin IAM role

### Step 2 - Install kops

https://github.com/kubernetes/kops/blob/master/docs/install.md#linux

### Step 3 - Install kubectl

https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-using-native-package-management

### Step 4 - Create S3 Bucket

Format - k8s-workshop-grab-&lt;yourname&gt;

Example - k8s-workshop-grab-vinay

### Step 5 - Create SSH Key Pair

```
ssh-keygen -t rsa -b 4096 -C "yourmailid@mail.com"
```

**DO NOT PROVIDE A PASSPHRASE WHEN PROMPTED - LEAVE EVERYTHING IN DEFAULT**

### Step 5 - Deploy K8s Cluster

```
kops create cluster --zones=ap-southeast-1a,ap-southeast-1b,ap-southeast-1c --master-zones=ap-southeast-1a,ap-southeast-1b,ap-southeast-1c --node-count=3 --node-size=t2.medium --master-size=t2.medium --state=s3://<bucket-name-here> --name=<yourname>.k8s.local --yes
```

###Step 6 - Validate Cluster

```
kubectl cluster-info
```

