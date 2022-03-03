# Hierarchical Edge Bundling 

## ¿ Qué hace ? 
Realiciona de manera herarquica las clases que importan otras clases.
De color rojo las clases que importa y de color azul las clases que importan a esa clase.


## ¿ Qué tecnologías utiliza ?
- CSS
- D3.js
- JavaScript
- HTML


## ¿ Cómo funciona el código ?
1. En el archivo '22ac214fe83d7053@426.js' se exporta por defecto la funcion llamada *define()*
donde se indica que la constante _main_ guarda el archivo de d3 y la constante _fileAttachments_
será para crear un nuevo objeto json llamado 'flare.json' donde se van a guardar los datos del archivo '9b6806e3dd9c4c2c26760ba784437138c78b43a9a8e58a0bbafe5833026e3265637c9c7810224d66b79ba907b4d0be731c1a81ad043e10376aec3c18a49f3d84' asignadole un nombre a cada elemento y añadiendolo a _main_.

2. Una función da el titulo a la pagina con mardown.

3. Con la ayuda de _main_ se definen las variables _chart_, _tree_, _bilink_, _d3_, _data_, _width_, _id_, _colornone_,_line_, _colorin_, _colorout_.

4. La funcion *hierarchy()*  en este caso no habla del metodo de d3 hierarchy() sino uno creado en el mismo codigo que
recibe *data()* (es una funcion que toma el archivo donde se guardan los datos a trabajar convertido en json) y lo retorna organizado de manera ascendente basandose en su altura o en orden alfabetico segun el nombre de los elementos dentro del json, luego _data_ se pasa como argumento a *hierarchy()* para crear un arreglo con los valores similares a data para crearles un nombre y obtener el indice de donde se encuentra para nombrarlo nodo padre y crearle nodos hijos que serian las clases que importa y le importan. De esta ultima tarea se encarga la funcion *bilink()* el resultado de todo esto se denomina _tree_ y se guarda en _root_.

5. Se crea un elemento svg con el atributo viewbox.

6. Se crearan tantas etiquetas g como se necesiten para cada nombre de dato se asignan algunos atributos como el tipo de fuente, la rotacion y el ancho del texto. Se añaden las funciones  *overed()* *outed()* para cuando se coloque y se retire (respectivamente) el mouse sobre una etiqueta g. *overed()* hará que el resto de lineas que conectan a otras clases y no a esa especificamente se ven de color más claro mientras que a esa especificamente la hará más oscura, si importa a otras clases la conexión se hará de color rojo (_colorin_), si es importada por otras clases será azul (_colorout_). *outed()* usa los mismo datos que *overed()* pero los llenará con null para que ninguna información se revele al no señalar ninguna etiqueta g.

7. En el archivo html se importan runtime e index siendo este ultimo el que exporta todo el contenido de '22ac214fe83d7053@426.js'




