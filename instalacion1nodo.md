# Instalación de k0s en un nodo.
### 1.- Descarga de k0s
Con este comando, descargamos un script y se ejecuta.
``` ruby 
curl -sSLf https://get.k0s.sh | sh
```
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/instalacion1.PNG)

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

### 3.- Iniciamos el clúster y comprobamos el status

``` ruby 
k0s start
k0s status
```
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/status.PNG)

### 4.- k0s incluye kubectl

``` ruby
k0s kubectl get nodes -o wide
```
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/informacion.PNG)
 
### 5.-Comprobaciones
 
1.- Creamos un pod:

``` ruby
k0s kubectl run pod-nginx-1 --image=nginx
```
 ![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/creamospod.PNG)
 
2.- Accedemos dentro del pod
  ``` ruby
  k0s kubectl exec pod/pod-nginx -it -- /bin/bash
  ```
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/accesopod.PNG)  
3.- Creamos una pasarela: port-forward y comprobamos la web desde otra terminal con el curl
   ``` ruby
   k0s kubectl port-forward pod/pod-nginx 8081:80
   curl localhost:8081
   ```
 ![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/comprobamosweb.PNG)
