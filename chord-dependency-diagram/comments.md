# Chord Dependency Diagram


## ¿ Qué hace ? 
Muestra las dependencias de las clases que importan otras clases.


## ¿ Qué tecnologías utiliza ?
- CSS
- D3.js
- JavaScript
- HTML


## ¿ Cómo funciona el código ?
1. En el archivo '7658b4d9887cc334@314.js':
    - Se importa d3.
    - Se crea una variable llamada _height_ y su valor hará referencia a la variable _width_.
    - Se crea _width_ y se le asigna el valor de 954.
    - Se crea la variable _innerradius_ su valor será el mínimo entre _width_ y _height_ multiplicado por 0.5 y restando entre 90.
    - Se define _outerradius_ y se le asigna el retorno de la suma de _innerradious_ entre diez.
    - En la variable _color_ se guarda la función que calcula el color de las "cuerdas", primero el método interpolateRainbow() crea un rango de colores basandose en la cantidad de elementos haya, segundo se llama a quantize() que define en los canales rgb las cantidades y por ultimo se asigna cada color a cada elemento segun el orden que ocupe dentro del arreglo de los datos con scaleOrdinal().
    - Se crea _ribbon_ que es como se conectan las clases, se le da forma.
    - Se define _arc_ quien crea el círculo exterior donde posteriormente se ubicarán los nombres.
    - Se crean las cuerdas, organizandolas en subgrupos (de mayor a menor) y cuidando que no se sobrepongan unas con otras.
    - Se crea matrix que recibe a _data_ y _names_ como parametros y crea un arreglo _index_ poblado de nombres e indices. Por cada indice crea un arreglo poblado de 0 y la longitud de este nuevo arreglo depende de cuantos indices hayan.
        Por ultimo recorre _data_ y enlaza _source_, _target_ y _value_ a matrix.
    - _Names_ es un arreglo de hecho de _data_ que contiene organizados de manera ascendiente cada dato con su respectivo _target_ y _source_.

    - Se crea el _chart_ y se le añade un elemento svg con atributo viewBox.
    - Define las cuerdas basandose en _matrix_.
    - Crea un grupo para cada cuerda y une a cada cuerda con su respectivo grupo.
    - A cada grupo le añade un _path_ que viene asignado a un _color_ y un _arc_, se le da un nombre que proviene de _names_, un grado de rotacion y cuando tiene que trasladarse. Asimismo un titulo y el total de clases de las que depende y las clases que dependen de esta clase.
    - Finalmente, se añaden todos los grupos al elemento svg con su respectivo color y su "lazo" (_ribbon_).

2. 'index.js' exporta toda la clase default dentro del archivo '7658b4d9887cc334@314.js'.

3. En el archivo html se vincula 'index.js' y 'runtime.js', se crea _runtime_ y _main_ que pasa a _runtime_ el archivo 'index.js' y una hoja de estilos llamada 'inspector.css'
