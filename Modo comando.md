# Guardar y salir
Se pueden combinar varias letras
```
:w = write
:q = quit (sale del archivo)
:q! = sale (sale del archivo forzando)
```
# Buscar
```
/palabra
	Busca una palabra en el documento a partir de donde está el cursor 
	
?palabra
	Busca una palabra en el documento por detrás del cursor
	
		Enter = Para ir a la primera ocurrencia se pone enter
		n = Para ir a la segunda ocurrencia se pone n 
		N = Para ir una ocurrencia atrás
```
# Sustituir
Con `:s` y los comandos de búsqueda
```
:s/ocurrencia/nuevaPalabra
	Cambia una ocurrencia por una palabra a partir de donde se encuentra el 
	cursor hasta el final de la linea actual
	
:s/ocurrencia/nuevaPalabra/g
	Lo mismo que el de arriba pero con todas las ocurrencias
	
:%s/ocurrencia/nuevaPalabra/g
	Cambia todas las ocurrencias del archivo 
	
:%s/ocurrencia/nuevaPalabra/gc
	Lo mismo que el comando de arriba pero va a preguntar uno a uno si se quiere 
	cambiar la ocurrencia
	
:.$s/ocurrencia/nuevaPalabra/gc
	Este es en todo el archivo pero a partir de donde está el cursor 
```
# Cambiar espacios por tabs
```
:set noexpandtab
:retab!
```
