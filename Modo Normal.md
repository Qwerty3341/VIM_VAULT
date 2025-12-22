- Ver los comandos del modo normal [[Comandos]]
- La mayoría de comandos se pueden concatenar con números para que lo haga `n` veces el comando 
# Navegando por el documento
```
w = word (Va al inicio de la siguiente palabra)
b = back (Va al inicio de la palabra anterior)
e = end (Va al final de la palabra siguiente)
```
# Navegando por líneas
```
$ = Va al final de una línea
% = se mueve entre paréntesis
0 = Se va al comienzo de la línea
^ =
número + tecla de navegación = se mueve n veces
```
# Nueva línea
```
o = open
	Crea una nueva línea
	Se puede concatenar con números 
		3o = hace 3 nuevas líneas
		
O = Abre una nueva línea por arriba de la línea
```
# Go
```
g = go 

gd = Busca la definición de una palabra
gf = Busca un archivo	
gg = regresa al principio del archivo
G = va al final del archivo
número + G = va a una línea en específico
```
# Cortar
```
x = elimina (corta) un caracter al frente del cursor

d = delate (borrar no existe, solo hay cortar)
	dw = delete word
	d$ = borra desde la posición del cursor hasta el final de la línea
	dd = borra una línea completa
	d + hjklweb = borra según la tecla de movimiento
	d + número + hjklweb = borrar n caracteres según la tecla de movimiento
```
# Pegar
```
p = paiste abajo de la línea actual (Al hacer un dd la línea se queda en el clipboard)
P = lo mismo que p pero por arriba de la línea actual

	La p y P se pueden encadenar con números
	La p y P se pueden encadenar con números
	La p y P se pueden encadenar con números
	La p y P se pueden encadenar con números
```
# Deshacer y Rehacer
```
u = undo
Ctr r = redo
```
# Reemplazar y cambiar
```
r + cualquier caracter = Va a remplazar un caracter 

R = va a dejarnos en modo reemplazar 

c = change 
	cw = Cambia una palabra (desde donde está el cursor)
	ciw = Cambia la palabra (dentro de cosas dentro de comillas o llaves) 

```



