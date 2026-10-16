# MA1.5 y MA1.6 — Entornos virtuales y pruebas unitarias con pytest

## 1. Objetivo

En esta actividad aprenderemos a crear y utilizar **entornos virtuales de Python** y a realizar **pruebas unitarias con pytest**.

Trabajaremos con las siguientes prácticas:

- [MA1.5 — Creación de un entorno virtual](https://revilofe.github.io/section1/u01/practica/PROG-U1.-Practica005/)
- [MA1.6 — Uso de pytest](https://revilofe.github.io/section1/u01/practica/PROG-U1.-Practica006/)

Además, continuaremos utilizando **Git y GitHub** para organizar el trabajo, registrar nuestros avances y entregar los resultados.

## 2. Preparación del repositorio

1. Acepta el assignment de Classroom50 enlazado en Moodle.
2. Clona el repositorio generado en tu equipo utilizando `git clone`.
3. Abre la carpeta del repositorio en Visual Studio Code.

Encontrarás esta estructura inicial:

```text
repositorio/
├── .gitignore
├── README.md
├── ma15_creacion_entorno_virtual/
│   └── EVIDENCIAS.md
└── ma16_uso_pytest/
    └── EVIDENCIAS.md
```

Cada actividad se realizará dentro de su carpeta correspondiente.

**Importante:** Ambas prácticas pertenecen al mismo repositorio de Classroom50. No debes crear otro repositorio Git dentro de ninguna de estas carpetas.

## 3. ¿Dónde realizar los ejemplos y dónde entregar los ejercicios?

Las prácticas MA1.5 y MA1.6 incluyen explicaciones y ejemplos guiados para aprender a trabajar con entornos virtuales y pytest.

**Debes distinguir dos tipos de trabajo:**

**1. Ejemplos guiados de las prácticas**

Puedes realizarlos en una carpeta de tu ordenador, fuera del repositorio de Classroom50.

Por ejemplo:

```text
Prog2627/
└── PracticasPython/
    ├── ejemplos_entorno_virtual/
    └── ejemplos_pytest/
```

Estas carpetas son únicamente para practicar y experimentar siguiendo las explicaciones de las páginas web.

**No tienes que subir estos ejemplos al repositorio de Classroom50.**

**2. Ejercicios y evidencias que debes entregar**

Los ejercicios y las comprobaciones solicitadas en este enunciado sí deben realizarse dentro del repositorio de Classroom50, utilizando las carpetas que ya tienes preparadas:

```text
Prog2627
└── repositorio-classroom50/
    ├── .gitignore
    ├── README.md
    ├── ma15_creacion_entorno_virtual/
    │   ├── EVIDENCIAS.md
    │   └── imagenes/
    └── ma16_uso_pytest/
        ├── src/
        ├── tests/
        ├── EVIDENCIAS.md
        └── imagenes/
```

En estas carpetas guardarás los archivos Python que se soliciten, las pruebas unitarias y las capturas de pantalla que demuestren las comprobaciones realizadas.

**Importante:**

- Los ejemplos guiados te sirven para aprender y puedes repetirlos tantas veces como necesites.
- Los ejercicios y evidencias de este enunciado constituyen tu entrega.
- No es necesario subir todos los archivos que hayas creado mientras seguías las explicaciones de las prácticas.
- Los entornos virtuales `.venv/` nunca deben subirse a GitHub, aunque los hayas creado dentro del repositorio.

**En resumen:** practica primero con los ejemplos y después realiza y documenta los ejercicios solicitados en tu repositorio de Classroom50.

## 4. MA1.5 — Creación de un entorno virtual

Realiza la [práctica MA1.5](https://revilofe.github.io/section1/u01/practica/PROG-U1.-Practica005/) siguiendo las instrucciones correspondientes a tu sistema operativo.

Crea el entorno virtual dentro de la carpeta de esta actividad y comprueba que puedes activarlo y desactivarlo correctamente.

### Evidencias que debes entregar

Completa `ma15_creacion_entorno_virtual/EVIDENCIAS.md` con las siguientes capturas:

**1. Estructura final del proyecto**

Una captura del explorador de VS Code donde se observen las carpetas y archivos del proyecto, incluida la carpeta `.venv/`.

**2. Intérprete con el entorno virtual desactivado**

Desactiva el entorno virtual y ejecuta:

```bash
python -c "import sys; print(sys.executable)"
```

Realiza una captura donde se vea el comando y la ruta del intérprete utilizado.

**3. Intérprete con el entorno virtual activado**

Activa el entorno virtual y ejecuta nuevamente:

```bash
python -c "import sys; print(sys.executable)"
```

Realiza otra captura donde se observe que ahora se utiliza el intérprete ubicado dentro de `.venv/`.

**4. Comprobación de `.gitignore`**

Desde la raíz del repositorio ejecuta:

```bash
git status --short --ignored
```

Realiza una captura donde se observe que `.venv/` aparece como ignorada, normalmente con el prefijo `!!`.

Comprueba también que el archivo `.gitignore` contiene la regla correspondiente.

## 5. MA1.6 — Uso de pytest

Realiza la [práctica MA1.6](https://revilofe.github.io/section1/u01/practica/PROG-U1.-Practica006/).

### 5.1. Organización del proyecto

Dentro de `ma16_uso_pytest/`, crea dos carpetas:

- `src/`: contendrá los módulos Python con las funciones que vamos a desarrollar.
- `tests/`: contendrá los archivos con las pruebas unitarias de esas funciones.

Además, crea un archivo vacío llamado `__init__.py` en cada una de estas carpetas.

La estructura será:

```text
ma16_uso_pytest/
├── src/
│   ├── __init__.py
│   ├── compara_numeros.py
│   └── calcula_factorial.py
├── tests/
│   ├── __init__.py
│   ├── test_compara_numeros.py
│   └── test_calcula_factorial.py
└── EVIDENCIAS.md
```

### 5.2. ¿Para qué sirve `__init__.py`?

En Python, un **paquete** permite organizar módulos relacionados dentro de una carpeta.

El archivo `__init__.py` identifica explícitamente esa carpeta como un paquete de Python.

Por ejemplo:

```text
src/
├── __init__.py
└── compara_numeros.py
```

Nos permite utilizar una importación como esta desde un archivo de pruebas:

```python
from src.compara_numeros import compara_numeros
```

De esta manera, podemos acceder a la función `compara_numeros()` definida en el módulo correspondiente.

**¿Qué debes hacer?**

1. Crea `src/__init__.py`.
2. Crea `tests/__init__.py`.
3. Deja ambos archivos vacíos. No es necesario escribir código en ellos.
4. Comprueba que están incluidos en el repositorio Git.

Aunque en versiones modernas de Python pueden existir paquetes sin `__init__.py`, **en esta actividad lo utilizaremos para identificar explícitamente nuestros paquetes y mantener una estructura uniforme**.

Recuerda que `__init__.py` no instala pytest ni configura automáticamente todas las rutas de importación. Para que las importaciones funcionen, también debemos ejecutar las pruebas desde la ubicación adecuada.

### 5.3. Ejercicio 1 — Comparar números

Crea los archivos:

- `src/compara_numeros.py`
- `tests/test_compara_numeros.py`

Implementa una función que reciba dos números y devuelva:

- El mayor de ambos si son diferentes.
- `0` si son iguales.

Escribe pruebas que comprueben su funcionamiento con números positivos, negativos e iguales.

### 5.4. Ejercicio 2 — Calcular el factorial

En este ejercicio vamos a comprobar el funcionamiento de una función que calcula el factorial de un número.

El factorial de un número entero positivo consiste en multiplicar todos los números enteros desde `1` hasta ese número.

Por ejemplo:

- `0! = 1` (por definición)
- `1! = 1`
- `3! = 3 × 2 × 1 = 6`
- `5! = 5 × 4 × 3 × 2 × 1 = 120`

Como todavía no hemos estudiado los bucles, **te proporcionamos la función ya implementada**:

Archivo `src/calcula_factorial.py`:

```python
def calcula_factorial(numero):
    """Calcula el factorial de un entero entre 0 y 10."""

    if type(numero) is not int or numero < 0 or numero > 10:
        return -1

    resultado = 1

    for i in range(2, numero + 1):
        resultado *= i

    return resultado
```

No necesitas comprender todavía todos los detalles del bucle `for`. Por ahora, debes saber que permite repetir la multiplicación para calcular el factorial.

**Tu trabajo consiste en:**

1. Copiar la función en `src/calcula_factorial.py`.
2. Crear `tests/test_calcula_factorial.py`.
3. Importar la función utilizando `from src.calcula_factorial import calcula_factorial`.
4. Escribir pruebas con pytest para comprobar, al menos:
   - El factorial de `0`.
   - El factorial de `1`.
   - El factorial de `5`.
   - El factorial de `10`.
   - Un número negativo.
   - Un número mayor que `10`.
5. Ejecutar las pruebas y comprobar que todas se superan.
6. Modificar intencionadamente algún resultado de la función para provocar un fallo en una prueba.
7. Capturar el fallo, corregir el error y volver a ejecutar las pruebas.

**Objetivo:** aprender a verificar el comportamiento de una función mediante pruebas unitarias, aunque todavía no conozcas todas las instrucciones utilizadas en su implementación.

### 5.5. Ejecución de las pruebas

Desde el terminal, sitúate en la carpeta `ma16_uso_pytest/`, activa su entorno virtual y ejecuta:

```bash
python -m pytest
```

Si has organizado correctamente los archivos, pytest localizará y ejecutará las pruebas.

**Importante:** Si utilizas importaciones como `from src.compara_numeros import compara_numeros`, ejecuta el comando desde `ma16_uso_pytest/`, no desde `tests/`.

Después, configura y utiliza la vista **Testing** de VS Code para ejecutar las pruebas desde el entorno gráfico.

Por último, introduce intencionadamente un error en la función del factorial y comprueba que alguna prueba detecta el fallo. Corrige el error y vuelve a ejecutar todas las pruebas.

### Evidencias que debes entregar

Completa `ma16_uso_pytest/EVIDENCIAS.md` con:

**1. Estructura final del proyecto**

Captura del explorador de VS Code donde se observen los módulos, las pruebas y los archivos `__init__.py`.

**2. Ejecución desde el terminal**

Captura de la ejecución correcta de `python -m pytest`, mostrando que todas las pruebas se superan.

**3. Ejecución desde Testing de VS Code**

Captura de la vista Testing con las pruebas detectadas y ejecutadas correctamente.

**4. Detección de un error**

Captura de una ejecución fallida después de introducir intencionadamente un error en la función del factorial. Debe observarse el fallo y su mensaje.

**5. Corrección del error**

Captura de una nueva ejecución donde todas las pruebas vuelvan a superarse.

**El código entregado finalmente debe estar corregido y superar todas las pruebas.**

## 6. Cómo incorporar las capturas a EVIDENCIAS.md

Las capturas deben guardarse en el propio repositorio y mostrarse dentro del archivo `EVIDENCIAS.md` correspondiente.

### Paso 1. Crear la carpeta de imágenes

Dentro de cada actividad crea una carpeta llamada `imagenes/`.

Por ejemplo:

```text
ma15_creacion_entorno_virtual/
├── EVIDENCIAS.md
└── imagenes/
    ├── estructura.png
    ├── interprete_sistema.png
    ├── interprete_venv.png
    └── gitignore.png
```

Puedes utilizar archivos `.png` o `.jpg` con nombres descriptivos.

### Paso 2. Insertar las imágenes en Markdown

Abre `EVIDENCIAS.md` y utiliza esta sintaxis:

```markdown
![Descripción de la imagen](imagenes/nombre_imagen.png)
```

Por ejemplo:

```markdown
## 2. Intérprete con el entorno desactivado

![Intérprete de Python del sistema](imagenes/interprete_sistema.png)

## 3. Intérprete con el entorno activado

![Intérprete de Python del entorno virtual](imagenes/interprete_venv.png)
```

La ruta de la imagen es relativa a la ubicación del archivo `EVIDENCIAS.md`.

### Paso 3. Comprobar las imágenes

Abre la vista previa de Markdown en VS Code:

- **Windows/Linux:** `Ctrl + Shift + V`
- **macOS:** `Cmd + Shift + V`

Comprueba que todas las imágenes se muestran correctamente.

**No utilices rutas absolutas de tu ordenador**, como `C:\Users\...`, porque no funcionarán al consultar el archivo desde GitHub.

## 7. Estructura final del repositorio

Al terminar ambas prácticas, el repositorio tendrá una estructura similar a esta:

```text
repositorio/
├── .gitignore
├── README.md
│
├── ma15_creacion_entorno_virtual/
│   ├── EVIDENCIAS.md
│   └── imagenes/
│       ├── estructura.png
│       ├── interprete_sistema.png
│       ├── interprete_venv.png
│       └── gitignore.png
│
└── ma16_uso_pytest/
    ├── src/
    │   ├── __init__.py
    │   ├── compara_numeros.py
    │   └── calcula_factorial.py
    ├── tests/
    │   ├── __init__.py
    │   ├── test_compara_numeros.py
    │   └── test_calcula_factorial.py
    ├── EVIDENCIAS.md
    └── imagenes/
        ├── estructura.png
        ├── pytest_terminal.png
        ├── pytest_testing.png
        ├── pytest_error.png
        └── pytest_corregido.png
```

Los nombres de las imágenes son orientativos. Puedes utilizar otros, siempre que estén correctamente enlazados.

Las carpetas `.venv/` existirán en tu equipo, pero **no deben aparecer en el repositorio de GitHub**.

## 8. Control de versiones y entrega

Durante el desarrollo debes utilizar Git para registrar los avances de tu trabajo.

No esperes a terminar ambas prácticas para realizar un único commit.

Es recomendable registrar distintos momentos:

- Creación y comprobación del entorno virtual.
- Incorporación de las evidencias de MA1.5.
- Implementación de las funciones y pruebas de MA1.6.
- Incorporación de las capturas y finalización del trabajo.

Utiliza mensajes de commit descriptivos.

Cuando hayas terminado:

1. Comprueba el estado del repositorio con `git status`.
2. Añade los archivos correspondientes mediante `git add`.
3. Registra los cambios con `git commit`.
4. Publica los cambios en GitHub mediante `git push`.
5. Accede al repositorio de Classroom50 desde el navegador y comprueba que aparecen los archivos y las imágenes.
6. Marca la tarea como entregada en Moodle siguiendo las instrucciones que hemos establecido desde el inicio del curso.

**Recuerda:**

- No subas `.venv/`, `__pycache__/` ni `.pytest_cache/`.
- Incluye los archivos `__init__.py` de `src/` y `tests/`.
- Las capturas deben ser legibles y mostrar los resultados solicitados.
- Los archivos `EVIDENCIAS.md` deben mostrar correctamente todas las imágenes en GitHub.
- Ambas prácticas se entregan en este mismo repositorio.
