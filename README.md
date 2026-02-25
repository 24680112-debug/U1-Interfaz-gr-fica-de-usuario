# U1-Interfaz gráfica de usuario
### Apuntes de clase

# 1.1 Creación de interfaz gráfica para usuarios
Este tema trata sobre cómo "dibujar" la ventana y organizar los elementos.

* Concepto: En Flet, la interfaz se construye mediante un árbol de controles. El contenedor principal es page.

* Relación con los archivos: * En S2.py (Calculadora), se usa ft.Column y ft.Row para organizar los botones de forma tabular.

  * En Forms.py, configuras el lienzo con page.title, page.bgcolor y page.padding para dar identidad visual a la app.

### Ejemplo clave:
```bash
# Configuración básica de la ventana (Forms.py)
page.title = "Registro de Estudiantes"
page.theme_mode = ft.ThemeMode.LIGHT
```
### Es vital entender cómo acomodar los elementos.

Columnas y Filas (ft.Column y ft.Row)
* ft.Column: Organiza los elementos de forma vertical (uno arriba de otro). Es la base de Forms.py para listar los campos de texto.

* ft.Row: Organiza los elementos de forma horizontal (uno al lado del otro).

* Espaciado (spacing): Es una propiedad que define la distancia en píxeles entre cada control hijo dentro de la fila o columna.

### El uso de expand y alignment
* expand: En S2.py y Forms.py, se usa expand=True para que un control ocupe todo el espacio disponible en su contenedor padre.

* alignment: Permite centrar o mover los elementos. Por ejemplo, en S2.py, el display de la calculadora usa alignment=ft.alignment.Alignment(0, 0) para centrar el texto totalmente.


# 1.2 Tipos de eventos
Los eventos son "cosas que pasan" en la aplicación (clics, cambios de texto, envíos).

* Eventos Comunes:

  * on_click: Cuando el usuario presiona un botón.

  * on_change: Cuando el usuario escribe en un campo.

  * subscribe: Un evento especial de red/comunicación (visto en chat1.py).

* Relación con lols archivos:

  * En chat1.py, se usa page.pubsub.subscribe(on_message). Este es un evento de tipo "broadcast" o difusión, donde la app reacciona cuando alguien envía un mensaje al servidor.
  <img width="1356" height="586" alt="image" src="https://github.com/user-attachments/assets/38bccb40-035d-4370-a16f-f413baed98c6" />


# 1.3 Manejo de eventos
Es la lógica que se ejecuta cuando ocurre un evento (los Event Handlers).

* Concepto: Se define una función y se asigna a la propiedad del control. Es vital usar page.update() para que los cambios se vean reflejados.

* Relación con los archivos:

  * En S2.py, la función numero_click(e) es la encargada de capturar qué número se presionó y actualizar el display de la calculadora.

  * Tip de Pro: El parámetro e (de event) contiene información sobre quién disparó el evento (por ejemplo, e.control.data).
<img width="377" height="328" alt="image" src="https://github.com/user-attachments/assets/ed9b7835-d17d-4e6e-8741-b458008726b4" />


### El flujo de actualización de la página
En el desarrollo de GUIs, la interfaz es estática hasta que el código le ordena refrescarse.

1. Captura: El usuario interactúa (ej. escribe en un TextField).

2. Procesamiento: Se ejecuta la función ligada al evento (ej. enviar_click).

3. Refresco: Se llama a page.update() para que Flet redibuje los cambios en la pantalla.

  Dato importante: Sin el page.update(), aunque cambies el valor de una variable en el código, el usuario seguirá viendo la información vieja en su pantalla.

# 1.4 Manejo de componentes gráficos de control
Este tema se refiere a conocer y configurar los "widgets" o controles disponibles.

* Componentes vistos en los códigos:

| Componente | Archivo de referencia | Uso principal |
| :--- | :---: | ---: |
| ft.TextField | Forms.py / chat1.py | Entrada de texto (Nombre, Email, Mensajes). |
| ft.Dropdown | Forms.py | Selección de opciones cerradas (Carrera, Semestre). |
| ft.RadioGroup| Forms.py | Selección de una única opción entre varias (Género). |
| ft.Container | S2.py | Personalización visual (bordes, colores, alineación). |
| ft.Divider | S2.py | Separación visual de secciones. |

### Nota sobre Lógica de Programación (ejercicio1.py)
EL archivo ejercicio1.py es la base de todo. Aunque es un script de consola (CLI), la lógica de validación que usas ahí:
```bash
if int(edad_usuario) > 18: # Lógica de decisión
```
### Basado en tel archivo Forms.py, tenemos una tabla sobre cuándo usar cada componente gráfico de control:
| Control | Cuándo usarlo | Ejemplo en los códigos |
|:----------|:------:|--------:|
| TextField    | Cuando necesitas texto libre (nombres, correos, mensajes).  | txt_nombre, txt_email.  |
| Dropdown | Cuando hay una lista definida de opciones (carreras, semestres).| dd_carrera, dd_semestre.|
| RadioGroup | Cuando el usuario debe elegir estrictamente una opción visible.| genero_group.|
| ElevatedButton | Para disparar la acción principal de procesamiento. | btn_enviar. |


## Referencias bibliográficas
* Flet Team. (2024). Flet: Build Flutter apps in Python. Recuperado de https://flet.dev/docs/.
* Matthes, E. (2023). Python Crash Course: A Hands-On, Project-Based Introduction to Programming. No Starch Press.
* Gamma, E., Helm, R., Johnson, R., & Vlissides, J. (1994). Design Patterns: Elements of Reusable Object-Oriented Software. Addison-Wesley.
