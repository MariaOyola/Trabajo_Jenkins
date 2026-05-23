# Ahora se van a enviar notificaciones (Email)

1. Se deben cumplir con laas siguientes reglas 
( en mi caso se va a llamar FaceLit)
![alt text](image.png)

--------------------------
1.2 Ya tenemos la  plugin en Jenkins (esto para poder enviar Gmail)

![alt text](image-1.png)
---------------------------
1.3 Configura SMTP en Jenkins

![alt text](image-2.png)

- se mira para ver si llego a mi cuenta 
![alt text](image-3.png)

-------------------------------
# Ahora se van a enviar notificaciones (Discord)

- Intalamos el Discord Notifier

![alt text](image-4.png)

- se crea canal en Discord 
![alt text](image-5.png)

- se configura 
![alt text](image-6.png)

- Seejecuta ( me salio error)
![alt text](image-7.png)
![alt text](image-8.png)

- Listo ya ejecuta correctamente 
![alt text](image-9.png)
![alt text](image-10.png)

- Tambien se envian a mi email 
![alt text](image-11.png)
![alt text](image-12.png)

------------------------------------------
# Ahora se van a enviar notificaciones (Microsoft Teams)

- Intalamos el Office 365 Connector / Power Automate workflows para usar Jenkis en microsoft teams. 

![alt text](image-13.png)

## NOTICIA DE ULTIMA HORA 

Durante la implementación de las notificaciones automáticas en Jenkins, inicialmente intenté integrar Microsoft Teams como plataforma de mensajería para recibir alertas de los builds del pipeline CI/CD.

El objetivo era que Jenkins enviara notificaciones automáticas cuando el proyecto compilara correctamente, fallara o quedara en estado inestable.

Sin embargo, durante el proceso surgieron varias limitaciones técnicas relacionadas con Microsoft Teams. La principal dificultad fue que la versión utilizada correspondía a Microsoft Teams Personal o Communities, la cual no incluye soporte completo para funcionalidades empresariales como Incoming Webhooks, Connectors o Workflows avanzados.

Además, muchas de las integraciones de Jenkins con Teams actualmente requieren cuentas Microsoft 365 empresariales o institucionales, ya que Microsoft ha migrado parte de sus sistemas de integración hacia Power Automate y servicios corporativos.

Debido a estas restricciones, la generación del webhook necesario para Jenkins no pudo realizarse correctamente en el entorno disponible.

Por esta razón, se decidió implementar Telegram como alternativa de notificaciones automáticas, ya que ofrece una integración mucho más sencilla mediante bots y APIs HTTP. Con Telegram fue posible configurar:

* Envío automático de mensajes.
* Notificaciones de éxito, error e inestabilidad.
* Integración directa con Jenkins usando curl.
* Comunicación en tiempo real al dispositivo móvil.

Finalmente, el sistema quedó funcionando correctamente utilizando Jenkins + Telegram + Discord + correo electrónico como mecanismos de monitoreo y notificación del pipeline CI/CD.


----------------

# Ahora se van a enviar notificaciones (Microsoft Teams)

![alt text](image-14.png)

- se crea user y nombre para telegram

8890540061:AAFFBM8o4ClBZtGacqdcALJJreNdXneiOj4 
![alt text](image-15.png)
![alt text](image-17.png)

- miramos el el Chat ID
![alt text](image-18.png)

- Ahora vamos a probar el envío
![alt text](image-19.png)

- Si esto funciona, telegram me emvia un mensaje 
![alt text](image-20.png)

- despues de eso ya puedo configurar mi Jenkinsfile.

- Me salio error por que lo configure mal 
![alt text](image-21.png)

- listo ya se corrigio 
![alt text](image-22.png)

- ya tengo el mensaje de respuesta 
![alt text](image-23.png)

----------------------------------

# Sección 8 — Webhooks de GitHub con Jenkins

1.  Consigue la URL pública de Jenkins
El problema con Jenkins en Docker es que corre en localhost:8080 — GitHub no puede llegar a esa URL porque es local. Necesitamos exponerla al internet.
Usamos ngrok (gratis y rápido):

- se Configura el Webhook en GitHub
![alt text](image-24.png)

- en  Api → Configurar → Triggers → marca:
![alt text](image-25.png)

-  Bamos a realizar un commit 
![alt text](image-26.png)

- sin necesidad de ejecutar ya me muestra el error 
![alt text](image-27.png)

- aqui se muestra como se ejecuta el jenkis automatico con el Webhooks 

<video width="600" controls>
    <source src="./jenkis.mp4" type="video/mp4">
</video>