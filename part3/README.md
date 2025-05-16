1. Deleting the previous database
<pre> <code>kubectl delete deploy products-db</code> </pre>
<pre> <code>kubectl delete svc products-db</code> </pre>

2. Deploy the changes
<pre> <code>kubectl apply -f part3/products-api -f part3/products-db -f part3/stock-api -f part3/web</code> </pre>

3. Restart the pods
<pre> <code>kubectl rollout restart deploy/products-api deploy/stock-api</code> </pre>
