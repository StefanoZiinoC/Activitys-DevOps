Utilizo AWS para hosatear mis servidores por que es facilmente escalable, tiene base en todas las regiones y se ocupan de una gran parte de la seguridad. ademas me notifica automaticamente si algo ocurre y podemos generar notificaciones personalizadas con las metricas que nos brinda, facilmente podemos generar estadisticas y controlar el flujo de usuarios.

El usuario se puede conectar a nuestra subnet publica a travez de **Route 53**, es un servicio web de DNS que nos permite modificar nuestra ip con un dominio mas comodo de escribir (www.example.com), ademas de encargarse de la seguirdad y control de flujo de usuarios. Conecta las solicitudes con las aplicaciones que dispongamos en nuestras subnets

**Internet Gateway** es un componente de la VPC de escalado horizontal, redundante y de alta disponibilidad que permite la comunicación entre su VPC e internet 

**Load balancer** para repartir el flujo de usuarios entre las dos subnets, si alguno sufre algun accidente inseperado nos queda una subnet clonada, con DBs actualizadas al dia gracias a la **repliaction**.

Montamos 2 **EC2**, una para el frontend en **ReactJS** y la otra el backend en **Django**, y otras 2 para sus respectivos clones en otra ubicacion geografica por si algo ocurre.

el usuario interacciona con el backend de acuerdo a lo permitido y responde a travez del NAT gateway ya que los backends estan en la private subnet.

El backend conecta con las bases de datos en la misma private subnet, le podemos establecer permisos para modificar, guardar, borrar segun necesitemos. Tenemos una DB relacional  (RDS) y otra DB no relacional (DynamoDB). solo se accede hasta donde nosotros permitamos.

Ademas el backend consume 2 microservicios externos a travez del NAT Gateway ya que estos no perteneces a la VPC, podrian ser API de terceros por ejemplo.
