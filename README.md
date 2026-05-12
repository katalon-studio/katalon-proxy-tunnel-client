<meta name="google-site-verification" content="phm3vFbTRK1zs-_i9n9-eerfJ0i_5sFwOuBVrfJOruQ" />

# Katalon Tunnel 

### Prerequisites                                                        
  - Helm 3.x                                                               
  - Kubernetes cluster                                                     
                                                                           
### 1. Add the Helm repository                                           
                                                                         
```sh                                                           
helm repo add katalon-tunnel https://raw.githubusercontent.com/katalon-studio/katalon-proxy-tunnel-client/refs/heads/release
helm repo update                                                         
```
 
### 2. Install the chart                                                     
```                                                                
helm install katalon-tunnel katalon/katalon-tunnel \
  --set tunnel.username="<your-email>" \
  --set tunnel.apiKey="<your-api-key>" \
  --set tunnel.accountId="<your-account-uuid>" \                           
  --set tunnel.organizationId=<your-org-id>
```                                                                      

### 3. Or install with a values file                                
                                                                         
Create a values.yaml:                                           
```
tunnel:
  username: "<your-email>"
  apiKey: "<your-api-key>"                                               
  accountId: "<your-account-uuid>"
  organizationId: <your-org-id>                                          
  group: "<optional-tunnel-group>"                              
```                                                                          

Then install:
```                                                                           
  helm install -n <namespace> katalon-tunnel katalon/katalon-tunnel -f values.yaml 
```                                                                           
Upgrade
```                                                                           
  helm upgrade -n <namespace> katalon-tunnel katalon/katalon-tunnel -f values.yaml 
```
Uninstall
```
  helm uninstall -n <namespace> katalon-tunnel
```

