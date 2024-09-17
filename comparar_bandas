import spotipy
from spotipy.oauth2 import SpotifyClientCredentials
import tkinter as tk
from tkinter import messagebox

# Autenticación con Spotify
client_id = '7e0a1e3f35bc49028ab8ed5f2d0afabb'
client_secret = '622cfc625aa04845b80adbcf9fa39834'

auth_manager = SpotifyClientCredentials(client_id=client_id, client_secret=client_secret)
sp = spotipy.Spotify(auth_manager=auth_manager)

# Función para obtener datos de la banda
def obtener_datos_banda(nombre_banda):
    try:
        resultado = sp.search(q='artist:' + nombre_banda, type='artist')
        artista = resultado['artists']['items'][0]
        
        nombre = artista['name']
        seguidores = artista['followers']['total']
        popularidad = artista['popularity']
        generos = artista['genres']
        
        return {
            'nombre': nombre,
            'seguidores': seguidores,
            'popularidad': popularidad,
            'géneros': generos
        }
    except IndexError:
        messagebox.showerror("Error", f"No se encontró la banda '{nombre_banda}' en Spotify.")
        return None

# Función para mostrar la comparación
def comparar_bandas():
    banda1_nombre = entry_banda1.get()
    banda2_nombre = entry_banda2.get()
    
    banda1 = obtener_datos_banda(banda1_nombre)
    banda2 = obtener_datos_banda(banda2_nombre)
    
    if banda1 and banda2:
        resultado = f"Comparación entre {banda1['nombre']} y {banda2['nombre']}:\n\n"
        resultado += f"Seguidores {banda1['nombre']}: {banda1['seguidores']}\n"
        resultado += f"Seguidores {banda2['nombre']}: {banda2['seguidores']}\n\n"
        
        resultado += f"Popularidad {banda1['nombre']}: {banda1['popularidad']}\n"
        resultado += f"Popularidad {banda2['nombre']}: {banda2['popularidad']}\n\n"
        
        resultado += f"Géneros {banda1['nombre']}: {', '.join(banda1['géneros'])}\n"
        resultado += f"Géneros {banda2['nombre']}: {', '.join(banda2['géneros'])}\n\n"
        
        if banda1['seguidores'] > banda2['seguidores']:
            resultado += f"{banda1['nombre']} es más popular en términos de seguidores."
        else:
            resultado += f"{banda2['nombre']} es más popular en términos de seguidores."
        
        text_resultado.config(state='normal')
        text_resultado.delete(1.0, tk.END)  # Limpiar el texto anterior
        text_resultado.insert(tk.END, resultado)
        text_resultado.config(state='disabled')
    else:
        text_resultado.config(state='normal')
        text_resultado.delete(1.0, tk.END)  # Limpiar el texto anterior
        text_resultado.config(state='disabled')

# Crear la ventana principal
ventana = tk.Tk()
ventana.title("Comparación de Popularidad de Bandas")

# Etiquetas y campos de entrada
label_banda1 = tk.Label(ventana, text="Nombre de la Banda 1:")
label_banda1.pack(pady=5)

entry_banda1 = tk.Entry(ventana, width=30)
entry_banda1.pack(pady=5)

label_banda2 = tk.Label(ventana, text="Nombre de la Banda 2:")
label_banda2.pack(pady=5)

entry_banda2 = tk.Entry(ventana, width=30)
entry_banda2.pack(pady=5)

# Botón para comparar
btn_comparar = tk.Button(ventana, text="Comparar", command=comparar_bandas)
btn_comparar.pack(pady=10)

# Área de texto para mostrar los resultados
text_resultado = tk.Text(ventana, height=15, width=50, state='disabled')
text_resultado.pack(pady=10)

# Iniciar la interfaz gráfica
ventana.mainloop()
