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

