# Practicando Markdown y Git


Git es una herramienta que nos permite rastrear cambios en diferentes archivos que tengamos en nuestros proyectos. Por lo que no solo mantiene el historial de cambios, sino que tambien facilita el trabajo en equipo.

Aun cuando se trabaja solo, el uso de un control de versiones nos permite especificar cada cambio que se realiza, compararlo contra otro cambios realizados anteriormente, buscar cambios previos, trabajar distintas cosas al mismo tiempo utilizando *branches* y luego compararlo contra el codigo principal y sus diferencias. 

Podemos pensar en un repositorio de versiones como un **arbol**, donde todo empieza en el _tronco_, y luego se pueden ir creando "ramas", que estaran basadas en el tronco pero que tendran su propia identidad y sus cambios especificos, para luego volver a regresar al tronco si asi se desea, o crear mas ramas a partir de otra rama.

De la forma en que trabaja _git_, es que crea una imagen o snapshot no solo del archivo que esta cambiando sino tambien del padre o rama a donde pertenece, donde al final un snapshot puede llegar a tener distintos padres con distintos cambios en cada interaccion.

Estos snapshots son ***inmutables***, esto quiere decir que no podemos cambiar el pasado de un cambio, pero si podemos usarlo para generar un nuevo snapshot con los cambios necesarios, por lo que es importante tenerlo en cuenta al momento de realizar cambios y mandarlos al snapshot.

Los snapshots seran identificados por el hash del mismo, por lo que las referencias deben ser consultadas en base al hash, lo que nos permite una facil identificacion de cada uno al momento de consultar historial o cambios en los mismos, y al ser inmutables sabemos que estos siempre seran los mismos.

Git tambien tiene ciertas ***referencias*** hacia snapshots especificos, se consideran *punteros* a commits. Las *referencias*, a diferencia de los snapshots, si son mutables por lo que una referencia puede apuntar a distintos commits, como por ejemplo "master" suele ser el ultimo commit en la rama principal (o tronco), pero tambien el nombre de un branch sera una referencia ya que esta siempre va a apuntar hacia el ultimo commit realizado.

Una de las maneras que git nos permite mantener mejor control en lo que deseamos hacer commit y crear un snapshot es el area de "staging", esta es un area donde podemos decidir que cambios queremos incluir ya que podemos estar trabajando en varios archivos al mismo tiempo pero no todos pueden estar listos o no todos son necesarios ser enviados para que nuestros cambios funcionen. El manejo de esta area pareciera doble trabajo, ya que no solo hicimos los cambios sino que ademas tenemos que agregarlos para ser considerados "listos" para el snapshot, pero en realidad esto nos permite evitar enviar cambios no deseados o tener una "vista previa" de lo que el snapshot va a incluir, por lo que puede considerarse una ayuda mas que una molestia.

Para poder confirmar el snapshot y enviarlo al servidor tenemos que hacerlo por medio de un push hacia el origen, ya que de lo contrario todos los cambios y snapshots existiran unicamente en nuestro repositorio local.

