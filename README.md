# real_estate_database

A real estate management database scheme that consists of typical real estate objects.
1. Property
2. Units
3. Tenants

## Kubernetes setup notes
- This entire setup uses a Kubernetes cluster.
- A special namespace is used for the deployment which is called realestate.
  - __Note__: Remember to create the `realestate` namepace in the cluster.
- A secret is created inside this `realestate` namespace to hole the MySQL database root password.
  - __Note__: Remember to create the secret and the password.
  - The Kubernetes secret command used is the following:
    - `kubectl create secret generic mysql-root-password --from-literal='password=abcdefg' --namespace="realestate"`
- **Remember** to apply the persistent volume manifest to the realestate namespace using `kubectl apply -n realestate -f <filename>`.
