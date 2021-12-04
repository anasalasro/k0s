# Comprobaciones
 
1.- Creamos un pod:

``` ruby
k0s kubectl run pod-nginx-1 --image=nginx
```
 ![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/creamospod.PNG)
 
2.- Accedemos dentro del pod
  ``` ruby
  k0s kubectl exec pod/pod-nginx-1 -it -- /bin/bash
  ```
![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/accesopod.PNG)  
3.- Creamos una pasarela: port-forward y comprobamos la web desde otra terminal con el curl
   ``` ruby
   k0s kubectl port-forward pod/pod-nginx-1 8081:80
   curl localhost:8081
   ```
 ![k0s](https://github.com/anasalasro/k0s/blob/main/imagenes/comprobamosweb.PNG)
