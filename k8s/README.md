### Step 1-: install the kubernetes in ubuntu
.Go tho the file kubernetes_install

### Step2 -:Create the kubernetes Dashboard for Admin user
~~~
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml
~~~
check the all pod is running or not
~~~
kubectl get pods -A
~~~
Apply the command below
~~~
kubectl apply -f adminuser.yaml
kubectl get secret -n kubernetes-dashboard $(kubectl get serviceaccount admin-user -n kubernetes-dashboard -o jsonpath="{.secrets[0].name}") -o    jsonpath="{.data.token}" | base64 --decode
kubectl apply -f dashboard-read-only.yaml
~~~
**To allow users to log in via the read-only account
~~~
kubectl get secret -n kubernetes-dashboard $(kubectl get serviceaccount read-only-user -n kubernetes-dashboard -o jsonpath="{.secrets[0].name}") -o jsonpath="{.data.token}" | base64 --decode

kubectl -n kubernetes-dashboard edit svc kubernetes-dashboard
{
NodePort
}

#create a token
kubectl -n kubernetes-dashboard create token admin-user
~~~

----------------------------------------------------------------
on browser login
11. https://hostname:/#/login
**
