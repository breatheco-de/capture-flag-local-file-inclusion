# Laboratorio CASINO LFI

Este laboratorio pone a prueba la capacidad del alumno para detectar una vulnerabilidad clásica de inclusión de archivos locales (LFI) en un sitio web. A través de la manipulación de parámetros en la URL, el alumno logrará acceder a archivos sensibles fuera del flujo visible del sitio.

En este laboratorio los alumnos comprenderán:

- Cómo identificar puntos vulnerables a LFI en una aplicación web.
- Cómo manipular rutas relativas para explorar el sistema de archivos.
- Cómo extraer archivos fuera del directorio expuesto.
- Cómo acceder a información sensible (flag) sin autenticación.


## Especificaciones de la máquina 🖥️

- **Sistema:** Ubuntu Server (o Debian sin GUI)
- **Servidor web:** Apache + PHP
- **Ruta del sitio:** `/var/www/html/index.php`
- **Contenido vulnerable:** Inclusión de archivos vía parámetro GET:

```php
<?php
$page = $_GET['page'] ?? 'home';
include("pages/$page.php");
?>
```

- **Carpeta de páginas:** `/var/www/html/pages/`
  - `home.php`
  - `about.php`

- **Archivo sensible:** `/var/www/html/flag.txt`


> **Nota:** No se requiere acceso por SSH ni escalado de privilegios. Todo se resuelve desde el navegador.


### Credenciales de la máquina

```bash
servername: casino-lfi-lab
username: student
password: 4geeks-lab
```

## Pasos esperados por el alumno

1. **Realiza reconocimiento de red para identificar la máquina.**
   - Utiliza herramientas como `nmap`, `netdiscover` o `arp-scan`.
   - Debe detectar una IP con el puerto **80 (HTTP)** abierto.

2. **Accede al sitio web desde el navegador.**
   - Introduce la IP descubierta en el navegador para cargar la landing page del casino.
   - Verá una URL como:
     ```
     http://<IP>/index.php?page=home
     ```

3. **Explora el parámetro `page` en la URL.**
   - Debe entender que los archivos se incluyen desde el directorio `pages/`.
   - Prueba diferentes valores: `home`, `about`, rutas inválidas, etc.

4. **Manipula el parámetro para escapar del subdirectorio.**
   - Intenta acceder a:
     ```
     ?page=../../flag
     ```

5. **Lee la flag directamente desde el navegador.**
   - Si lo hace correctamente, se mostrará el contenido de `flag.txt`.
   - El objetivo es que comprenda cómo funciona una vulnerabilidad de LFI y cómo acceder a recursos fuera del alcance previsto.
