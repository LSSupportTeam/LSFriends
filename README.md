# LSFriends - Sistema de Amigos para Minecraft

LSFriends es un completo sistema de amigos para servidores Minecraft compatible con BungeeCord y Velocity. Permite a los jugadores gestionar amigos, enviar solicitudes, chatear en privado y más.

![LSFriends Logo](https://github.com/LSSupportTeam/LSFriends/raw/main/logo.png)

## Características

- **Sistema de amigos completo**: Añadir, eliminar y gestionar amigos
- **Solicitudes de amistad**: Enviar, aceptar o rechazar solicitudes
- **Mensajes privados**: Comunicación directa entre amigos
- **Notificaciones**: Avisos cuando amigos se conectan o desconectan
- **Menús intuitivos**: Interfaz gráfica para gestionar todas las funciones
- **Almacenamiento flexible**: Soporte para MySQL y archivos locales
- **Compatibilidad múltiple**: Funciona con BungeeCord y Velocity
- **Multiservidor**: Permite interactuar con amigos en diferentes servidores

## Requisitos

- Java 8 o superior
- Servidor Minecraft con Spigot/Paper 1.8+
- BungeeCord o Velocity

## Instalación

1. Descarga los archivos JAR de la [página de releases](https://github.com/LSSupportTeam/LSFriends/releases)
2. Coloca `ls-friends-proxy.jar` en la carpeta de plugins de tu proxy (BungeeCord/Velocity)
3. Coloca `ls-friends.jar` en la carpeta de plugins de cada servidor Spigot/Paper
4. Reinicia tu servidor proxy y servidores Spigot/Paper
5. Configura los archivos de configuración según sea necesario

## Arquitectura

LSFriends consta de dos componentes principales:

- **LSFriends-Proxy**: Plugin para BungeeCord/Velocity que gestiona toda la lógica del sistema de amigos, almacenamiento de datos y comunicación entre servidores.
- **LSFriends**: Plugin para Spigot/Paper que proporciona la interfaz gráfica y maneja la interacción con los jugadores.

## Configuración

### Configuración del Proxy (BungeeCord/Velocity)

```yaml
# Configuración del almacenamiento
storage-type: "FILE" # FILE o MYSQL

# Configuración de MySQL (si se utiliza)
mysql:
  host: "localhost"
  port: 3306
  database: "lsfriends"
  username: "root"
  password: "password"
  table-prefix: "ls_"

# Límites
max-friends: 100
friend-request-timeout: 300 # segundos
```

### Configuración del Servidor (Spigot/Paper)

```yaml
# Configuración de interfaz
menu-title: "&8&l» &b&lLSFriends &8&l«"

# Conexión con el proxy
proxy:
  host: "127.0.0.1"
  port: 25565
```

## Comandos

### Comandos principales
- `/ls` - Abre el menú principal del sistema de amigos
- `/ls help` - Muestra la ayuda del plugin
- `/ls add <jugador>` - Envía una solicitud de amistad
- `/ls accept <jugador>` - Acepta una solicitud de amistad
- `/ls deny <jugador>` - Rechaza una solicitud de amistad
- `/ls remove <jugador>` - Elimina a un amigo
- `/ls list` - Muestra tu lista de amigos
- `/ls pending` - Muestra las solicitudes pendientes
- `/ls toggle` - Activa/desactiva las solicitudes de amistad
- `/ls msg <jugador> <mensaje>` - Envía un mensaje privado
- `/lsr <mensaje>` - Responde al último mensaje recibido
- `/ls reload` - Recarga la configuración del plugin (requiere permiso)

## Permisos

- `lsfriends.reload` - Permite recargar la configuración del plugin

## Solución de problemas

### Problemas comunes

1. **No se pueden enviar mensajes entre servidores**
   - Asegúrate de que el canal `lsfriends:main` está registrado correctamente
   - Verifica que las direcciones IP y puertos en la configuración son correctos

2. **Los datos no se guardan en MySQL**
   - Comprueba las credenciales de la base de datos
   - Asegúrate de que la base de datos existe y es accesible

3. **La interfaz gráfica no aparece**
   - Verifica que la versión del servidor es compatible
   - Asegúrate de que la configuración del menú es correcta

## Compatibilidad

LSFriends ha sido probado y es compatible con:

- **Proxy**: BungeeCord, Waterfall, Velocity
- **Servidor**: Spigot, Paper, PurPur

## Personalización

El plugin es altamente personalizable a través de los archivos de configuración. Puedes modificar:

- Mensajes y prefijos
- Diseño y elementos de los menús
- Colores y efectos visuales
- Sonidos de notificaciones
- Y mucho más

## Contribuir

¿Quieres contribuir al desarrollo de LSFriends? ¡Genial! Aquí hay algunas formas de hacerlo:

1. Reportar bugs o sugerir mejoras en la [sección de issues](https://github.com/LSSupportTeam/LSFriends/issues)
2. Enviar pull requests con nuevas características o correcciones
3. Mejorar la documentación o traducciones

## Compilación desde el código fuente

Para compilar el proyecto desde el código fuente:

1. Clona el repositorio
   ```bash
   git clone https://github.com/LSSupportTeam/LSFriends.git
   ```

2. Navega a la carpeta del proyecto
   ```bash
   cd LSFriends
   ```

3. Compila el proyecto usando Maven
   ```bash
   mvn clean package
   ```

4. Los archivos JAR compilados estarán en las carpetas `ls-friends/target` y `ls-friends-proxy/target`

## Licencia

LSFriends está licenciado bajo la [Licencia MIT](LICENSE).

## Contacto

Para soporte o consultas, puedes:
- Abrir un [issue en GitHub](https://github.com/LSSupportTeam/LSFriends/issues)
- Contactar al equipo de desarrollo en Discord: [Enlace al Discord](https://discord.gg/lsfriends)

---

Desarrollado con ❤️ por LSTeam 
