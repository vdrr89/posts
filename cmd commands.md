## Intérprete de Comandos 
# Terminal CMD

---
## Abrir el CMD
en la carpeta que se desee: 
escribir en la barra de navegación: 

`cmd + enter`


o presionar la tecla windows y escribir cmd

## Abrir el ejecutador de tareas
Teclas: Win + R

---
## MOVERSE ENTRE CAREPETAS

### Ver que carpetas/archivos hay dentro de donde estás
`c:/users/veronica>dir`

### Ir hacia carpeta
```
c:/users>
c:/users>cd veronica
c:/users/veronica>
```

### Ir hacia carpeta (si tiene espacios)
```
c:/users>
c:/users>cd "veronica yo"
c:/users/veronica yo>
```

### Volver a carpeta anterior
```
c:/users/veronica>..
c:/users 
```

### crear una carpeta
`c:/users/veronica>mkdir nuevaCarpeta`

### Eliminar archivo o carpeta
`c:/users/veronica>del hello.txt`

---
## Información del sistema

`SYSTEMINFO`


`ipconfig`


`ipconfig /all`



### Modificar IP
```
ipconfig /release (esto libera su IP actual)
ipconfig /renew (esto va a renovar/actualizar su IP)
```

### Encontrar la dirección física (Ethernet MAC) que corresponde a una determinada dirección IP
`arp -a`

### Tareas que se están ejecutando
Despliega la lista de tareas que se están ejecutando

`tasklist`

### Averiguar la IP de un sitio
`nslookup www.google.com`

### Averiguar la IP de un servidor de email
```
nslookup (Presionar Intro) 
yahoo.com
```

### Averiguar el ping hacia un sitio
`ping xxxx (x es la dirección IP)`

### Conocer la ruta que sigue un paquete antes de llegar al destino,
```
tracert xxxx (x es la dirección IP)
tracert www.google.com (www.google.com es la web que no conoce la dirección IP)
```
---
## Enviar o Recibir archivos vía Bluetooth
`fsquirt`