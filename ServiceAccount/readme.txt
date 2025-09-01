kubectl apply -f dev/ -n argocd
persistentvolumeclaim/azure-managed-disk-pvc unchanged
configmap/usermanagement-dbcreation-script unchanged
secret/mysql-db-password created
vrinc@Vrinceanu:~/master/test/WebApplication_and_MYSQL_Pod_Deployment$ kubectl delete -f dev/08-Kubernetes-Secrets.yml -n argocd
secret "mysql-db-password" deleted
vrinc@Vrinceanu:~/master/test/WebApplication_and_MYSQL_Pod_Deployment$ kubectl apply -f ServiceAccount/09-ServiceAccount.yaml 
serviceaccount/usermgmt-sa configured
vrinc@Vrinceanu:~/master/test/WebApplication_and_MYSQL_Pod_Deployment$ kubectl apply -f ServiceAccount/09-ServiceAccount.yaml -n argocd
serviceaccount/usermgmt-sa unchanged
vrinc@Vrinceanu:~/master/test/WebApplication_and_MYSQL_Pod_Deployment$ kubectl apply -f ServiceAccount/SecretProviderClass.yaml -n arg
ocd
secretproviderclass.secrets-store.csi.x-k8s.io/mysql-kv-provider unchanged
vrinc@Vrinceanu:~/master/test/WebApplication_and_MYSQL_Pod_Deployment$ kubectl apply -f dev-db/05-mysql-clusterip-service.yml -n argocd
service/mysql created
vrinc@Vrinceanu:~/master/test/WebApplication_and_MYSQL_Pod_Deployment$ kubectl apply -f dev-webapp/07-UserMgmtWebApp-Service.yml -n ar
gocd
service/usermgmt-webapp-service created
vrinc@Vrinceanu:~/master/test/WebApplication_and_MYSQL_Pod_Deployment$ kubectl apply -f application-ServiceAccount_Key_Vault.yaml -n a
rgocd
application.argoproj.io/myapp-webapp-argo-application created