##**Direccionamiento básico IPv4**
Una dirección IP es un número, que sirve para identificar de forma única a un dispositivo dentro de la red.
La dirección IPv4 es un numero de 32 bits que identifica de forma exclusiva una interfaz de red en un sistema, tal como se explica en aplicación de las direcciones IP a las interfaces de la red. Una dirección IPv4 se escribe en dígitos decimales, y se divide en cuatro campos de 8 bits separados por puntos.

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277586416_724557605577367_6231186254466409603_n.jpg?_nc_cat=107&ccb=1-5&_nc_sid=730e14&_nc_ohc=G4GR6H13GYUAX-dKLgg&_nc_ht=scontent.fcue10-1.fna&oh=00_AT8slN72dyRbgjjvpOxuYNplVthrxpq48vDRhm7HY9WvSQ&oe=624CEC67)


El direccionamiento IP proporciona un mecanismo para la asignación de identificadores a cada dispositivo conectado a una red. 

###Formato de una dirección IP
Una dirección IP tiene el formato x.x.x.x, donde a la x se le denomina un octeto y debe ser un valor decimal entre 0 y 255. Los octetos se encuentran separados por puntos. Una dirección IPv4 debe contener tres puntos y cuatro octetos.
###Direcciones IP disponibles

######**Clase A**
En una red de clase A, los primeros ocho bits de la dirección, o el primer punto decimal, son la parte de la red, y la parte restante es la del host. Hay 128 redes de clase A posibles. 
Sin embargo, cualquier dirección que comience con «127.» se denomina dirección de loopback, es decir, que apunta al propio host.
Ejemplo para una dirección IP de clase A:
2.134.213.2

######**Clase B**

En una red de clase B, los primeros 16 bits de la dirección son la parte de la red. Todas las redes de clase B tienen el primer bit a 1 y el segundo bit a 0. Si dividimos la dirección en octetos, nos queda que las direcciones 128.0.0.0 a 191.255.0.0 corresponden a redes de clase B. Hay 16 384 redes de clase B posibles.
Ejemplo para una dirección IP de clase B:
135.58.24.17

######**Clase C**
En una red de clase C, los dos primeros bits están puestos a 1 y el tercero a 0. Eso hace que los primeros 24 bits de la dirección sean la parte de la red, y el resto, la del host. Las direcciones de red de clase C van desde 192.0.0.0 a 223.255.255.0. Hay más de 2 millones de redes de clase C posibles.
Ejemplo para una dirección IP de clase C:
192.168.178.1
 
######**Clase D**
Las direcciones de clase D se utilizan para aplicaciones de multidifusión. A diferencia de las clases anteriores, la Clase D no se utiliza para operaciones de red “comunes”. Las direcciones de clase D tienen los primeros tres bits a “1” y el cuarto bit establecido a “0”. Las direcciones de clase D son direcciones de red de 32 bits, lo que significa que todos los valores que podemos encontrar en el rango 224.0.0.0 - 239.255.255.255 se utilizan para identificar grupos de multidifusión de forma única. 
Ejemplo para una dirección IP de clase D:
227.21.6.173

######**Clase E**
Las redes de clase E se definen marcando los primeros cuatro bits de la dirección de red a 1, lo que genera las direcciones que van desde 240.0.0.0 a 255.255.255.255. A pesar de que esta clase está reservada, nunca se definió su uso, por lo que la mayoría de las implementaciones de red descartan estas direcciones como ilegales o indefinidas, a excepción, claro está, de 255.255.255.255, que se utiliza como una dirección de difusión (broadcast).
Ejemplo para una dirección IP de clase E:
243.164.89.28    

##Máscara de red
Es la combinación de bits para delimitar una red de computadoras. Se trata de 32 bits separados en 4 octetos (como las direcciones IP) su función es indicar a los dispositivos qué parte de la dirección IP corresponde a la red/subred y cual al host.
Mediante la máscara de red, un dispositivo sabrá si debe enviar un paquete dentro o fuera de la red en la que está conectado. La máscara de red se representa colocando en 1 los bits de red y en cero los bits de host. 

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277563068_724557755577352_1000881864191499481_n.jpg?_nc_cat=109&ccb=1-5&_nc_sid=730e14&_nc_ohc=2v__F1POIQ0AX-lk0dB&_nc_ht=scontent.fcue10-1.fna&oh=00_AT80qJa1n9W--tp5kuJ3k4hjynNnJihZC_Eyos_G2dPrlw&oe=624D8B9E)

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277571417_724557772244017_5749783295238405566_n.jpg?_nc_cat=104&ccb=1-5&_nc_sid=730e14&_nc_ohc=NztUNuwOOJ4AX-A0BlV&_nc_ht=scontent.fcue10-1.fna&oh=00_AT-oZXKKn2OCRM9ZK5bdzLh8TFjr8G_jI0KbROo4CzC7hA&oe=624CD11B)

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277778784_724557795577348_8754553997937313642_n.jpg?_nc_cat=102&ccb=1-5&_nc_sid=730e14&_nc_ohc=k9aBZLJGTYwAX8VHcZ-&_nc_ht=scontent.fcue10-1.fna&oh=00_AT9Yb6B79CiCSeZciNYGJ7NQtvv6a_DeSs2BLpQd7-I6cQ&oe=624C2309)

##Clases 
Conceptualmente una dirección IPv4 tiene dos partes el prefijo y el host definidos por la máscara, sin tener consideración de la clase (A, B, o C). 

##Classful 
Conceptualmente una dirección IPv4 tiene tres partes red, subred y host definidos por la máscara y las reglas de la Clase A, B, y C.

Es decir, una dirección Classful está definida por una clase específica en la parte de la red, mientras que una dirección Classless no es definida por una clase especifica de 8, 16 o 24 bits.

##Prefijo de subred
Es el número de bits que representa la dirección IP. La longitud del prefijo es el número de bits establecido en 1 en la máscara de subred. Está escrito en «notación de barra», que se observa mediante una barra diagonal (/) seguida del número de bits establecido en 1.

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277563155_724557638910697_1785199284200903763_n.jpg?_nc_cat=102&ccb=1-5&_nc_sid=730e14&_nc_ohc=UZXWITIq7FkAX8vR_sd&_nc_ht=scontent.fcue10-1.fna&oh=00_AT_Jd9tO9DswuyCaOeN0jQPL4mV3HecFaEpwdGWcN3YG9A&oe=624DF10F)

##Clasificacion de direciones IPV4

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277806236_724557792244015_3788331445985599611_n.jpg?_nc_cat=104&ccb=1-5&_nc_sid=730e14&_nc_ohc=_bgICZxN2dsAX9N3z2j&_nc_ht=scontent.fcue10-1.fna&oh=00_AT9TXsMYbYjEFq5LlUjGHMyzI-Kx3tSVzc1H4UsRdwjK-w&oe=624D096B)

##Ejemplo de plan de direccionamiento de una red
El plan de direcciones incluye determinar lo siguiente:

- Las necesidades de cada subred en cuanto al tamaño
- Cantidad de hosts por subred
- La forma en que se asignarán las direcciones de host
- Cuáles son los hosts que requerirán direcciones IPv4 estáticas y cuáles pueden utilizar DHCP
        

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277564953_724557745577353_3383803454560922221_n.jpg?_nc_cat=104&ccb=1-5&_nc_sid=730e14&_nc_ohc=ruaFQEI2YlsAX9PydPN&_nc_ht=scontent.fcue10-1.fna&oh=00_AT9H8Y1BZ2v5GbOHhLihLFMaEEojP3exci_ktutio91zRA&oe=624CD159)
##**Internet de las cosas**
El internet de las cosas básicamente se refiere a que elementos físicos de un hogar o una empresa tienen la capacidad de interconectarse a la red para intercambiar datos con otros dispositivos y cumplir tareas específicas propias de su diseño con el único fin de mejorar la calidad de vida de las personas.

###Aplicaciones 
![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277705807_724557642244030_9130101881771183172_n.jpg?_nc_cat=106&ccb=1-5&_nc_sid=730e14&_nc_ohc=EZ3n7rWhWucAX8DC5TK&_nc_ht=scontent.fcue10-1.fna&oh=00_AT9Wfoe9mWtxV1yFBc0UE_Y0ZBvdTDjQjtVZfo18H701EA&oe=624C1A5B)

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277806364_724557635577364_2665909587306572784_n.jpg?_nc_cat=100&ccb=1-5&_nc_sid=730e14&_nc_ohc=Uj7sv9707ioAX_J1Rtz&_nc_ht=scontent.fcue10-1.fna&oh=00_AT80KwTe6hkcsqNuY82LZX4bDYGyf9kaaI8w0zpHxJ-W9g&oe=624DE045)

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277782957_724557645577363_1422103579139843505_n.jpg?_nc_cat=106&ccb=1-5&_nc_sid=730e14&_nc_ohc=hx1Hwe_W2W0AX9NJjq_&_nc_ht=scontent.fcue10-1.fna&oh=00_AT-Iabct44yylD5rk9foz4_OU-f6CvOVZ1swnZIAQyK8kA&oe=624D6EDE)
###Características del internet de las cosas 

El internet de las cosas se caracteriza por su estructura de diseño y su conectividad con otros dispositivos, portando un tamaño pequeño, formado por un procesador y sensores con el único fin de interactuar con el medio que los rodea para recopilar datos importantes sobre las acciones y automatizar sus procesos.

- **Conectividad**: Para la comunicación es fundamental que cada dispositivo esté conectado a la red y a la vez con otros dispositivos, también, su comunicación puede ser mediante bluetooth.
- **Sensibilidad**: Este parámetro se enfoca en la sensibilidad del dispositivo para detectar diferentes aspectos como la temperatura, movimiento, sonidos, etc.
- **Interacción**: Es primordialmente para la intercomunicación entre el usuario, el dispositivo y el área física en el que se encuentran. 
- **Seguridad**: Este aspecto está ligado a proteger íntegramente los datos que se fluctúan por este medio. 

###Características de las comunicaciones

Características de una red de ordenadores: Hay una serie de características que nos permiten definir su funcionalidad. Si la red no marcha como nosotros queremos, habrá que fijarse en alguno de los siguientes 5 elementos.

- **Velocidad**

Es la velocidad a la que se transmiten los datos por segundo a través de la red. Suelen medirse con un test de velocidad. La rapidez de subida y descarga de datos será diferente según los estándares que utilicemos y también según el tipo de red o medio a través del que se transmiten los datos (inalámbrica, fibra óptica, cables de teléfono o coaxial).

- **Seguridad de la red**

Es uno de los aspectos más peligrosos que rodean a las redes inalámbricas, como ya hablamos en otra ocasión. La aparición de intrusos que nos quitan ancho de banda es una de las razones que convierte estas redes en bastante más vulnerables.

- **Confiabilidad**

Mide el grado de probabilidades que existe de que uno de los nodos de la red se averíe y por tanto se produzcan fallos. En parte dependerá de la topología de la red que hallamos instalado y del lugar que ocupa el componente averiado. Cuando uno de los componentes no funciona, puede afectar al funcionamiento de toda la red o por el contrario constituir un problema local.

- **Escalabilidad**

Una red no puede añadir nuevos componentes de forma continua y esperar que funcione a la misma velocidad. A medida que añadimos nuevos nodos y estos se hallan funcionando a la vez, la conexión a Internet se reduce, la velocidad de transmisión de datos en general es menor y hay más probabilidad de errores.

- **Disponibilidad**

Es la capacidad que posee una red para hallarse disponible y completamente activa cuando la necesitamos. La cantidad de tiempo posible en que podemos someter los nodos a unas condiciones de rendimiento necesarias en nuestra empresa. El objetivo es conseguir que la red se halle disponible según las necesidades de uso para las que se ha instalado.

###Tipos de comunicación

**M2M**:
Es un acrónimo que significa "Machine to Machine" o "Maquina a Maquina" Esta conectividad que se hace entre máquinas es autónoma; no hace falta la intervención de una persona para que la operación de transmisión de datos se haga con éxito.

**Características**:
- Funcionabilidad limitada.
- Bajo consumo
- Embebidos
- Ciclo de vida

**M2P**:
Es un acrónimo que significa “Machine to Person” o “Maquina a Persona” es que los nodos son tratados de igual manera. Redes descentralizadas y distribuidas en las cuales las aplicaciones puede comunicarse entre sí, intercambiando información sin el acoplo e un servidor central.

**Características**:
- Capacidades técnicas de análisis.
- Elementos de paneles de información.
- Habilidad de usar grandes cantidades de datos.

**P2P**:
Es un acrónimo que significa “Person to Person” o “Persona a Persona” es un tipo de conexión con una arquitectura destinada a la comunicación entre aplicaciones. Esto permite a las personas o a los ordenadores compartir información y archivos de uno a otro sin necesidad de intermediarios.

**Características**:
- Alcanza un fin superior.
- Administra y optimiza el ancho de banda.
- Compartir archivos de cualquier tipo.
- Enrutamientos anónimo.

![Visualización](https://scontent.fcue10-1.fna.fbcdn.net/v/t39.30808-6/277779624_724557662244028_8503474722113767126_n.jpg?_nc_cat=105&ccb=1-5&_nc_sid=730e14&_nc_ohc=4EyKs6hBgcYAX9Vq0vC&_nc_ht=scontent.fcue10-1.fna&oh=00_AT8vGG4A8IqC4VtR9alT6MjRMv3XFToYEQ9JK7Elhhi0Fw&oe=624C6090)























