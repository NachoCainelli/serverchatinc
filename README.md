# Estructura usuario

usuario->socket (es un entero)
usuario->name (es un char*)

# Estructura CasillaTabla

CasillaTabla->usuario
CasillaTabla->libre (es un entero)

# MENSAJE PRIVADO

EN EL CLIENTE (llamado Cristian) ----> /msg Gonzalo hola

Internamente EN EL SERVIDOR:

* /msg en el switch para corroborar que es un comando valido
Ya dentro del switch
* Gonzalo se guarda en una variable nombre
* hola se guarda en una variable mensaje
* recorrer la tabla y donde haya un usuario Gonzalo realiza lo siguiente

send(Gonzalo, mensajeformateado, sizeof(mensajeformateado), 0)
send(Cristian, mensajeformateado2, sizeof(mensajeformateado2), 0)
printf(mensajeformateado3)

# MENSAJE GLOBAL

EN EL CLIENTE (llamado Cristian) ----> hola

Internamente EN EL SERVIDOR:

* entra en el switch de mensaje global
Ya dentro del switch
* hola se guarda en una variable mensaje
* recorrer la tabla y a todos los usuarios realizar

send(tabla[index].socket, mensajeformateado, sizeof(mensajeformateado),0)

fuera de la iteracion, printf(mensajeformateado)