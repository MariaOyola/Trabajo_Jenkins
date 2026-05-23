# ¿ Como funciona la estructura de proyecto ? 

## Cómo funciona el flujo REAL que debes simular

La lógica es esta:

```text
feature/* → Jenkins valida → si funciona → merge a develop

develop → Jenkins valida → si funciona → merge a main
```

| Rama         | Uso                                       |
|---------------|-------------------------------------------|
| `main`        | Producción                                |
| `develop`     | Integración                               |
| `feature/*`   | Nuevas funciones o corrección de errores  |

-----------------------------

1.1 Mirara si funciona Jenkis en mi Doker 
![alt text](image-2.png)
![alt text](image-3.png)

--------------------------

1.2 Esta el la estructura de ramas que voy a usar para realizar el repo

![alt text](image-4.png)

Link : https://github.com/MariaOyola/Eco_Api
--------------------------------------

1.4  Cremos el Jenkinsfile en mi repo 
![alt text](image-5.png)
![alt text](image-6.png)

esto se encuentra en la rama  feature/login-ui, y la idea es mergearla hacia la develop y despues llevarla a produccion para que Jenkis la pueda vallidar  

![alt text](image-7.png)

--------------------------
1.5  configuramos el Jenkis Pipeline para que Jenkins detecte todas las ramas automáticamente:

![alt text](image-8.png)
![alt text](image-9.png)

1.6 Lo ejeutamos ( ESTO PARA VER SI FUNCIONA)
![alt text](image-10.png) 

: )   FUNCIONO 
---------------------------------------
1.6  Ahora vamos a crear un error con la rama feature/auth-error, y para eso cree un error en la capa Controller en la clase AnimalController. 

![alt text](image-11.png)

- subimos el error 

![alt text](image-12.png)

y merger a la develop ( lo hice por comandos)

![alt text](image-14.png)

- y despues en la main
![alt text](image-15.png)

- se borro un (;)
![alt text](image-16.png)
![alt text](image-17.png)

- Ahora vamos a corregir ese error y despues subirlo, y para eso vamos a crear otra rama para arreglarlo

![alt text](image-18.png)

- ya se arreglo desde la main
![alt text](image-19.png)

-------------------------------

1.7 Generamos un  conflicto en la merge 

Conflicto de merge → BUILD UNSTABLE
- en la rama  feature/login-ui genere un error
![alt text](image-20.png)

- y se sube
![alt text](image-21.png)

-  y secrea un error en la develop
![alt text](image-22.png)

- y se mergea

![alt text](image-23.png)

![alt text](image-24.png)
- como no tengo la inteccion  UNSTABLE, entonces normalmente me salee como correcto  
![alt text](image-25.png)

----------------------
1.8 Se vuelve a arreglar el repo 
![alt text](image-26.png)

ahora hacemos los merge hacia develop

![alt text](image-27.png)

- y listo ya todo  esta bien
![alt text](image-28.png)

