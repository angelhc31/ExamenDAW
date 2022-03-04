# Ejercicio 4

## Paso 1
Primero he creado la estuctura del directorio:
```sudo mkdir -p /var/www/ejercicio4.daw/ej4```

## Paso 2
Después le he dado los permisos necesarios:
```sudo chown -R $USER:$USER /var/www/ejercicio4.daw/ej4```
```sudo chmod -R 755 /var/www```

## Paso 3
Ahora he creado la página que mostrará nuestro host:
```nano /var/www/ejercicio4.daw/ej4/index.html```

Allí escribo
```
<html>
  <head>
    <title>Ejercicio4</title>
  </head>
  <body>
    <h1>Angel Hesse Caracena</h1>
  </body>
</html>
```

## Paso 4
Crear el archivo para el virtual host, primero copio el archivo para el domino:

```sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/ejercicio4.daw.conf```

Ahora lo edito

```sudo nano /etc/apache2/sites-available/ejercicio4.daw.conf```

Y modifico la información de forma que:

```
ServerAdmin angelhessecaracena@gmail.com
ServerName ejercicio4.daw
ServerAlias www.ejercicio4.daw
DocumentRoot /var/www/example.com/public_html
```

## Paso 5
Habilitamos los cambios realizados
```
sudo a2ensite example.com.conf
sudo a2dissite 000-default.conf
```

Y reiniciamos apache para aplicarlos ```sudo systemctl restart apache2```

## Paso 6
Configurar los hosts
```sudo nano /etc/hosts```

Y añadimos una linea donde ```111.111.111.111 ejercicio4.daw```

Y ya puedes ir al navegador y abrir tu virtual host.