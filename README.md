[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24070496&assignment_repo_type=AssignmentRepo)
<div align="center">

# Sesión · Entorno, Git, GitHub Classroom y fundamentos de Python

| Curso | Python Intermedio para Análisis de Datos · DIAN 2026 |
|---|---|
| Duración | 4 horas |
| Modalidad | Virtual sincrónico |
| Prerrequisitos | Ninguno · solo un navegador actualizado y conexión a internet |
| Participante | Wilmer García Torres |

</div>

---

## Cómo leer este material

Este material está pensado para leerse con la terminal abierta al lado. Conviene ejecutar cada comando cuando aparece, observar la salida y no avanzar hasta entender qué pasó.

Las secciones marcadas con **▶ Pausa y piensa** son momentos para detenerse antes de seguir. Están justo donde suele aparecer una confusión.

Las secciones marcadas con **🔁 Ciclo Git** son recordatorios para guardar el avance. Cada uno deja evidencia de lo que hiciste en esa etapa.

---

## Contenido

<details open>
<summary>Ver contenido de la sesión</summary>

- [Introducción](#introducción)
- [Objetivos](#objetivos)
- [GitHub Classroom](#github-classroom)
- [Explorar el repositorio](#explorar-el-repositorio)
- [🔁 Primer ciclo Git](#-primer-ciclo-git)
- [Python y sus dependencias](#python-y-sus-dependencias)
- [🔁 Segundo ciclo Git](#-segundo-ciclo-git)
- [Python como lenguaje](#python-como-lenguaje)
- [El menú principal](#el-menú-principal)
- [Funciones y procedimientos](#funciones-y-procedimientos)
- [Encadenamiento de funciones](#encadenamiento-de-funciones)
- [🔁 Ciclo Git · bloque 1](#-ciclo-git--bloque-1)
- [Condicionales simples](#condicionales-simples)
- [Condicionales anidados](#condicionales-anidados)
- [Condicionales encadenados](#condicionales-encadenados)
- [🔁 Ciclo Git · bloque 2](#-ciclo-git--bloque-2)
- [Ciclos con repetición definida · for](#ciclos-con-repetición-definida--for)
- [Ciclos con repetición indefinida · while](#ciclos-con-repetición-indefinida--while)
- [🔁 Ciclo Git · bloque 3](#-ciclo-git--bloque-3)
- [Listas](#listas)
- [Diccionarios](#diccionarios)
- [Menús de consola](#menús-de-consola)
- [Documentación](#documentación)
- [🔁 Ciclo Git · cierre](#-ciclo-git--cierre)
- [Banco de ejercicios adicional](#banco-de-ejercicios-adicional)
- [Troubleshooting](#troubleshooting)
- [Para profundizar](#para-profundizar)
- [Cierre](#cierre)
- [Bibliografía](#bibliografía)

</details>

---

## Introducción

El primer obstáculo de un curso de programación no es el código: es el entorno. Antes de escribir algo útil hay que resolver dónde va a vivir ese código, cómo se guarda, cómo se comparte y cómo se recupera si algo sale mal.

Esta sesión construye ese entorno paso a paso y, una vez en pie, arranca el lenguaje desde los fundamentos: qué es Python, cómo se estructura, y las piezas básicas con las que se construye cualquier programa de análisis de datos.

---

## Objetivos

Al finalizar esta sesión podrás:

- Aceptar una tarea en GitHub Classroom y entender la estructura del repositorio que recibes
- Explorar un proyecto Python en Codespaces y explicar para qué sirve cada carpeta
- Ejecutar el ciclo Git completo: `add`, `commit`, `push` y verificar en github.com
- Crear un ambiente virtual, instalar dependencias desde `requirements.txt` y explicar para qué sirve cada paso
- Escribir funciones, condicionales, ciclos, listas y diccionarios en Python aplicados al contexto del curso
- Agregar opciones activas al menú principal del proyecto

---

## Git y GitHub

### El problema que resuelven

Trabajas en un archivo llamado `proceso_declaraciones.py` y lo modificas varias veces durante la semana. Sin ninguna herramienta de control, la carpeta termina así:

```
proceso_declaraciones.py
proceso_declaraciones_v2.py
proceso_declaraciones_FINAL.py
proceso_declaraciones_FINAL_ESTE.py
proceso_declaraciones_USAR_ESTE.py
```

Esa es la solución natural cuando no hay nada que lleve el historial.

**Git** resuelve ese problema llevando el registro completo de cambios del proyecto, de modo que siempre tienes un solo archivo pero puedes volver a cualquier versión anterior con un comando.

Git registra cambios localmente, en tu propia máquina. 

**GitHub** es el servicio web donde esos cambios se publican y se comparten. La diferencia es parecida a la que hay entre escribir un documento y subirlo a una carpeta compartida: son dos acciones distintas aunque vayan seguidas.

### Los conceptos que más vas a usar

| Concepto | Qué es |
|----------|--------|
| **Repositorio (repo)** | Carpeta del proyecto con historial de cambios incluido |
| **Commit** | Punto de control guardado con un mensaje descriptivo |
| **Push** | Subir commits locales al repositorio en GitHub |
| **Pull** | Traer cambios del repositorio remoto al local |

> [!TIP]
> **▶ Pausa y piensa:** ¿cuál es la diferencia entre Git y GitHub? Antes de seguir, intenta explicarlo con tus palabras. Si no puedes, vuelve al párrafo anterior y léelo de nuevo; la distinción va a aparecer muchas veces en el curso.

### Crear la cuenta en GitHub

Ve a [github.com](https://github.com) y haz clic en **Sign up**.

GitHub pide un nombre de usuario, un correo y una contraseña. Usa tus **credenciales personales**, no las institucionales: la cuenta es tuya, y la vas a querer conservar más allá de este curso. Para el nombre de usuario elige algo que te identifique profesionalmente; algo como `maria-lopez-dev` o `jcardona-datos` funciona bien, porque ese nombre va a aparecer en la URL de tu repositorio y en tu perfil público.

Después del registro, GitHub envía un correo de verificación. Haz clic en el enlace antes de continuar.


## GitHub Classroom

### Qué es

GitHub Classroom es una herramienta construida sobre GitHub que distribuye repositorios de trabajo individuales. Cuando el instructor crea una tarea en Classroom y comparte el enlace de invitación, cada participante que abre ese enlace y acepta recibe su propia copia privada del repositorio, con todos los archivos del curso ya incluidos.

La copia es tuya. Lo que hagas ahí no afecta el repositorio del instructor ni el de ningún compañero. El instructor puede ver el historial de todos los repositorios desde un panel, pero no puede modificar el tuyo.

```
Repositorio plantilla del instructor
         ↓  (GitHub Classroom duplica para cada participante)
Tu repositorio: sesion-01-tu-usuario
         ↓  (lo abres en Codespaces)
Workspace en la nube listo para trabajar
         ↓  (git push)
Tu avance queda visible en github.com
```

### Cómo aceptar la tarea

El instructor compartirá un enlace de invitación. El enlace tiene esta forma:

```
https://classroom.github.com/a/XXXXXXXX
```

**Paso 1.** Abre el enlace en el navegador. Si no has iniciado sesión en GitHub, te pedirá que lo hagas.

**Paso 2.** Aparece una pantalla con el nombre de la tarea y el botón verde **Accept this assignment**. Haz clic.

**Paso 3.** GitHub tarda entre 30 y 60 segundos. La página muestra un mensaje de configuración. Cuando termina, aparece el enlace a tu repositorio personal.

**Paso 4.** Abre ese enlace. Tu repositorio se llama algo como `sesion-01-tu-usuario`.

> [!TIP]
> **▶ Pausa y piensa:** antes de continuar, ¿cuál es la diferencia entre el repositorio del instructor y el tuyo? ¿Qué pasaría si trabajaras directamente sobre el repositorio del instructor en lugar de en tu propia copia?

---

## Explorar el repositorio

### Abrir Codespaces

Estando en tu repositorio en github.com, haz clic en el botón verde **`<> Code`**. Aparece un menú con dos pestañas. Selecciona **Codespaces** y luego **Create codespace on main**.

GitHub tarda entre 30 y 60 segundos en preparar la máquina. Cuando termina, se abre **Visual Studio Code** en el navegador. Es el mismo editor que usarían si lo instalaran localmente, con la diferencia de que la máquina que ejecuta el código está en un servidor de GitHub.

Para abrir la terminal usa `Terminal → New Terminal` o el atajo `` Ctrl + ` ``.

### Qué tiene el Codespace al abrirlo

| Componente | Versión | Para qué sirve |
|------------|---------|----------------|
| Ubuntu Linux | 24.04 | Sistema operativo de la máquina virtual |
| Python | 3.12 | El intérprete que ejecuta el código |
| pip | 25.x | Descarga e instala librerías de Python |
| Git | 2.x | Registra y sincroniza cambios del proyecto |
| VS Code (web) | última | El editor de código |

Las librerías de análisis de datos (pandas, numpy, scikit-learn) **no vienen instaladas**. Las vas a instalar en esta sesión, una por una.

### Límites de la cuenta gratuita

| Recurso | Límite mensual |
|---------|---------------|
| Horas de cómputo | ~60 horas en máquina de 2 núcleos |
| Almacenamiento | 15 GB |
| Inactividad antes de pausarse | 30 minutos |
| Codespaces activos al mismo tiempo | 2 |

El Codespace se pausa solo después de 30 minutos sin actividad. Para retomarlo, ve a [github.com/codespaces](https://github.com/codespaces) y GitHub lo reactiva con todo tu trabajo, pero para que los cambios se mantengan es importante seguir el ciclo de add, commit y push a cualquier actividad. El código se debe almacenar en Github, Codespace es sólo un espacio de consulta temporal. 

### Visual Studio Code

**Visual Studio Code** (VS Code) es un editor de código desarrollado por Microsoft y publicado en 2015. Es software libre, su código fuente está en GitHub, y se convirtió en el editor más usado entre desarrolladores según encuestas anuales de Stack Overflow. Arranca rápido, consume poca memoria y tiene un sistema de extensiones que permite adaptarlo a casi cualquier lenguaje. Para Python tiene extensiones que detectan errores mientras escribes, sugieren nombres de variables y funciones, y permiten ejecutar código línea por línea.

Lo que ves en Codespaces es exactamente VS Code, corriendo en un servidor de GitHub en lugar de en tu propia máquina. La diferencia práctica es que la máquina que ejecuta el código no es la tuya; todo lo demás, el editor, los atajos y las extensiones, funciona igual.

La interfaz tiene cuatro áreas:

```
┌─────────────────────┬──────────────────────────────────────┐
│  EXPLORADOR DE      │                                      │
│  ARCHIVOS           │   EDITOR DE CÓDIGO                   │
│  (panel izquierdo)  │                                      │
│                     │   Aquí escribes y editas archivos    │
│  📁 procesamiento_  │                                      │
│     datos/          │                                      │
│    📁 data/         │                                      │
│    📁 src/          │                                      │
│    📄 main.py       │                                      │
│    📄 README.md     │                                      │
├─────────────────────┴──────────────────────────────────────┤
│  TERMINAL INTEGRADA                                         │
│  $ python main.py                                           │
└─────────────────────────────────────────────────────────────┘
```

| Área | Para qué sirve |
|------|----------------|
| Explorador de archivos | Abrir, crear y organizar archivos del proyecto |
| Editor | Escribir y editar código Python, Markdown, CSV |
| Terminal | Ejecutar comandos de Python, pip y Git |
| Barra de estado (abajo) | Ver errores, el intérprete activo y la rama Git actual |

Para abrir la terminal usa `Terminal → New Terminal` o el atajo `` Ctrl + ` ``. Si ese atajo no responde en tu teclado, prueba con `Ctrl + Shift + ñ`.


### La estructura del repositorio

Abre la terminal y ejecuta:

```bash
ls -la
```

Verás algo así:

```
.gitignore
README.md
data/
main.py
requirements.txt
src/
```

Revisemos cada elemento.

**`src/`**

Es la carpeta donde vive el código Python del proyecto. Abre la terminal y ejecuta:

```bash
ls src/
```

Verás `__init__.py` y `utils.py`. El archivo `__init__.py` está vacío y cumple un rol técnico: le indica a Python que `src` es un paquete desde el que se pueden importar funciones. Sin él, la línea `from src.utils import algo` fallaría.

`utils.py` contiene los esqueletos de las funciones que vas a escribir durante la sesión.

**`data/input/` y `data/output/`**

```bash
ls data/
ls data/input/
ls data/output/
```

`data/input/` es donde irán los archivos de datos que el proyecto consuma: CSV, TXT, archivos Excel. Por ahora está vacía; los archivos de práctica se integran en futuras sesiones.

`data/output/` es donde el proyecto guardará los resultados que genere: archivos procesados, reportes, exportaciones. También vacía por ahora.

> [!NOTE]
> Mantener los datos separados del código hace que el repositorio sea más limpio y que sea más difícil confundir un archivo de entrada con uno de salida.

**`.gitignore`**

```bash
cat .gitignore
```

Este archivo le dice a Git qué no rastrear. Verás entradas como `.venv/` y `__pycache__/`. Cuando en unos minutos creemos el ambiente virtual, la carpeta `.venv/` aparecerá en el proyecto pero Git la ignorará porque está en este archivo. Sin el `.gitignore`, Git intentaría subir cientos de megabytes de archivos del ambiente virtual que no tienen ningún valor en el repositorio.

> [!NOTE]
> El repositorio `github/gitignore` en GitHub mantiene plantillas actualizadas para cada lenguaje. La plantilla oficial de Python está en [github.com/github/gitignore/blob/main/Python.gitignore](https://github.com/github/gitignore/blob/main/Python.gitignore) y cubre casos adicionales que irán apareciendo a medida que el proyecto crece.


**`README.md`**

```bash
cat README.md
```

Es la documentación de entrada del proyecto: qué hace, cómo se instala y cómo se ejecuta. Es lo primero que ve cualquier persona que llega al repositorio. Está escrito en Markdown, el mismo formato de este material. Sobre este formato aprenderemos en sesiones posteriores.

**`requirements.txt`**

```bash
cat requirements.txt
```

Lista las librerías externas que el proyecto necesita. Lo veremos en detalle en la siguiente sección.

**`main.py`**

```bash
cat main.py
```

Es el punto de entrada del proyecto: el archivo que se ejecuta cuando alguien escribe `python main.py`. Contiene un menú de consola con opciones que se van activando a medida que implementas las funciones en `utils.py`.

> [!TIP]
> **▶ Pausa y piensa:** ¿por qué tiene sentido separar `main.py` (que orquesta) de `src/utils.py` (que implementa)? ¿Qué pasaría si todo estuviera en un solo archivo?

---
### 🔁 Práctica guiada · Git
Antes de instalar nada, guarda el primer registro de que estás aquí. Abre `README.md` en el editor, desplázate al inicio  y agrega en la tabla inicial tu nombre. La línea se ve así:

```
| Participante |  |
```

Guarda con `Ctrl + S`. Luego en la terminal:

#### `git add` · elegir qué entra en el próximo commit

Git no incluye automáticamente todos los cambios en un commit. Primero hay que marcarlos. Eso permite ser selectivo: si cambiaste tres archivos pero solo uno está listo, puedes hacer commit de ese y dejar los otros para después.

```bash
git status          # ver qué archivos cambiaron
```

La salida muestra dos secciones: *Changes to be committed* (listos) y *Changes not staged* (modificados pero no marcados). Luego:

```bash
git add README.md    # agregar solo un archivo específico
git status              # solo README.MD aparece en "to be committed"

git add .               # agregar todo lo que cambió
git status              # ahora todos los archivos están listos
```

#### `git commit` · crear el punto de control

Un commit es una foto del proyecto en un momento dado. El mensaje es la etiqueta de esa foto; si es vago, es muy difícil reconstruir el historial. Por eso la buena práctica de programación es definir commits claros. 

```bash
# Vago: no dice nada útil tres semanas después
git commit -m "cambios"

# Útil: describe qué cambió y dónde
git commit -m "Sesión: participante registrado"
```

Convención del curso: `Sesión: descripción breve`. Para correcciones: `Fix: descripción del error corregido`.

#### `git push` · subir al repositorio remoto

```bash
git push
```

Este comando sube todos los commits locales que GitHub todavía no tiene. Abre tu repositorio en github.com y comprueba que el último commit aparece con el mensaje que escribiste.

#### `git pull` · traer cambios del repositorio remoto

Cuando el instructor actualiza el repositorio base, necesitas traer esos cambios a tu copia:

```bash
git pull
```

Si no hay conflictos, Git descarga y aplica los cambios automáticamente. El caso más frecuente de conflicto en este curso: tú y el instructor modificaron el mismo archivo. En ese caso, avisa al instructor para resolverlo juntos.

#### Resultado esperado

Abre tu repositorio en github.com. Al lado de `README.md` en la lista de archivos deberías ver tu mensaje de commit y la fecha de hace unos segundos.

> Si aparece: el ciclo Git funcionó y ya tienes el flujo grabado en la memoria. Si no aparece: revisa que el `push` no arrojó error y que estás mirando tu repositorio (con tu nombre de usuario en la URL), no el del instructor.

**El flujo completo de una sesión de trabajo es el siguiente:**

```bash
git pull                           # traer cambios antes de empezar
# ... trabajar ...
git add . # Sube todos los archivos modificados. Utilizar solo el nombre en concreto si se quiere subir uno en particular
git commit -m "descripción clara"
git push                           # subir al terminar
```

## Python y sus dependencias

### Qué es pip

Python viene con un gestor de paquetes llamado **pip**. Su trabajo es descargar e instalar librerías desde [PyPI](https://pypi.org), un repositorio público con más de 500.000 paquetes. Cuando escribes `pip install pandas`, pip busca pandas en PyPI, descarga el archivo y lo deja disponible para tus programas.

Verifica que pip está disponible:

```bash
pip --version
```

Deberías ver algo como `pip 25.x from /usr/local/lib/python3.12/...`.

### El archivo `requirements.txt`

`requirements.txt` es el archivo donde se documenta qué librerías necesita el proyecto y en qué versiones. Cuando alguien clona el repositorio en una máquina nueva, ejecuta `pip install -r requirements.txt` y reproduce exactamente el mismo entorno.

Abre `requirements.txt` en el editor. Tiene esta estructura:

```
# Comentario explicativo
nombre_libreria==version_exacta
```

El operador `==` fija la versión exacta. También existen `>=` (mínimo esta versión) y `~=` (compatible con esta versión), pero para este curso usamos `==` para garantizar reproducibilidad: cualquier persona que instale desde este archivo obtendrá exactamente las mismas versiones.

Por ahora el archivo tiene solo dos librerías:

```
pandas==2.3.0
openpyxl==3.2.0
```

`pandas` es la herramienta central para análisis de datos tabulares. `openpyxl` permite leer y escribir archivos Excel; pandas la usa internamente cuando cargas un `.xlsx`.

**Ejercicio de investigación:** antes de instalar, busca en [pypi.org](https://pypi.org) una librería que te parezca útil para el trabajo que haces. Agrégala al final de `requirements.txt` con su versión más reciente. No importa que no la uses todavía: el objetivo es que sepas cómo se agrega una dependencia al proyecto.

### El ambiente virtual

Antes de instalar, hay que crear un **ambiente virtual**. Sin él, las librerías se instalarían en el Python global del sistema, mezclando las dependencias de todos los proyectos.

Imagina que tienes dos proyectos: uno necesita pandas 2.2 y otro requiere pandas 2.3 para funciones nuevas. Si instalas las dos versiones en el Python global, una de las dos va a romper a la otra. El ambiente virtual aísla cada proyecto en su propia copia de Python.

```
Sin ambiente virtual             Con ambiente virtual

Python del sistema               Python del sistema
  └── pandas 2.2  ← conflicto    (limpio)
  └── pandas 2.3
                                  .venv/
                                    └── pandas 2.3  ← solo este proyecto
```

**Crear el ambiente virtual:**

```bash
python -m venv .venv
```

Esto crea la carpeta `.venv/` en el proyecto. El `.gitignore` ya la excluye, así que no se subirá a GitHub.

**Activar el ambiente:**

```bash
# En Codespaces, Mac y Linux:
source .venv/bin/activate
```

El prompt cambia y muestra `(.venv)` al inicio. Esa señal visual confirma que el ambiente está activo.

> [!IMPORTANT]
> **Cada vez que abras una nueva terminal** en Codespaces deberás ejecutar `source .venv/bin/activate` antes de trabajar. Si no lo haces, pip instalará en otro lugar y Python no encontrará las librerías.

**En tu propio computador con Windows:**

```powershell
# PowerShell:
.venv\Scripts\Activate.ps1

# CMD:
.venv\Scripts\activate.bat
```

Si PowerShell muestra un error sobre scripts deshabilitados:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```


> [!IMPORTANT]
> **Cada vez que abras una nueva terminal** debes activar el ambiente antes de trabajar. Si no lo haces, pip instalará en otro lugar y Python no encontrará las librerías del proyecto. Este es el error más frecuente en las primeras sesiones; vale la pena grabarlo.

### Instalar las dependencias

Con el ambiente activo, instala desde el `requirements.txt` que ya tiene tus tres librerías:

```bash
pip install -r requirements.txt
```

El proceso puede tardar 1-2 minutos. pip descarga cada librería y sus dependencias.

**Verificar:**

```bash
pip list | grep -E "pandas|openpyxl"
```

Deberías ver las dos librerías (más la que agregaste) con sus versiones. Si no aparecen, repite la instalación.

---

## 🔁 Segundo ciclo Git

Guardaste el `requirements.txt` con tu librería adicional. Sube eso al repositorio:

```bash
git add requirements.txt
git commit -m "Sesión: requirements.txt actualizado con librería adicional"
git push
```

Verifica en github.com que el archivo en el repositorio ahora incluye tu librería.

## Python como lenguaje

### Un lenguaje interpretado

Python es un lenguaje **interpretado**: el código se ejecuta línea por línea, en tiempo real, sin necesidad de compilarlo primero. Eso tiene como consecuencia que los errores aparecen exactamente en la línea que falla, puedes probar fragmentos directamente en el intérprete interactivo, y el ciclo de prueba es rápido.

Abre el intérprete:

```bash
python
```

El prompt `>>>` indica que Python está esperando instrucciones. Escribe esto:

```python
2 + 2
```

Responde `4` inmediatamente. Ahora escribe:

```python
mensaje = "Procesamiento de datos"
print(mensaje.upper())
```

Sale `PROCESAMIENTO DE DATOS`. El intérprete ejecutó esas dos líneas en el momento. No hubo pasos intermedios.

Sal con `exit()`.

### Reglas de sintaxis a recordar

**Indentación obligatoria.** Python usa el tab para definir bloques de código. No existen llaves `{}` ni palabras clave `begin/end`. Usar 4 espacios es el estándar; usar 3 o 2 también funciona, pero mezclar tamaños en el mismo archivo produce un error.

```python
# Correcto
def saludar(nombre):
    mensaje = f"Hola, {nombre}"
    return mensaje

# Error: IndentationError
def saludar(nombre):
mensaje = f"Hola, {nombre}"  ← sin sangrado → falla
```

**Dos puntos al final de estructuras de bloque.** Todo `def`, `if`, `for`, `while` y `else` termina en `:`.

```python
def calcular(valor):        # ← dos puntos
    if valor > 0:           # ← dos puntos
        return "positivo"   # ← sangrado de 4 espacios
```

**Mayúsculas y minúsculas son distintas.** `nit`, `NIT` y `Nit` son tres variables diferentes. Por convención, las variables y funciones van en minúsculas; las constantes en MAYÚSCULAS.

**Sin punto y coma.** En Python no se usan `;` al final de cada línea (aunque técnicamente Python los acepta). El salto de línea es suficiente.

**Comentarios con `#`.** Todo lo que sigue a `#` en una línea es ignorado por Python.

```python
# Este es un comentario de línea completa
resultado = valor * tasa  # este comentario explica la línea
```

### El estándar PEP 8

PEP 8 es la guía de estilo oficial de Python. Seguirla hace que cualquier desarrollador Python pueda leer tu código sin esfuerzo adicional.

| Elemento | Convención | Ejemplo |
|----------|-----------|---------|
| Variables y funciones | `snake_case` | `valor_declarado`, `calcular_iva` |
| Constantes | `MAYUSCULAS` | `TASA_IVA`, `ESTADOS_VALIDOS` |
| Módulos y archivos | `snake_case` | `data_loader.py`, `utils.py` |
| Sangrado | 4 espacios | (no tabs) |
| Líneas | máximo 79 caracteres | |
| Líneas entre funciones | 2 líneas en blanco | |

En este curso seguimos PEP 8 en todo el código.

---

## El menú principal

Abre `main.py` en el editor. Ya tiene un menú funcional con siete opciones y una estructura `while` que mantiene el programa corriendo hasta que el usuario elige salir.

Ejecútalo ahora para ver cómo se ve:

```bash
python main.py
```

Verás el menú impreso y podrás escribir un número. La mayoría de opciones dice `(función pendiente de implementar)`. A medida que escribas cada función en `utils.py` y la importes en `main.py`, irás descomentando las líneas correspondientes en `ejecutar_opcion()` y la opción empezará a funcionar.

`main.py` no cambia de estructura, más bien incrementa en las llamadas activas a funciones o procedimientos. En el archivo `utils.py` es donde está la lógica. Esto permite hacer una mejor separación de responsabilidades

> Revisa la función `ejecutar_opcion()` en `main.py`. Cada bloque `elif` tiene el código comentado con `# TODO`. Cuando implementes la función correspondiente, descomentas esas líneas y la opción del menú puede ser utilizada.

> TODO significa “por hacer”. En programación se usa como una marca dentro del código para señalar una tarea pendiente.

En Python suele escribirse como comentario:

```python
# TODO: conectar esta opción cuando la función esté implementada
```

Python ignora esa línea porque empieza con `#`, pero la persona que lee el código entiende que allí falta completar algo.

En este proyecto, los `# TODO` indican opciones del menú que ya están planeadas, pero que todavía dependen de funciones que vas a escribir en `utils.py`. Cuando la función esté lista, podrás descomentar las líneas correspondientes y probar la opción desde `main.py`.

Usar `TODO` ayuda a trabajar por etapas: primero se deja preparada la estructura general y luego se completa la lógica paso a paso.

---

## Funciones y procedimientos

Una **función** recibe datos, hace un cálculo y retorna un resultado. Un **procedimiento** ejecuta una acción (imprimir, guardar) y no retorna nada útil. La distinción importa al diseñar código porque si algo calcula, debe retornar; si algo muestra o guarda, no necesita retornar.

Hunt y Thomas, en *The Pragmatic Programmer* (2019), resumen este principio como DRY (*Don't Repeat Yourself*): cada pieza de conocimiento debe tener una representación única. Una función con nombre bien elegido es esa representación.

```python
# Función: calcula y retorna
def calcular_iva(valor_base, tasa=0.19):
    """
    Calcula el IVA sobre un valor base.

    Args:
        valor_base (float): Monto antes de impuestos.
        tasa (float): Tasa de IVA. Por defecto 0.19.

    Returns:
        float: Valor del IVA.
    """
    return valor_base * tasa


# Procedimiento: ejecuta una acción, no retorna nada útil
def mostrar_resultado(etiqueta, valor):
    """Imprime un resultado con formato."""
    print(f"  {etiqueta}: ${valor:,.0f}")


# Uso
iva = calcular_iva(1_000_000)
mostrar_resultado("IVA calculado", iva)
# IVA calculado: $190,000
```

El bloque entre comillas triples justo debajo de `def` es el **docstring**: la documentación de la función. VS Code lo muestra como tooltip cuando empiezas a escribir el nombre de la función en otro lugar del código. Martin, en *Clean Code* (2008), explica que el código bueno se lee como prosa; el docstring es el párrafo introductorio.

### Ejercicio básico · `calcular_iva` (~10 min)

Contexto: el área necesita calcular el IVA de una declaración. El resultado es un único valor numérico que se usará en reportes y en el menú del sistema.

Escribe `calcular_iva(valor_base, tasa=0.19)` en `src/utils.py`. Retorna el valor del IVA como `float`.

Salida esperada:
```
calcular_iva(1_000_000)        -> 190000.0
calcular_iva(1_000_000, 0.05)  -> 50000.0
calcular_iva(0)                -> 0.0
```

Una vez implementada, descomenta la opción 1 del menú en `main.py`.

### Ejercicio intermedio · `formatear_reporte_valor` (~12 min)

Contexto: el sistema genera líneas de texto para informes de seguimiento. Cada línea resume un registro en una sola cadena legible.

Escribe `formatear_reporte_valor(nit, nombre, valor, estado)`. Retorna una cadena de texto (`str`) con este formato:

```
NIT 900123456 | Empresa ABC S.A.S. | $1,500,000 | ACTIVO
```

El valor debe mostrarse con separadores de miles usando `:,` en el f-string. Ningún parámetro del retorno es un diccionario.

Salida esperada para `("900123456", "Empresa ABC S.A.S.", 1_500_000, "ACTIVO")`:
```
NIT 900123456 | Empresa ABC S.A.S. | $1,500,000 | ACTIVO
```

### Ejercicio avanzado · `generar_ficha_contribuyente` (~20 min)

Contexto: el sistema genera fichas formales para imprimir o enviar por correo.

Escribe `generar_ficha_contribuyente(nit, nombre, municipio, periodo, valor, estado)`. Recibe seis parámetros  y retorna una cadena de texto multilínea con este formato:

```
╔══════════════════════════════════════╗
║  FICHA DE CONTRIBUYENTE              ║
╠══════════════════════════════════════╣
  NIT        : 900123456
  Nombre     : EMPRESA ABC S.A.S.
  Municipio  : BOGOTA
  Periodo    : 202401
  Valor      : $1,500,000
  Estado     : ACTIVO
╚══════════════════════════════════════╝
```

El nombre y el municipio van en mayúsculas. Usa `nombre.upper()` y `municipio.upper()` directamente dentro de la función. Todos los valores llegan como parámetros.

Una vez implementada, descomenta la opción 4 del menú en `main.py` 

---

## Encadenamiento de funciones

Encadenar funciones es pasar el resultado de una como argumento de otra. Tiene dos formas en Python: composición explícita y encadenamiento de métodos.

### Composición explícita

```python
def limpiar_nit(nit):
    """Elimina guiones y puntos de un NIT."""
    sin_guiones = nit.replace("-", "")
    sin_puntos = sin_guiones.replace(".", "")
    return sin_puntos


def validar_longitud(nit_limpio):
    """Verifica que el NIT tenga entre 9 y 10 caracteres."""
    longitud = len(nit_limpio)
    return longitud >= 9 and longitud <= 10


def validar_nit(nit):
    """Valida un NIT completo: limpia y luego verifica longitud y dígitos."""
    nit_limpio = limpiar_nit(nit)           # ← llama a la primera
    es_longitud_valida = validar_longitud(nit_limpio)   # ← usa su resultado
    solo_digitos = nit_limpio.isdigit()
    return es_longitud_valida and solo_digitos
```

Cada función hace una sola cosa. `validar_nit` llama a las otras dos y combina sus resultados. Si la regla de longitud cambia, solo hay que modificar `validar_longitud`.  Permitiendo que cada función sea responsable de una sola cosa puede se facilita la mantenibilidad del código fuente y se favorece la reutilización.

### Encadenamiento de métodos

Python permite encadenar llamadas a métodos directamente sobre el resultado anterior, sin variables intermedias:

```python
def normalizar_nombre(nombre):
    """Limpia y normaliza un nombre para comparación."""
    return nombre.strip().upper().replace("  ", " ")


# Es equivalente a:
def normalizar_nombre_paso_a_paso(nombre):
    sin_espacios = nombre.strip()
    en_mayusculas = sin_espacios.upper()
    sin_dobles = en_mayusculas.replace("  ", " ")
    return sin_dobles
```

Ambas versiones producen el mismo resultado. La primera es más compacta; la segunda, más fácil de depurar paso a paso. Para quien empieza, la segunda forma suele ser más clara porque permite inspeccionar cada paso.

### Ejercicio básico · `procesar_nit` 

Escribe `procesar_nit(nit)` que encadena `limpiar_nit()` y `validar_nit()`. Retorna una cadena de texto (`str`) con el resultado:

Salida esperada:
```
procesar_nit("900-123-456")  ->  "NIT 900123456: válido"
procesar_nit("ABC-123")      ->  "NIT ABC123: INVÁLIDO"
procesar_nit("123")          ->  "NIT 123: INVÁLIDO"
```

La función llama a `limpiar_nit()` primero, luego pasa el resultado a `validar_nit()`, y construye el mensaje según el resultado booleano.

### Ejercicio intermedio · `normalizar_texto` 

Encadenar métodos sobre una cadena permite limpiar datos de texto en una sola expresión. Escribe `normalizar_texto(texto)` que aplique en cadena: `.strip()`, `.upper()` y `.replace("  ", " ")` para eliminar espacios extra internos.

Salida esperada:
```
normalizar_texto("  bogotá d.c.  ")   ->  "BOGOTÁ D.C."
normalizar_texto("  empresa  abc  ")  ->  "EMPRESA ABC"
normalizar_texto("CALI")              ->  "CALI"
```

### Ejercicio avanzado · `pipeline_nit` 

Escribe `pipeline_nit(nit)` que encadena tres operaciones sobre un NIT y retorna un informe como `str`. Las operaciones en orden: (1) limpiar con `limpiar_nit()`, (2) validar con `validar_nit()`, (3) si es válido, formatearlo con `f"NIT {nit_limpio} — apto para procesamiento"`; si no, `f"NIT {nit_original} — rechazado: formato inválido"`.

Salida esperada:
```
pipeline_nit("900-123-456")  ->  "NIT 900123456 — apto para procesamiento"
pipeline_nit("ABC-123")      ->  "NIT ABC-123 — rechazado: formato inválido"
```

---

## 🔁 Ciclo Git · bloque 1

Haz commit al repositorio de los cambios que llevas

```bash
git add src/utils.py main.py
git commit -m "Sesión: funciones y encadenamiento implementados"
git push
```

---

## Condicionales simples

Un condicional simple evalúa una condición y ejecuta un bloque u otro. Tiene dos caminos posibles.

```python
def requiere_revision(valor):
    """
    Determina si una declaración requiere revisión por valor alto.

    Args:
        valor (float): Valor declarado.

    Returns:
        bool: True si supera el umbral de revisión.
    """
    umbral = 2_000_000

    if valor > umbral:
        return True
    else:
        return False
```

> [!TIP]
> **▶ Pausa y piensa:** esta función puede escribirse en una sola línea como `return valor > umbral`. ¿Por qué para efectos de aprendizaje conviene escribir el `if/else` explícito?

### Ejercicio básico · `esta_al_dia` 

Escribe `esta_al_dia(dias_mora)`. Retorna `True` si `dias_mora` es 0, `False` en cualquier otro caso.

Salida esperada con `[0, 1, 30, -5]`:
```
0 dias: True
1 dias: False
30 dias: False
-5 dias: False
```

### Ejercicio intermedio · `aplicar_descuento` 

Contexto: los contribuyentes que pagan voluntariamente antes de ser notificados reciben un descuento del 10 %.

Escribe `aplicar_descuento(valor, pago_voluntario)`. Si `pago_voluntario` es `True`, retorna el valor con el 10 % de descuento. Si no, retorna el valor original.

Salida esperada con `(1_000_000, True)` y `(1_000_000, False)`:
```
Con descuento  : $900,000
Sin descuento  : $1,000,000
```

### Ejercicio avanzado · `asignar_prioridad` 

Contexto: el sistema de seguimiento asigna prioridad de atención según el valor declarado y si el contribuyente tiene historial de incumplimiento.

Escribe `asignar_prioridad(valor, tiene_historial_incumplimiento)`. Retorna `"ALTA"` si el valor supera 1.000.000 Y tiene historial, `"MEDIA"` si solo cumple una de las dos condiciones, y `"BAJA"` si no cumple ninguna.

---

## Condicionales anidados

Un condicional anidado coloca un `if` dentro de otro. Se usa cuando la segunda condición solo tiene sentido si la primera es verdadera.

```python
def evaluar_pago(estado, valor):
    """
    Evalúa si un registro está en orden según su estado y valor.

    Args:
        estado (str): Estado del registro.
        valor (float): Valor declarado.

    Returns:
        str: Resultado de la evaluación.
    """
    if estado == "ACTIVO":
        if valor >= 100_000:
            return "En regla"
        else:
            return "Activo con valor insuficiente"
    elif estado == "INACTIVO":
        return "Registro inactivo"
    else:
        return "Requiere revisión manual"
```

Conviene limitar el anidamiento a dos niveles. Cuando hay más de dos niveles, el código se vuelve difícil de seguir y casi siempre puede reescribirse de forma más clara.

### Ejercicio básico · `clasificar_mora` 

Escribe `clasificar_mora(dias_mora, valor)`. Primero verifica si hay mora (dias_mora > 0). Si hay mora, clasifica según si el valor es mayor o menor a 500.000: `"Mora alta"` o `"Mora baja"`. Si no hay mora: `"Sin mora"`.

### Ejercicio intermedio · `determinar_tipo_seguimiento` 

Escribe `determinar_tipo_seguimiento(estado, valor, municipio)`. Si el estado es `ACTIVO`: si el municipio es `"Bogota"` o `"Medellin"` y el valor supera 2.000.000 → `"Seguimiento prioritario"`; de lo contrario → `"Seguimiento estándar"`. Si el estado es `PENDIENTE` → `"Seguimiento urgente"`. Cualquier otro estado → `"Sin seguimiento"`.

### Ejercicio avanzado · `evaluar_cumplimiento` 

Escribe `evaluar_cumplimiento(estado, valor, dias_mora, historial)`. Aplica reglas de negocio que cruzan las cuatro variables para producir una de estas categorías: `"Cumplimiento total"`, `"Incumplimiento leve"`, `"Incumplimiento grave"` o `"Caso crítico"`. Define tú mismo las reglas, pero deben cruzar al menos dos variables en cada nivel.

---

## Condicionales encadenados

Cuando hay más de dos posibilidades, los bloques `elif` evitan anidar. Solo se ejecuta el primero cuya condición sea verdadera; los demás se ignoran.

```python
def clasificar_contribuyente(valor):
    """
    Clasifica al contribuyente según su valor declarado.

    Categorías:
        GRANDE      : más de 5.000.000
        MEDIANO     : entre 1.000.001 y 5.000.000
        PEQUEÑO     : entre 100.001 y 1.000.000
        MÍNIMO      : entre 1 y 100.000
        SIN VALOR   : 0

    Args:
        valor (float): Valor declarado.

    Returns:
        str: Categoría del contribuyente.
    """
    if valor > 5_000_000:
        return "GRANDE"
    elif valor > 1_000_000:
        return "MEDIANO"
    elif valor > 100_000:
        return "PEQUEÑO"
    elif valor > 0:
        return "MÍNIMO"
    else:
        return "SIN VALOR"
```

### Ejercicio básico · `describir_periodo` 

Escribe `describir_periodo(periodo)`. Recibe una cadena en formato `YYYYMM` y retorna una descripción: si el mes está entre 1 y 3 → `"Primer trimestre"`, 4-6 → `"Segundo trimestre"`, 7-9 → `"Tercer trimestre"`, 10-12 → `"Cuarto trimestre"`. Para períodos con formato inválido → `"Período no reconocido"`.

### Ejercicio intermedio · `calcular_sancion_basica` 

Escribe `calcular_sancion_basica(dias_mora, valor_base)`. Aplica tasas de sanción según el atraso: 0 días → 0 %, 1-30 → 1 %, 31-60 → 3 %, 61-90 → 5 %, más de 90 → 10 %. Retorna el valor de la sanción calculada.

### Ejercicio avanzado · `priorizar_cobro` 

Escribe `priorizar_cobro(valor, dias_mora, tipo_contribuyente)`. `tipo_contribuyente` puede ser `"GRANDE"`, `"MEDIANO"` o `"PEQUEÑO"`. Combina las tres variables con `elif` para asignar una de cinco prioridades de cobro (`P1` a `P5`). Define las reglas con criterio: un contribuyente grande con mora alta debe ser `P1`; un pequeño con pocos días de atraso puede ser `P4` o `P5`.

---

## 🔁 Ciclo Git · bloque 2
Haz commit al repositorio de los cambios que llevas

```bash
git add src/utils.py
git commit -m "Sesión: condicionales simples, anidados y encadenados"
git push
```

---

## Ciclos con repetición definida · for

Un ciclo `for` recorre cada elemento de una colección, uno por uno, en orden. El número de iteraciones queda determinado por el tamaño de la colección desde el principio.

```python
def imprimir_nits(nits):
    """Imprime una lista de NITs numerados."""
    for i, nit in enumerate(nits, start=1):
        print(f"  {i}. {nit}")


def generar_periodos(anio, cantidad):
    """
    Genera códigos de período para un año dado.

    Args:
        anio (int): Año de los períodos.
        cantidad (int): Número de períodos a generar.

    Returns:
        list: Lista de códigos en formato YYYYMM.
    """
    periodos = []
    for mes in range(1, cantidad + 1):
        codigo = f"{anio}{mes:02d}"
        periodos.append(codigo)
    return periodos
```

`range(1, cantidad + 1)` genera los enteros del 1 al `cantidad` inclusive. El `:02d` formatea el mes con cero a la izquierda.

Los ejercicios de esta sección trabajan con listas de cadenas de texto (`str`) y números (`float`). 

### Ejercicio básico · `imprimir_nits_validos` 

Contexto: el sistema recibe una lista de NITs y necesita imprimir solo los que tienen formato válido, numerados desde 1.

Escribe `imprimir_nits_validos(nits)`. Recorre la lista, llama `validar_nit()` para cada elemento e imprime solo los válidos con su número de posición.

```python
nits_prueba = ["900123456", "ABC123", "800234567", "123", "700345678"]
imprimir_nits_validos(nits_prueba)
```

Salida esperada:
```
NITs válidos:
  1. 900123456
  2. 800234567
  3. 700345678
```

### Ejercicio intermedio · `calcular_totales` 

Contexto: el área recibe una lista de valores declarados y necesita calcular el total, el promedio y el máximo.

Escribe `calcular_totales(valores)`. Recibe una lista de `float` y retorna tres valores por separado (no en diccionario): `total`, `promedio` y `maximo`. Usa acumuladores y un ciclo `for`; no uses `sum()`, `max()` ni `statistics`.

```python
valores = [1_500_000, 850_000, 0, 2_300_000, 950_000, 3_200_000, 450_000, 1_100_000]
total, promedio, maximo = calcular_totales(valores)
```

Salida esperada:
```
Total  : $10,350,000
Promedio: $1,293,750
Máximo : $3,200,000
```

### Ejercicio avanzado · `generar_periodos_multiple` 

Contexto: el sistema necesita generar los códigos de período para varios años consecutivos, en una sola lista.

Escribe `generar_periodos_multiple(anio_inicio, anio_fin, meses_por_anio=12)`. Usa un `for` externo para los años y un `for` interno (`range`) para los meses. Retorna una lista de cadenas en formato `YYYYMM`.

Salida esperada con `(2024, 2025, 3)`:
```
['202401', '202402', '202403', '202501', '202502', '202503']
```

---

## Ciclos con repetición indefinida · while

Un ciclo `while` repite un bloque mientras una condición sea verdadera. El número de iteraciones no se conoce de antemano. Siempre debe existir algo dentro del ciclo que eventualmente haga la condición falsa; si no, el ciclo corre para siempre.

```python
def buscar_primer_valido(nits):
    """
    Busca el primer NIT válido en una lista de cadenas.

    Args:
        nits (list): Lista de NITs como cadenas de texto.

    Returns:
        str | None: El primer NIT válido encontrado, o None si no hay ninguno.
    """
    indice = 0
    while indice < len(nits):
        nit = nits[indice]
        if validar_nit(nit):
            return nit
        indice = indice + 1
    return None
```

Los ejercicios de esta sección trabajan con listas de cadenas y números, igual que los del ciclo `for`.

### Ejercicio básico · `sumar_hasta_limite` (~10 min)

Escribe `sumar_hasta_limite(valores, limite)`. Recibe una lista de `float` y acumula valores mientras el total no supere el límite. Retorna una tupla `(cantidad_procesada, total_acumulado)`.

```python
valores = [1_500_000, 850_000, 2_300_000, 950_000, 450_000]
cantidad, total = sumar_hasta_limite(valores, 3_000_000)
```

Salida esperada:
```
Procesados: 2 valores
Total: $2,350,000
```

### Ejercicio intermedio · `encontrar_primer_sobre_umbral` 

Escribe `encontrar_primer_sobre_umbral(valores, umbral)`. Recorre la lista con `while` y retorna el primer valor que supere el umbral. Si ninguno lo supera, retorna `None`.

```python
valores = [850_000, 950_000, 2_300_000, 1_100_000]
encontrar_primer_sobre_umbral(valores, 2_000_000)  # -> 2300000
encontrar_primer_sobre_umbral(valores, 5_000_000)  # -> None
```

### Ejercicio avanzado · `validar_secuencia_periodos` 

Escribe `validar_secuencia_periodos(periodos)`. Recibe una lista de códigos de período y verifica con `while` que estén en orden consecutivo (sin saltos de mes). Retorna `True` si la secuencia es válida, `False` si hay un salto, y el índice donde ocurrió el salto.

---

## 🔁 Ciclo Git · bloque 3
Haz commit al repositorio de los cambios que llevas
```bash
git add src/utils.py main.py
git commit -m "Sesión: ciclos for y while implementados"
git push
```

---

## Listas

Una lista guarda elementos en orden y se accede por posición (empezando en 0). Se puede agregar, eliminar y buscar elementos.

```python
def obtener_estados_unicos(declaraciones):
    """
    Extrae los estados que aparecen en la lista sin repetirlos.

    Args:
        declaraciones (list): Lista de declaraciones.

    Returns:
        list: Estados únicos en orden de primera aparición.
    """
    estados = []
    for declaracion in declaraciones:
        estado = declaracion["estado"]
        if estado not in estados:
            estados.append(estado)
    return estados


def agregar_si_no_existe(lista, elemento):
    """Agrega un elemento a la lista solo si no está ya."""
    if elemento not in lista:
        lista.append(elemento)
    return lista
```

Operaciones más usadas:

```python
mi_lista = ["ACTIVO", "INACTIVO", "PENDIENTE"]

mi_lista.append("SUSPENDIDO")      # agregar al final
mi_lista.remove("INACTIVO")        # eliminar por valor
mi_lista[0]                        # acceder por posición
len(mi_lista)                      # longitud
"ACTIVO" in mi_lista               # verificar existencia
mi_lista.sort()                    # ordenar (modifica la lista)
```

### Ejercicio básico · `agregar_unico`

Contexto: el sistema construye una lista de estados presentes en un lote de registros, sin repetidos.

Escribe `agregar_unico(lista, elemento)`. Si el elemento ya está en la lista, la retorna sin cambios. Si no está, lo agrega y retorna la lista actualizada.

```python
estados = ["ACTIVO", "INACTIVO"]
estados = agregar_unico(estados, "PENDIENTE")   # agrega
estados = agregar_unico(estados, "ACTIVO")      # no agrega, ya existe
print(estados)
```

Salida esperada:
```
['ACTIVO', 'INACTIVO', 'PENDIENTE']
```

### Ejercicio intermedio · `filtrar_valores_en_rango`

Contexto: el área necesita quedarse solo con los valores que caen dentro de un rango para un análisis focalizado.

Escribe `filtrar_valores_en_rango(valores, minimo, maximo)`. Recibe una lista de `float` y retorna una nueva lista con solo los valores entre `minimo` y `maximo` inclusive. La lista original no debe modificarse.

```python
valores = [1_500_000, 850_000, 0, 2_300_000, 950_000, 450_000, 1_100_000]
filtrar_valores_en_rango(valores, 500_000, 1_200_000)
```

Salida esperada:
```
[850000, 950000, 1100000]
```

### Ejercicio avanzado · `ordenar_valores` 

Escribe `ordenar_valores(valores, descendente=True)`. Recibe una lista de `float` y retorna una nueva lista ordenada. Implementa el ordenamiento ( requieres dos ciclos anidados) (sin usar `.sort()` ni `sorted()`). Al terminar, verifica que el resultado coincide con `sorted(valores, reverse=descendente)`.

```python
valores = [1_500_000, 850_000, 2_300_000, 450_000, 1_100_000]
ordenar_valores(valores, descendente=True)
```

Salida esperada:
```
[2300000, 1500000, 1100000, 850000, 450000]
```

---

## Diccionarios

### DECLARACIONES: una lista de diccionarios

Hasta aquí todos los ejercicios trabajaron con listas de cadenas o números. Es el momento de presentar la estructura de datos principal del curso.

Abre `src/utils.py` y mira la constante `DECLARACIONES`. Es una **lista de diccionarios**: cada elemento es un diccionario que representa un registro de declaración tributaria con seis campos fijos.

```python
DECLARACIONES[0]
# {
#   "nit":      "900123456",
#   "nombre":   "Empresa ABC S.A.S.",
#   "municipio": "Bogota",
#   "periodo":  "202401",
#   "valor":    1_500_000,
#   "estado":   "ACTIVO"
# }
```

Para acceder a un campo de un elemento de la lista:

```python
primer_registro = DECLARACIONES[0]
nit = primer_registro["nit"]         # "900123456"
valor = primer_registro["valor"]     # 1500000
```

O en una sola línea:

```python
nit = DECLARACIONES[0]["nit"]
```

Y para recorrer todos los registros:

```python
for declaracion in DECLARACIONES:
    print(declaracion["nit"], declaracion["estado"])
```

Con eso en mente, un diccionario guarda pares clave-valor. Las claves deben ser únicas; los valores pueden ser cualquier tipo, incluyendo listas u otros diccionarios.

```python
def construir_registro(nit, nombre, municipio, periodo, valor, estado):
    """
    Construye un diccionario de declaración con los campos estándar.

    Args:
        nit (str): NIT del contribuyente.
        nombre (str): Nombre o razón social.
        municipio (str): Municipio de registro.
        periodo (str): Período en formato YYYYMM.
        valor (float): Valor declarado.
        estado (str): Estado del registro.

    Returns:
        dict: Registro estructurado.
    """
    return {
        "nit":       nit,
        "nombre":    nombre,
        "municipio": municipio,
        "periodo":   periodo,
        "valor":     valor,
        "estado":    estado,
    }


def actualizar_estado(registro, nuevo_estado):
    """Retorna una copia del registro con el estado actualizado."""
    registro_actualizado = dict(registro)
    registro_actualizado["estado"] = nuevo_estado
    return registro_actualizado
```

Para iterar sobre un diccionario:

```python
registro = {"nit": "900123456", "estado": "ACTIVO"}

for clave, valor in registro.items():
    print(f"{clave}: {valor}")
```

### Ejercicio básico · `indexar_por_nit` 

Escribe `indexar_por_nit(declaraciones)`. Retorna un diccionario donde cada clave es un NIT y el valor es el diccionario completo del registro. Permite buscar un registro directamente por NIT sin recorrer toda la lista.

Uso esperado:
```python
indice = indexar_por_nit(DECLARACIONES)
print(indice["600456789"]["nombre"])  # Industrias PQR S.A.
```

### Ejercicio intermedio · `construir_resumen_por_estado` (~15 min)

Escribe `construir_resumen_por_estado(declaraciones)`. Retorna un diccionario donde cada clave es un estado y el valor es otro diccionario con `conteo` y `total_valor`.

Salida esperada con `DECLARACIONES`:
```python
{
  'ACTIVO':     {'conteo': 5, 'total_valor': 9150000},
  'INACTIVO':   {'conteo': 1, 'total_valor': 0},
  'PENDIENTE':  {'conteo': 1, 'total_valor': 950000},
  'SUSPENDIDO': {'conteo': 1, 'total_valor': 450000}
}
```

### Ejercicio avanzado · `agrupar_por_municipio` (~20 min)

Escribe `agrupar_por_municipio(declaraciones)`. Retorna un diccionario donde cada clave es un municipio y el valor es una lista con todos los registros de ese municipio. Luego escribe una segunda función `imprimir_agrupacion(agrupacion)` que reciba el resultado e imprima un resumen formateado por municipio.

---

## 🔁 Ciclo Git · bloque 4

```bash
git add src/utils.py
git commit -m "Sesión: listas y diccionarios implementados"
git push
```

---

## Menús de consola

Abre `main.py` en el editor. Este archivo es el punto de entrada del proyecto: es el archivo que se ejecuta cuando escribes:

```bash
python main.py
```

El programa ya tiene un menú funcional. Aunque varias opciones todavía no hacen el procesamiento completo, la estructura general ya está lista. Esto permite que durante la sesión vayas activando cada opción a medida que implementas las funciones en `src/utils.py`.

El archivo `main.py` está organizado en tres partes:

| Parte                     | Qué hace                                                           |
| ------------------------- | ------------------------------------------------------------------ |
| `mostrar_menu()`          | Imprime en pantalla las opciones disponibles.                      |
| `ejecutar_opcion(opcion)` | Recibe la opción elegida y decide qué acción ejecutar.             |
| `main()`                  | Mantiene el programa funcionando hasta que el usuario elige salir. |

La función `mostrar_menu()` solo se encarga de mostrar texto. Allí están las opciones que ve el usuario: calcular IVA, validar un NIT, clasificar un valor, buscar una declaración, ver estadísticas o salir.

La función `ejecutar_opcion(opcion)` recibe el número escrito por el usuario. Luego usa una estructura `if`, `elif`, `else` para decidir qué bloque de código ejecutar. Por ejemplo, si el usuario escribe `"1"`, se ejecuta el bloque de la opción 1; si escribe `"2"`, se ejecuta el bloque de la opción 2.

La función `main()` controla el ciclo del programa. Primero muestra el menú, luego pide una opción, después llama a `ejecutar_opcion(opcion)`. Ese ciclo se repite mientras la opción sea distinta de `"0"`.

```python
opcion = ""
while opcion != "0":
    mostrar_menu()
    opcion = input("  Seleccione una opción: ").strip()
    ejecutar_opcion(opcion)
```

Esto significa que el programa no termina después de una sola acción. Vuelve a mostrar el menú una y otra vez hasta que el usuario selecciona `0`.

### Cómo se conecta `main.py` con `utils.py`

En este proyecto, `main.py` coordina el flujo del programa, pero la lógica de procesamiento se escribe en `src/utils.py`.

Por ejemplo, `main.py` puede pedir un NIT al usuario y mostrar el resultado, pero la validación del NIT debe estar en una función de `utils.py`. Esa separación permite que el código sea más fácil de leer, probar y reutilizar.

```text
main.py
  → muestra el menú
  → pide datos al usuario
  → llama funciones

src/utils.py
  → contiene las funciones que procesan datos
  → valida, calcula, filtra, clasifica o resume información
```

### Qué significa `TODO` en este archivo

Varias opciones del menú tienen líneas comentadas con `# TODO`. `TODO` significa “por hacer” y se usa para marcar partes del código que todavía deben completarse.

En este caso, los `TODO` indican que la opción del menú ya está preparada, pero falta implementar la función correspondiente en `src/utils.py`.

Por ejemplo, una opción puede verse así:

```python
# TODO: descomentar cuando implementes validar_nit
# from src.utils import validar_nit
# nit = input("  Ingrese el NIT: ").strip()
# es_valido = validar_nit(nit)
print("  (función pendiente: validar_nit)")
```

Mientras la función no exista, el programa muestra un mensaje de función pendiente. Cuando implementes `validar_nit` en `src/utils.py`, podrás descomentar las líneas necesarias y quitar o reemplazar el mensaje temporal.

El trabajo seguirá este ciclo:

```text
1. Escribes una función en src/utils.py.
2. Vuelves a main.py.
3. Descomentas el bloque de la opción correspondiente.
4. Importas la función dentro de ejecutar_opcion().
5. Ejecutas python main.py y pruebas la opción.
```

Así el menú va creciendo poco a poco. La estructura principal permanece igual; lo que cambia es que cada opción empieza a llamar funciones que ya fueron implementadas.


---

## Documentación

El código bien documentado permite que otra persona (o tú mismo seis meses después) entienda qué hace cada función sin tener que leerla línea por línea.

### Docstrings

Ya los has visto en todos los ejemplos. El estándar del curso es el formato Google:

```python
def funcion(parametro_uno, parametro_dos):
    """
    Una línea que describe qué hace la función.

    Párrafo opcional con más contexto cuando es necesario.

    Args:
        parametro_uno (tipo): Descripción.
        parametro_dos (tipo): Descripción.

    Returns:
        tipo: Descripción de lo que retorna.

    Raises:
        TipoError: Cuando ocurre esta condición.
    """
```

### Comentarios en línea

Un comentario en línea explica el **por qué**, no el **qué**. El código ya dice qué hace; el comentario agrega contexto que el código no puede expresar.

```python
# Mal comentario: repite lo que el código ya dice
indice = indice + 1  # incrementa indice en 1

# Buen comentario: explica por qué se hace así
indice = indice + 1  # avanzamos aunque no haya coincidencia para evitar ciclo infinito
```

### Ejercicio de documentación 

Revisa las funciones que escribiste en `src/utils.py`. Identifica al menos tres que tengan docstrings incompletos o comentarios que expliquen el qué en lugar del por qué. Corrígelos. Luego escribe el docstring del módulo completo al inicio del archivo:

```python
"""
utils.py - Funciones de utilidad del proyecto de análisis de declaraciones.

Este módulo contiene las funciones desarrolladas durante la Sesión 1 del curso
Python Intermedio para Análisis de Datos - DIAN 2026.

Autora/Autor: [Tu nombre]
Fecha: [Fecha de la sesión]
"""
```

---

## 🔁 Ciclo Git · cierre

Commit final de la sesión:

```bash
git add .
git commit -m "Sesión: sesión completa - entorno, dependencias y fundamentos Python"
git push
```

Verifica en github.com que tu repositorio tiene el historial de commits del día. A partir del tablero del github classroom puedo revisar ese historial como evidencia del trabajo realizado.

---

## Banco de ejercicios adicional

Esta sección contiene ejercicios adicionales para quienes terminan antes o quieren practicar más después de la sesión. Todos usan la constante `DECLARACIONES` de `src/utils.py`.

Agrega estos ejercicios como funciones adicionales en `src/utils.py` y llámalas desde `main.py` cuando quieras probarlas.

### Variables bandera

Una variable bandera es un booleano que empieza en `False` y cambia a `True` cuando ocurre algo específico dentro de un ciclo.

**Ejercicio:** `existe_sin_valor(declaraciones)` → retorna `True` si al menos un registro tiene `valor == 0`. Usa una bandera y `break` para detener la búsqueda en cuanto la encuentres.

**Ejercicio:** `todos_tienen_nit_valido(declaraciones)` → retorna `True` solo si todos los registros tienen NIT válido. La bandera empieza en `True` y cambia a `False` en cuanto encuentres uno inválido.

### Acumuladores y contadores

**Ejercicio:** `calcular_total_por_estado(declaraciones, estado)` → suma los valores solo de los registros con el estado indicado.

**Ejercicio:** `construir_lista_nombres(declaraciones)` → acumula los nombres en una cadena separada por ` / `. La cadena no debe terminar con ` / `.

### Ciclos anidados

**Ejercicio:** `encontrar_nits_comunes(lista_a, lista_b)` → encuentra los NITs que aparecen en ambas listas. Usa dos ciclos `for` anidados.

**Ejercicio:** `generar_combinaciones(municipios, estados)` → genera todas las combinaciones posibles como pares de cadenas. Usa ciclos anidados.

---
## Organización de código - del notebook al proyecto: ordenar para poder reutilizar

En un notebook es común escribir una celda, ejecutarla, ver el resultado y seguir con la siguiente. Ese flujo es cómodo para explorar: permite probar una idea, revisar una tabla, graficar una columna o confirmar rápidamente si una transformación funciona.

Cuando el trabajo empieza a repetirse, ese mismo flujo comienza a mostrar límites. Un análisis de datos no suele terminar en una sola ejecución. Los archivos cambian, llegan nuevas versiones, aparecen errores, se piden ajustes y otra persona necesita entender qué se hizo. En ese momento, el código deja de ser una prueba aislada y se convierte en un proceso que debe poder repetirse.

Piensa en una base de declaraciones. Primero llega un archivo CSV. Luego llega una versión corregida. Después alguien pide filtrar solo ciertos períodos, guardar un resumen por municipio y generar una salida para revisar. Si todo está en un notebook, mezclado con pruebas, gráficos temporales, celdas ejecutadas en distinto orden y archivos guardados en cualquier carpeta, reconstruir el proceso se vuelve difícil.

En un proyecto organizado, cada cosa tiene un lugar:

```text
data/input/     archivos que entran al proceso
data/output/    archivos generados por el proceso
src/            funciones reutilizables
main.py         punto de entrada para ejecutar el proyecto
requirements.txt librerías necesarias
README.md       instrucciones para usar el proyecto
```

La carpeta `data/input/` guarda los archivos de entrada. Allí deben estar los datos originales o los archivos que el programa necesita leer. La carpeta `data/output/` guarda los resultados: archivos limpios, resúmenes, reportes o exportaciones. Esta separación evita sobrescribir por accidente un archivo original y permite saber qué produjo el código.

La carpeta `src/` contiene funciones. Una función bien escrita puede usarse muchas veces: desde `main.py`, desde una prueba, desde otro archivo o incluso desde un notebook. Por ejemplo, una función para limpiar nombres de columnas puede aplicarse hoy sobre una base pequeña y mañana sobre una base más grande sin volver a escribir la lógica.

`main.py` cumple otro papel: coordina la ejecución. Allí no debería quedar todo el detalle del procesamiento. Su trabajo es llamar funciones, organizar el flujo y permitir que el usuario ejecute opciones concretas. Esta separación ayuda a leer el proyecto: una persona puede abrir `main.py` para entender el recorrido general y luego entrar a `src/utils.py` para revisar cómo se implementa cada parte.

Este cambio modifica la forma de trabajar. Ya no se escribe código solo para ejecutarlo una vez y ver qué pasa. Se escribe código pensando en que pueda volver a ejecutarse con otros datos, revisarse después, corregirse sin dañar todo el archivo y compartirse con otra persona. Las entradas y salidas quedan ordenadas, las funciones quedan disponibles para nuevas sesiones y el historial de Git muestra cómo fue creciendo el proyecto.

Un notebook puede seguir siendo útil para explorar. El proyecto organizado sirve cuando esa exploración debe convertirse en un proceso repetible.

### Práctica guiada · ¿Qué tan fácil sería trabajar sobre este proyecto?

Antes de empezar a modificar nuestro propio repositorio, revisaremos tres proyectos públicos en GitHub que usan notebooks para análisis de datos. La intención es mirar los repositorios como lo haría una persona que llega por primera vez y necesita continuar el trabajo de alguien más.

Trabajen en parejas o grupos de tres. Abran los siguientes repositorios:

1. [Practical pandas projects](https://github.com/schlende/practical-pandas-projects)
2. [Python Diwali Sales Analysis](https://github.com/Divyanshu-RS/Python_Diwali_Sales_Analysis)
3. [Beginner Data Analysis Project](https://github.com/punneko/beginner-data-analysis-project)

Durante 15 minutos exploren los tres repositorios sin ejecutar nada todavía. Revisen el README, los notebooks, los archivos de datos, las carpetas y los nombres de archivos. Imaginen que alguien les pide hacer una mejora pequeña, por ejemplo:

* agregar una nueva visualización;
* cambiar el archivo de entrada;
* corregir una transformación de datos;
* guardar un nuevo archivo de salida;
* explicar a otra persona cómo ejecutar el análisis;
* reutilizar una parte del código en otro proyecto.

Respondan estas preguntas para cada repositorio:

| Pregunta                                                                                          | Repositorio 1 | Repositorio 2 | Repositorio 3 |
| ------------------------------------------------------------------------------------------------- | ------------- | ------------- | ------------- |
| ¿El README explica qué hace el proyecto?                                                          |               |               |               |
| ¿Se entiende por dónde empezar?                                                                   |               |               |               |
| ¿Los datos de entrada están ubicados en una carpeta clara?                                        |               |               |               |
| ¿Los resultados o salidas están separados de los datos originales?                                |               |               |               |
| ¿Hay un archivo `requirements.txt` o instrucciones para instalar librerías?                       |               |               |               |
| ¿Los notebooks tienen nombres descriptivos?                                                       |               |               |               |
| ¿El código parece fácil de reutilizar fuera del notebook?                                         |               |               |               |
| ¿Se puede identificar qué parte carga datos, qué parte transforma y qué parte muestra resultados? |               |               |               |
| ¿Qué sería difícil si tuvieran que hacer mantenimiento?                                           |               |               |               |
| ¿Qué mejora harían primero en la organización del proyecto?                                       |               |               |               |

Después de completar la tabla, asignen una calificación de 1 a 5 a cada repositorio:

| Calificación | Criterio                                                                                                                   |
| ------------ | -------------------------------------------------------------------------------------------------------------------------- |
| 1            | Sería difícil empezar. No queda claro qué abrir, qué instalar o qué ejecutar.                                              |
| 2            | Se entiende la idea general, pero faltan instrucciones o hay archivos mezclados.                                           |
| 3            | Se puede trabajar con esfuerzo. Hay partes claras y otras confusas.                                                        |
| 4            | Es fácil iniciar. La estructura ayuda a entender el proyecto.                                                              |
| 5            | Es muy fácil continuar el trabajo. Hay instrucciones, orden, nombres claros y separación entre entradas, código y salidas. |


#### Cierre de la práctica

Después de revisar los tres repositorios, vuelvan al repositorio del curso y observen su estructura:

```text
data/input/
data/output/
src/
main.py
requirements.txt
README.md
```

> Si una persona nueva llegara a tu proyecto dentro de tres meses, ¿qué necesitaría encontrar para empezar a trabajar sin pedirte explicaciones?


## Troubleshooting

| Error | Por qué ocurre | Solución |
|-------|---------------|----------|
| `(.venv)` no aparece en el prompt | Comando de activación no ejecutado o ejecutado en ruta incorrecta | Verificar que la terminal está en la raíz del proyecto con `pwd`; ejecutar `source .venv/bin/activate` |
| `ModuleNotFoundError: No module named 'pandas'` | Ambiente virtual no activado en esta terminal | `source .venv/bin/activate` y volver a intentar |
| `ModuleNotFoundError: No module named 'src'` | La terminal no está en la raíz del proyecto | `cd procesamiento_datos` o el nombre de la carpeta del repositorio |
| `IndentationError` | Mezcla de tabs y espacios o sangrado incorrecto | En VS Code: `Tab Size: 4`, `Insert Spaces: true` |
| `SyntaxError` en un f-string | Comillas internas del mismo tipo que las externas | Usa `"` afuera y `'` adentro, o al revés |
| `error: failed to push some refs` | El repositorio remoto tiene commits que el local no tiene | `git pull` primero y luego `git push` |
| `fatal: not a git repository` | La terminal no está dentro de la carpeta del proyecto | `cd` hasta la carpeta que contiene el `.git` |
| La función retorna `None` | Falta el `return` o está mal indentado | Verificar que cada rama del `if/else` tiene su `return` |
| El menú no muestra la opción nueva | Las líneas en `ejecutar_opcion()` siguen comentadas | Quitar los `#` de las líneas correspondientes |

---

## Para profundizar

- **Pro Git** (Chacon y Straub, 2014): capítulos 1 y 2 cubren el flujo básico que se usó hoy. Disponible en [git-scm.com/book](https://git-scm.com/book)
- **PEP 8 – Style Guide for Python Code**: [peps.python.org/pep-0008](https://peps.python.org/pep-0008). El estándar oficial de estilo. Conviene leer la introducción y las secciones de nomenclatura.
- **The Pragmatic Programmer** (Hunt y Thomas, 2019): el principio DRY y las ideas sobre código mantenible son directamente aplicables desde la primera función que escribiste hoy.
- **Clean Code** (Martin, 2008): los capítulos sobre funciones (cap. 3) y nombres (cap. 2) refuerzan los criterios de diseño de `utils.py`.

---

## Cierre

El entorno está montado, las dependencias documentadas y el primer historial de Git registrado. El proyecto tiene un menú funcional que irá creciendo en cada sesión.

Los conceptos de Python que trabajaste hoy, funciones, condicionales, ciclos, listas y diccionarios, son las piezas con las que están construidos todos los módulos que vienen: el cargador de datos, el transformador, el validador. La diferencia entre la Sesión 1 y la Sesión 9 no es que aparezcan conceptos completamente nuevos; es que esas mismas piezas se combinan de formas más sofisticadas sobre datos reales.

---

## Bibliografía

**Ingeniería de software:**
- Martin, R. C. (2008). *Clean Code: A Handbook of Agile Software Craftsmanship*. Prentice Hall.
- Hunt, A., y Thomas, D. (2019). *The Pragmatic Programmer* (20.ª ed. aniversario). Addison-Wesley.
- Van Rossum, G., Warsaw, B., y Coghlan, A. (2001). *PEP 8 – Style Guide for Python Code*. [peps.python.org/pep-0008](https://peps.python.org/pep-0008)

**Python:**
- Python Software Foundation. (2024). *The Python Tutorial*. [docs.python.org/3/tutorial](https://docs.python.org/3/tutorial)

**Control de versiones:**
- Chacon, S., y Straub, B. (2014). *Pro Git* (2.ª ed.). Apress. [git-scm.com/book](https://git-scm.com/book)



