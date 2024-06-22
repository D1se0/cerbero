# Cerbero

Cerbero es una herramienta de línea de comandos diseñada para realizar ataques de fuerza bruta contra servicios SSH y FTP. Esta herramienta puede ser útil para auditorías de seguridad o pruebas de penetración donde se necesite probar la resistencia de las credenciales de acceso.

<p align="center">
  <img src="https://github.com/D1se0/cerbero/assets/164921056/064b49a7-e7f8-4548-9017-1a68390a032e" alt="Directorybrute" width="400">
</p>

---

## Características Principales

- Soporte para ataques de fuerza bruta a servicios SSH y FTP.
- Capacidad para manejar múltiples usuarios y contraseñas a través de archivos o entradas directas.
- Opción para enumerar usuarios a través de vulnerabilidades conocidas en versiones de SSH.
- Manejo de hilos para mejorar el rendimiento durante los ataques.
- Interfaz de línea de comandos intuitiva y fácil de usar.

## Requisitos

Para ejecutar Cerbero, se necesitan las siguientes dependencias:

- Python 3.x
- Bibliotecas Python:
  - paramiko
  - ftplib
  - colorama

Puedes instalar las dependencias ejecutando:

```bash
pip install -r requirements.txt
```

## Uso

### Ejemplos de Uso Básico

1. **Ataque SSH con un usuario y contraseña específicos:**

```bash
 python cerbero.py -H <target_ip> -s ssh -u <username> -p <password>
```

Ataque FTP con archivos de usuarios y contraseñas:

python cerbero.py -H <target_ip> -s ftp -U users.txt -P passwords.txt

Opciones Disponibles
-H, --host: Especifica la dirección IP del host de destino.
-s, --service: Define el servicio a atacar (ssh o ftp).
-u, --user: Proporciona un usuario único para la autenticación.
-p, --passwd: Proporciona una contraseña única para la autenticación.
-U, --user-file: Especifica un archivo con una lista de usuarios.
-P, --passwd-file: Especifica un archivo con una lista de contraseñas.
-t, --threads: Número de hilos a utilizar para aumentar la velocidad del ataque (por defecto: 5).
-o, --output-file: Guarda los resultados en un archivo especificado.
-c, --success-continue: Continúa con la siguiente combinación de usuario/contraseña válida después de encontrar una.
-e, --extra-params: Parámetros adicionales para personalizar las combinaciones de usuario/contraseña.
-en, --enumerate-users: Intenta enumerar usuarios aprovechando vulnerabilidades conocidas en versiones de SSH.

Ejecución como Root
Para ejecutar Cerbero con todos los permisos necesarios, se recomienda ejecutarlo como usuario root o con privilegios equivalentes, especialmente si se necesitan puertos bajos o se realizan múltiples conexiones simultáneas.

Contribuciones
Si deseas contribuir a Cerbero, ¡estamos abiertos a sugerencias, reportes de problemas y solicitudes de mejora! Por favor, crea un issue en este repositorio o envía una pull request con tus cambios.

Agradecimientos
Cerbero fue creado por Diseo (@d1se0) como proyecto personal. Agradecemos a todos los contribuidores y usuarios por su apoyo y retroalimentación.

Este formato te permitirá tener un README.md estructurado y claro para tu proyecto en GitHub, proporcionando a los usuarios una guía rápida sobre cómo usar tu herramienta y los detalles necesarios para comenzar. Asegúrate de personalizarlo según tus necesidades y detalles específicos de implementación.
