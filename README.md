# Práctica de Configuración de Servidores DNS - ies.test

## Descripción General

En esta práctica se configuraron dos servidores DNS (DNSA y DNSB) para gestionar la resolución de nombres dentro de la red local de la institución. El dominio principal `ies.test` fue configurado en ambos servidores, así como las zonas de subdominios como `informatica`, `aulas` y `departamentos`, con el fin de simular un entorno de red real. Se implementó la resolución de nombres directa e inversa utilizando `bind9`, el software DNS más común en Linux.

## Estructura de Zonas y Configuración

Los servidores DNS se configuraron de acuerdo con las siguientes características:

1. **Dominio Principal:**
   - El dominio `ies.test` fue configurado tanto en **DNSA** como en **DNSB**.
   - DNSA se configuró como el servidor **maestro** para las zonas del dominio.
   - DNSB se configuró como un servidor **esclavo** de DNSA para las zonas `informatica` y `aulas`.

2. **Subdominios:**
   - **informatica.ies.test**: Configurado como una zona maestra en DNSA.
   - **aulas.ies.test**: Configurado como una zona maestra en DNSA.
   - **departamentos.ies.test**: Configurado como una zona maestra en DNSA.
   
3. **Zonas Inversas:**
   - Se configuró la zona inversa para la red `192.168.57.0/24` en DNSA, permitiendo la resolución de direcciones IP a nombres de dominio.

## Archivos de Configuración

### 1. **Archivo `named.conf.local` en DNSA**
Este archivo contiene las configuraciones de las zonas DNS en el servidor DNSA. Define las zonas `ies.test`, `informatica.ies.test`, `aulas.ies.test`, y la zona inversa `57.168.192.in-addr.arpa`.

```bash
zone "ies.test" {
    type master;
    file "/etc/bind/db.ies.test";
};

zone "informatica.ies.test" {
    type master;
    file "/etc/bind/db.informatica";
};

zone "aulas.ies.test" {
    type master;
    file "/etc/bind/db.aulas";
};

zone "departamentos.ies.test" {
    type master;
    file "/etc/bind/db.departamentos";
};

zone "57.168.192.in-addr.arpa" {
    type master;
    file "/etc/bind/db.57.168.192";
};
