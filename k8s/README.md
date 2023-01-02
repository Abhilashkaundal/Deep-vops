### Step 1-: install the kubernetes in ubuntu
.Go tho the file kubernetes_install

###Step2 -:
Create the kubernetes Dashboard for Admin user
~~~
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml
~~~
check the all pod is running or not
~~~
kubectl get pods -A
~~~
Apply the the command below
~~~
kubectl apply -f adminuser.yaml
 kubectl get secret -n kubernetes-dashboard $(kubectl get serviceaccount admin-user -n kubernetes-dashboard -o jsonpath="{.secrets[0].name}") -o    jsonpath="{.data.token}" | base64 --decode
~~~



