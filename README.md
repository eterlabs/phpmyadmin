![alt text](https://www.eterlabs.com/wp-content/uploads/2021/02/cropped-eterlabs-2.png)

Este repositorio fue generado para aprender a montar PhpMyAdmin usando las imágenes de Docker de Eterlabs, estas imágenes las creamos basadas en los requerimientos internos para desarrollo por lo tanto no es recomendable usarlas para ambientes productivos.


Si te gusta este repositorio y te gustaría poder obtener más herramientas de desarrollo, síguenos en nuestras redes sociales.


* [Facebook](https://www.facebook.com/eterlabsmx)
* [Instagram](https://www.instagram.com/eterlabsmx/)
* [LinkedIn](https://www.linkedin.com/company/eterlabs)


Si te gustaría sugerir contenido o módulos envíanos un correo a contacto@eterlabs.com

Para usar este repositorio sigue los siguientes pasos:

#### Requerimiento Previos

* Tener instalado Docker.

#### Montado del proyecto

1.- Clonar el proyecto
```
git clone https://github.com/eterlabs/phpmyadmin.git
```

2.- Moverse al proyecto
```
cd magento-modules
```

3.- Iniciar el proyecto
```
docker-compose up -d
```

4.- Configura el ambiente creando una copia del archivo de configuración
```
cp phpmyadmin/config.sample.inc.bk.php phpmyadmin/config.inc.php
```

5.- Conecta con tu base de datos modificando la siguiente parte de código
```
/* Authentication type */
$cfg['Servers'][$i]['auth_type'] = 'cookie';
/* Server parameters */
$cfg['Servers'][$i]['host'] = 'host.docker.local';
$cfg['Servers'][$i]['compress'] = false;
$cfg['Servers'][$i]['AllowNoPassword'] = false;
```

En el cual **host.docker.local** es el host bridge de Docker para conectar con una base de datos local el cual cambia de acuerdo al sistema operativo

Para mac usar:
```
host.docker.internal
```
Para ubuntu usar:
```
host.docker.local
```
Nota: también se puede generar un enlace a cualquier otro host.

6.- Probar el ambiente entrando a la url:
```
http://localhost:8090/
```