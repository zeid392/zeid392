- 👋Deleting the Virtual User
After you define an identity provider, create a new user, and assign that user the cluster-admin
role, you can remove the kubeadmin user credentials to improve cluster security.
[user@demo ~]$ oc delete secret kubeadmin -n kube-system


oc get oauth cluster -o yaml > oauth.yaml

apiVersion: config.openshift.io/v1
kind: OAuth
metadata:
name: cluster
spec:
identityProviders:
- name: my_htpasswd_provider
mappingMethod: claim
type: HTPasswd
htpasswd:
fileData:
name: htpasswd-secret



