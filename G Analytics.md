Analizar Google Analytics
```
ga.getAll()[0].get('trackingId')
```

---

En la consola de Chrome:
```
function tagname()
{
  document.getElementsByTagName("input");
}
```

---

Para obtener un listado desde el sitio, en la consola de Chrome: 
```
var arr=document.getElementByTagName("input");
```

Para contar los elementos que contiene la lista: 
```
arr.length
```
iconos en ig
var icon = document.getElementsByTagName("svg")

nombre del icono de ig
icon[0].ariaLabel

post en ig
var post = document.getElementsByClassName("_aabd")

ver nombres de todos los íconos
for (let i = 0; i < icon.length; i++) {
  console.log(icon[i].ariaLabel);
}

---

var comment1 = document.getElementsByClassName("_aade")
comment1.length
comment1[0]
for (let i = 0; i < 10; i++){
    console.table(comment1[i].firstChild.nodeValue)
}

