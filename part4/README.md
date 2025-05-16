1. Deploy the changes
   
<pre> <code>kubectl apply -f part4/ingress-controller -f part4/products-db -f part4/products-api -f part4/stock-api -f part4/web</code> </pre>

2. Update the host file
   
Run Powershell as an Administrator and `cd /path/to/your/repository/`
<pre> <code>.\scripts\add-to-hosts.ps1 widgetario.local 127.0.0.1</code> </pre>
<pre> <code>.\scripts\add-to-hosts.ps1 api.widgetario.local 127.0.0.1</code> </pre>

3. Check the app at `http://widgetario.local` and the API at `http://api.widgetario.local/products`
