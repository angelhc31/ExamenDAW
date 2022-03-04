# Memoria

## Resumen
En este documento recopilaré toda la documentcaión que he hecho a lo largo del examen, así como una conclusión y una opinión personal sobre el examen. 

## Motivaciones
Me he presentado a este examen para subir nota, porque mi primer trimestre fue un desaste, sinceramente no estaba orgulloso de mi rendimiento y queria enmendar mis errores en la medida de lo posible.


# Contenido
## Ejercicio 2

### Paso 1
Primero he establecido coneción con la máquina ```ssh 192.168.0.148``` después he comprobado si se habia establecido correctamente ```ifconfig```.

### Paso 2
Después he accedido al escritorio ```cd Escritorio``` y he creado el archivo *angelHesse.txt* ```cat > angelHesse.txt``` donde he escrito lo que se pedía.

Y por último he comprobado que se había creado correctamente ```ls``` ```nano angelHesse.txt```.

## Ejercicio 3

### Paso 1
Primero he establecido coneción con la máquina ```ssh 192.168.0.148``` después he comprobado si se habia establecido correctamente ```ifconfig```.

### Paso 2
Después he accedido al escritorio ```cd Escritorio``` y he creado la carpeta *angelHesse* ```mkdir angelHesse```.

### Paso 3
Y por último he comprobado que se había creado correctamente ```ls```, después he accedido a la carpeta ```cd angelHesse``` y he descargado la imagen ```wget https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/arro-2021-rai-racesuit-fullbody-helmet-0343-1613996103.jpg``` y he comprobado que se hubiera descargado ```ls```.

## Ejercicio 4

### Paso 1
Primero he creado la estuctura del directorio:
```sudo mkdir -p /var/www/ejercicio4.daw/ej4```

### Paso 2
Después le he dado los permisos necesarios:
```sudo chown -R $USER:$USER /var/www/ejercicio4.daw/ej4```
```sudo chmod -R 755 /var/www```

### Paso 3
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

### Paso 4
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

### Paso 5
Habilitamos los cambios realizados
```
sudo a2ensite example.com.conf
sudo a2dissite 000-default.conf
```

Y reiniciamos apache para aplicarlos ```sudo systemctl restart apache2```

### Paso 6
Configurar los hosts
```sudo nano /etc/hosts```

Y añadimos una linea donde ```111.111.111.111 ejercicio4.daw```

Y ya puedes ir al navegador y abrir tu virtual host.

## Conclusión
El examen en una primera instancia me ha parecido complicado, pero a medida que he ido indagando en los ejercicios me he dado cuenta de que no era tan complicado, si ibas con calma se podía ir contestando. Así que me ha parecido un examen capaz de demostrar los conocimientos del alumnado sin necesidad de estresarle.

Este curso pese a las adversidades me ha gustado. Espero que te vaya muy bien.