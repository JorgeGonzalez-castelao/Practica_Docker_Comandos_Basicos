
    
    PRACTICA DOCKER -> COMANDOS BASICOS
    
    1. Descarga la imagen 'ubuntu y comprueba que está en tu equipo.

        -> *docker run ubuntu* : Si no poseemos la imagen de manera local, la buscara de   manera inmediata en la red para así descargarla.

        -> *docker image ls -a* : Permite visualizar las imagenes decargadas.
    
    2. Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre.
    
        -> *docker run ubuntu*  : para inicializar ubuntu.
    
        -> *docker ps -a* : Gracias a esto miramos todos los contenederos, nuestro objetivo será el primero ya que se organizan por fecha de creacion y ahí podremos ver su nombre.

    3. Crea un contenedor con el nombre 'dam_ubu1'. ¿Como puedes acceder a él?

        -> *docker run -it --name  dam_ubu1 ubuntu* : Este comando nos da la capacidad de dotar a nuestro contenedor el nombre dam_ubu1 y con el prefijo it se iniciaria.
    
    4. Comprueba que ip tiene y si puedes hacer un ping a google.com.
    
        -> Comprobamos la ip gracias a descargar los *nettools* en el contenedor

        -> *apt update* : actualizamos los paquetes

        -> *apt install net-tools* : descargamos lo indicado

        -> *ifconfig* : para ver la deseada ip
    
        -> Para conectar con Google tenemos que instalar su paquete 

        -> *apt install  iputils-ping* : Descarga el paquete de google.

        -> *ping google.com* : para realizar el pingeo le daremos al comando Ctrl + C.
    
    5. Crea un contenedor con el nombre 'dam_ubu2'. ¿Puedes hacer ping entre los contenedores?
    
        -> Se realiza lo mismo que en el apartado 3, pero con el ligero cambio de cambiar el nombre a *'dam_ubu2'*.

        -> Se puede hacer ping entre contenedores gracias a saber la **ip** que tengamos en el contenedor deseado.
    
    6. Sal del terminal, ¿que ocurrió con el contenedor?
    
        -> *docker ps*: Pese a que parezca que se cierra en primera instancia, la realidad es que sigue encendido, esto se sabe gracias al comando docker ps ya que visualiza los contenedores activos.

    7. ¿Cuanta memoria en el disco duro ocupaste?
    
        -> *docker system df -v* : Este comando visualiza todo , para que sea más exacto se le añade -v, así obtenemos la respuesta deseada.

    8.¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?.

        -> *docker stats* : Vemos los contenedores activos y nos indica su carga de RAM , su pesaje varia entre un minimo de 5 Mb, hasta un máximo de 15 Gb.

        -> *docker stats -a* : Con la variable -a, tambien vemos los contenedores inactivos.
