# CASINO LFI - Inclusión peligrosa en el servidor del casino

En este laboratorio deberás analizar una página web aparentemente simple de un casino en línea, detectar una vulnerabilidad de inclusión de archivos locales (LFI) y acceder a un archivo oculto que contiene una flag. En este laboratorio aprenderás:

- Exploración de parámetros en URL
- Detección de vulnerabilidades LFI
- Manipulación de rutas relativas
- Acceso a archivos internos del sistema
- Lectura de flags desde el servidor web

<how-to-start>
   
## 🌱 Cómo iniciar este laboratorio

Sigue las siguientes instrucciones para comenzar:

1. **Descarga la máquina virtual** desde este [enlace](https://storage.googleapis.com/cybersecurity-machines/casino-lab.ova).
2. **Importa la máquina** en tu gestor de virtualización preferido (VirtualBox, VMware, etc.).
3. Una vez iniciada la máquina, ¡ya puedes comenzar con el laboratorio!

</how-to-start>

## 📄 Instrucciones

Estás frente al sitio web de un casino ficticio llamado **Casino Royale**. Tu tarea es analizar cómo está construida la página y descubrir si hay alguna vulnerabilidad en el uso de rutas y archivos.

1. **Descubre la dirección IP de la máquina CASINO LFI.**: La máquina está conectada a la misma red que tú, pero su IP no ha sido proporcionada. Utiliza herramientas como `nmap`, `netdiscover` o `arp-scan` para escanear la red.

2. **Accede al sitio web alojado en el servidor.**
   - Abre tu navegador y visita la IP asignada.
   - Observa el contenido que se muestra con:
     ```
     ?page=home
     ?page=about
     ```

3. **Explora el parámetro vulnerable.**: ¿Podés modificar el valor del parámetro `page`?


4. **Extrae el contenido de la flag.**


**Recuerda:** no todo archivo incluido fue pensado para ser visto.

¡Feliz hackeo!

