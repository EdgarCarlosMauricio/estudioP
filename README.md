# Tarea

- Con VPN activo entrar al servidor 172.30.0.27 ojala con bitvise por facilidad


Entorno
- Ya que se trabaja con apache tenemos 3 carpetas principalmente

1. /var/www/html
- En la primera tendremos las carpetas servidas que puedes encontrar en https://data.sis.co:334/
- Aqui usamos def application(environ, start_response): para ejecutar los archivos python basado en mod_wsgi sin ejecutar frameworks como flask, django.
- El problema es que al importar un archivo, este archivo lo debemos tener no en ese directorio sino en /usr/lib/python3/dist-packages

2. /usr/lib/python3/dist-packages
- Aqui colocamos los archivos de modulos a importar

3. /etc/apache2
- Este es un directorio de configuracion de apache para manejar el wsgi y el virtualhost


Tarea:

En este momento si entra con altair o postman o insomnia y envia una petcion POST  https://data.sis.co:334/proxy/proxy
y envia 
```
{
  usuarios(tipoFilter: "string", dataFilter: "string") {
    total
  }
}
```
- Podra ver en funcionamiento una query de graphql en su mas simple expresion
- Si ve su contenido podra ver que se mporta un archivo llamado proxy, este archivo se encentra alojado en /usr/lib/python3/dist-packages

- Ya que esto es solo un fragmento del archivo original con fines de enseñanza, debe tener en cuena que el archivo original lo puede encontrar en /var/www/html/proxy/bck/original


- Como puede ver esta conectado a la base de datos, Puede usar el esquema pqrs_new_sch_v1 para pruebas.
- La idea es que cree otras consultas y mutaciones.
