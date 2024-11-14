# Pruebas de Consultas DNS

Este archivo muestra los resultados de las pruebas realizadas desde el ordenador anfitrión para comprobar que las consultas DNS hacia el servidor maestro (DNSA) y el servidor esclavo (DNSB) funcionan correctamente. Las pruebas incluyen consultas directas e inversas para nombres de dominio dentro del dominio `ies.test` y sus subdominios.

## Configuración de los Servidores DNS

- **DNSA**: Servidor maestro para las zonas `informatica.ies.test`, `aulas.ies.test`, `departamentos.ies.test`, y la zona inversa `57.168.192.in-addr.arpa`.
- **DNSB**: Servidor esclavo para las zonas `informatica.ies.test` y `aulas.ies.test`.

## Pruebas Realizadas

### 1. Prueba de Resolución Directa hacia el Servidor Maestro (DNSA)

#### Comando `nslookup` y `dig`

 ![primera captura](capturas-dns/1.PNG)
 ![segunda captura](capturas-dns/2.PNG)
 ![tercera captura](capturas-dns/3.PNG)
 ![cuarta captura](capturas-dns/4.PNG)
 ![quinta captura](capturas-dns/5.PNG)
 ![sexta captura](capturas-dns/6.PNG)
![septima captura](capturas-dns/7.PNG)
