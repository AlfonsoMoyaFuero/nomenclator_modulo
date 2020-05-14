# nomenclator_modulo
Editor de Toponimia (Experimental)

Dentro de la asignatura de "Programación en Open Source en Geomática" del Máster Universitario en Geotecnologías Cartográficas en Ingeniería y Arquitectura, se encuadra la programación de este plugin.

Se trata de una herramienta para recoger la Toponimia de la Acadamia Valenciana de la Lengua (ALV). En ningún caso pretende sustituir las herramientas existentes, y es únicamente con propósitos académicos.
El objetivo del complemento es dotar a los encuestadores de una herramienta que facilite la delineación de la toponimia. Para ello, por medio de desplegables, se selecciona el tipo de topónimo a insertar, y una vez dibujado, se rellenan automáticamente los campos de:
•	Usuario
•	Clave
•	Elemento
•	Fecha
•	UUID

No hace falta cargar cartografía de partida. El complemento una vez se carga, hay que indicarle el directorio de trabajo, en caso de no existir los shapes de edición, los crea. 
Estos ficheros son:
•	edit_topo_punto.shp
•	edit_topo_linea.shp
•	edit_topo_poligono
Los campos que contienen estos shapes, idénticos en ambos casos son:
•	Id.- Identificador de número de elemento.
•	clave_top.- clave toponímica, identificador
•	elemento.- descripción de la clave toponímica
•	texto_nom.- Topónimo
•	topo_mayor.- Toponimia mayor o menor (S/N)
•	globalid.- identificador único uuid
•	usuario.- nombre de usuario
•	validado.- verificación por la AVL (S/N)
Los únicos campos que debe rellenar el usuario una vez se ha delineado el topónimo (punto, línea o pligono) son el campo “texto_norm” para incluir el texto del topónimo, y el campo “topo_mayor” son S/N para indicar si es Toponimia Mayor (escalas 1:150.000 o menor) o Toponimia Menor (escala mayor a 1:/150.000).

Errores detectados:
- Al cargar las capas por primera vez, a veces no se carga la capa "dic_toponimia.dbf" que se encuentra en el directorio "datos" del propio plugin. En ese caso es necesario cargarla a mano para que el plugin funcione. Se debe de cargar antes de invocar el botón "Abrir".
- Al detener la edición de alguna capa de toponimia (punto, linea o poligono) el QGIS hace los cambios correctamente pero se sale del programa. Sería necesario volver a cargar el QGIS y el plugin.
