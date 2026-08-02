Para este laboratorio de pruebas estaremos ocupando el hipervisor Oracle Virtual Box para crear maquinas virtuales tanto del firewall como del equipo servirá como cliente.
Primero haremos la instalación del firewall, usaremos pfSense CE(Comunity Edition). 
Lo primero será ir al sitio oficial de Netgate y descargar la imagen ISO de pfSense.
Ya que hayamos descargado la imagen lo siguiente será crear su MV. 
La MV se creará con los siguientes valores:
| Configuración | Estado              |
| ------------- | ------------------- |
| Memoria RAM   | ✅ 1024 MB           |
| CPU           | ✅ 2 núcleos         |
| Adaptador 1   | ✅ NAT (WAN)         |
| Adaptador 2   | ✅ Red interna (LAN) |
_________________________________________
Una vez aplicadas estas configuraciones podemos arrancar la MV e iniciar el proceso de instalación del sistema Operativo de pfSense en la maquina virtual.
Algunos problemas que se presentaron durante la instalación y como resolverlos:
Problema 1
Descripción
La máquina virtual mostraba:
CPU doesn't support long mode
Causa
La VM fue creada con el tipo Other en lugar de BSD / FreeBSD (64-bit).
Solución
Se eliminó la máquina virtual y se creó nuevamente con la configuración correcta.
Problema 2
La instalación iniciaba nuevamente al reiniciar.
Causa
La ISO seguía montada.
Solución
Se retiró el medio óptico virtual después de la instalación.
Problema 3
La interfaz LAN no aparecía inicialmente.
Solución
Se reasignaron las interfaces desde la opción Assign Interfaces del menú de consola.


Al terminar la instalación de pfSense y si todo salió correctamente veremos un menú parecido al siguiente:
<img width="732" height="412" alt="image" src="https://github.com/user-attachments/assets/e518c371-ac2a-4eb4-b84b-b01324ed7e82" />

**Instalación de Ubuntu en Oracle Virtual Box**

El siguiente punto ahora será crear la MV de nuestra maquina cliente la cual monitorearemos con el firewall

Usaremos los siguientes valores:
| Configuración |                                                Valor |
| ------------- | ---------------------------------------------------: |
| RAM           |                                              2048 MB |
| CPU           |                                                    2 |
| Disco         |                                       25 GB dinámico |
| Adaptador     | **Red interna** (la misma que usa la LAN de pfSense) |




