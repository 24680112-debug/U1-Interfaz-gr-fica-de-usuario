# U1-Interfaz gráfica de usuario
### Apuntes de clase

# 1.1 Creación de interfaz gráfica para usuarios
Este tema trata sobre cómo "dibujar" la ventana y organizar los elementos.

* Concepto: En Flet, la interfaz se construye mediante un árbol de controles. El contenedor principal es page.

* Relación con los archivos: * En S2.py (Calculadora), usas ft.Column y ft.Row para organizar los botones de forma tabular.

  * En Forms.py, configuras el lienzo con page.title, page.bgcolor y page.padding para dar identidad visual a la app.

### Ejemplo clave:
```bash
# Configuración básica de la ventana (Forms.py)
page.title = "Registro de Estudiantes"
page.theme_mode = ft.ThemeMode.LIGHT
```
# 1.2 Tipos de eventos
Los eventos son "cosas que pasan" en la aplicación (clics, cambios de texto, envíos).

* Eventos Comunes:

  * on_click: Cuando el usuario presiona un botón.

  * on_change: Cuando el usuario escribe en un campo.

  * subscribe: Un evento especial de red/comunicación (visto en chat1.py).

* Relación con lols archivos:

  * En chat1.py, usas page.pubsub.subscribe(on_message). Este es un evento de tipo "broadcast" o difusión, donde la app reacciona cuando alguien envía un mensaje al servidor.
  
