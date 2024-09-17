# Comparador de Popularidad de Bandas (Spotify API)

Este proyecto es una aplicación de Python que permite comparar la popularidad de dos bandas de música utilizando la API de Spotify. Muestra información como el número de seguidores, popularidad y géneros de las bandas comparadas en una interfaz gráfica amigable construida con `tkinter`.

## Funcionalidades

- Conexión a la API de Spotify.
- Comparación de dos bandas en base a:
  - Número de seguidores.
  - Popularidad.
  - Géneros musicales.
- Interfaz gráfica para el ingreso de datos y visualización de los resultados.

## Requisitos

- Python 3.x
- Una cuenta de desarrollador de Spotify [Spotify for Developers](https://developer.spotify.com) para obtener tus credenciales (Client ID y Client Secret).

### Dependencias de Python

Antes de ejecutar la aplicación, asegurate de instalar las siguientes dependencias de Python:

```bash
pip install spotipy requests tkinter


Configuración
Obtené tus credenciales de Spotify:

Registrate en Spotify for Developers.
Creá una nueva aplicación y obtené tu Client ID y Client Secret.
Configura tus credenciales: En el archivo principal, reemplazá los valores de TU_CLIENT_ID y TU_CLIENT_SECRET con las credenciales de tu aplicación de Spotify:

python
Copiar código
client_id = 'TU_CLIENT_ID'
client_secret = 'TU_CLIENT_SECRET'
Ejecución
Cloná el repositorio a tu máquina local:

bash
Copiar código
git clone https://github.com/usuario/nombre-repositorio.git
Navegá al directorio del proyecto:

bash
Copiar código
cd nombre-repositorio
Ejecutá el archivo Python:

bash
Copiar código
python main.py
Ingresá los nombres de las bandas que querés comparar en los campos de texto de la interfaz gráfica y presioná "Comparar". Los resultados se mostrarán en la misma ventana.

Capturas de Pantalla

Estructura del Proyecto
bash
Copiar código
|-- main.py           # Archivo principal que contiene la lógica del programa
|-- README.md         # Este archivo
Mejoras Futuras
Agregar más estadísticas, como las canciones o álbumes más populares de cada banda.
Implementar la opción de exportar los resultados a un archivo CSV o PDF.
Mejorar la interfaz gráfica y agregar estilos personalizados.
Contribuciones
Si querés contribuir a este proyecto, podés hacerlo a través de pull requests o abriendo un issue en el repositorio. Se aceptan sugerencias y mejoras.
