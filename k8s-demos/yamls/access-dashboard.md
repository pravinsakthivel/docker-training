### Deploy and Access Kubernetes Dashboard

1.  Create a new ServiceAccount named user1

    ```
    $ kubectl apply -f admin-user.yaml
    ```

2.  Create a new user-role with "Cluster-Admin" role
    And assign it to "user1"

    ```
    $ kubectl apply -f role-binding.yml
    ```

3.  List all serviceaccounts from namespace "kube-system"
    
    ```
    $ kubectl get serviceaccounts -n kube-system
    ```

4.  Get ALL Secrets (names only) from namespace kube-system
    
    ```
    $ kubectl get secrets -n kube-system
    ```

5.  From list of secrets copy the name of last secret
    the name must begin with "user1-token"

6.  Get the actual TOKEN using name from previous step

    ```
    $ kubectl describe secrets {PASTE} -n kube-system
    ```
7.  Copy the token text into a new notepad window for later use.
    remove "token:  " from the beginning of text.

8.  Deploying K8S Dashboard (Services, PODS, Replicas)
    
    ```
    $ kubectl apply -f kubernetes-dashboard.yaml
    ```

9.  Start the Proxy Server (Dashboard)
    
    ```
    $ kubectl proxy 
    ```
    
10. Open Web browser and Visit URL:
     http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/

11. On FIRST startup, dashboard ask you to authenticate
    Copy the TOKEN from notepad (You copied from secret)
    PASTE in "TOKEN" field to Authenticate
    Press SIGN IN button

    Once AUTHENTICATED, next time onwards you just need
    Step 9 & Step 10 to launch dashboard