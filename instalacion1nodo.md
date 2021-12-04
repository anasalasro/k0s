# Instalación de k0s en un nodo.
### 1.- Descarga de k0s
Con este comando, descargamos un script y se ejecuta.
``` ruby 
curl -sSLf https://get.k0s.sh | sh
```

![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/instalacion1.PNG)

Con este comando, descargamos un script y se ejecuta.

Podemos comprobar la versión instalada:

``` ruby 
k0s version
```
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/version.PNG)
### 2.- Lo instalamos en el cluster.

``` ruby 
k0s install controller --single
```

![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/instalacionCluster.PNG)

### 3.- Iniciamos el clúster

``` ruby 
k0s start
```
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/instalacionCluster.PNG)
### 4.Chequeamos el servicio

`k0s status`
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/instalacionCluster.PNG)

### 5.- k0s incluye kubectl

`k0s kubectl get nodes -o wide`
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/instalacionCluster.PNG)
 
### 6.-Comprobaciones
 
1.- Creamos un pod:

  `k0s kubectl run pod-nginx --image=nginx`
 ![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/instalacionCluster.PNG)
 
 NAME            READY   STATUS    RESTARTS   AGE
pod/pod-nginx-1   1/1     Running   0          19s

NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   5m32s

 
2.- Accedemos dentro del pod
  `k0s kubectl exec pod/pod-nginx -it -- /bin/bash`
  
3.- Creamos una pasarela: port-forward
   `k0s kubectl port-forward pod/pod-nginx 8081:80`
 ![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/instalacionCluster.PNG)
