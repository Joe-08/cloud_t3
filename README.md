# Cassandra

## Esencial

- NoSQL Distributed Database
- Cada instancia de Cassandra se denomina nodo y este contiene toda una base de datos Cassandra.
- Cada nodo puede manejar unas 2 a 4 TB de datos y muchos miles de operaciones por segundo por core. La cantidad de operaciones depende los recursos asignados al nodo.
- Cassandra es una base de datos distribuida, aunque se pueda correr en un solo nodo. 
- Es un sistema sin líder y *peer-to-peer*, lo que significa que cada nodo puede hacer lo mismo que cualquiera.
- Los nodos se comunican a través de un protocolo llamado gossip que utilizan para trasladar información entre nodos.
- Los nodos están organizados en grupos llamados *data centers*, se puede representar como todos los nodos conectados por un aro.

## Características

- **Base de datos de nivel petabyte.** No solo Cassandra puede almacenar todos esos datos, sino que también mantiene rendimiento y escalado, algo por lo que Cassandra sobresale.
- **Base de datos siempre encendida.** Debido a que está construida para mantener un 100% tiempo de actividad, aún cuando haya casos de fallas de nodos. Hace esto gracias a su naturaleza distribuida, replicación automática y topología sin líder.
- **Distribución geográfica.** Es una manera de crear una base de datos global poniendo *data centers* donde sea necesario alrededor del mundo y Cassandra manejará la comunicación y replicación de los datos automáticamente.
- **Rendimiento.** A modo general, su escritura en la base de datos a una velocidad entre microsegundos a milisegundos, y su lectura es de milisegundos. Esto se mantiene si la base de datos tiene tres nodos o más ya que Cassandra escala linealmente e indefinidamente por lo que si se quiere mejor rendimiento basta aumentar la cantidad de nodos.
- **Independiente del proveedor.** Se puede instalar en cualquier dispositivo sin preocuparse por dependencias de un proveedor.

## Particionamiento

Una de las preguntas que se pueden venir a la mente es cómo sabe la base de datos dónde poner los datos o cómo conseguirlos después si se quieren leer. Esto se logra gracias a que los datos se dividen en particiones.

En este ejemplo podemos observar que la tabla tiene tres columnas y ***country*** es nuestra llave de partición, lo que significa que se dividen las filas basadas en el valor de nuestra llave de partición y serán almacenadas en un nodo y los datos se distribuirán automaticamente alrededor de los nodos en el *cluster*.

[!Tabla de particion](imagen_2021-11-15_171116.png)

Los datos particionados se verían de esta forma:

[!Particion]()

El usuario es el que elige la llave de partición.

## Replicación

