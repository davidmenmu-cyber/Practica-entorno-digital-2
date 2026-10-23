# Documentación de mi entorno de desarrollo · Práctica 2

**Nombre y apellidos:** David Mendoza Muñoz
**URL de mi repositorio:** https://github.com/davidmenmu-cyber/Practica-entorno-digital-2

> Rellena cada apartado a medida que avanzas. Donde pone «pega aquí», copia el texto
> de la terminal (no hace falta captura). Escribe con tus palabras: no se valora la longitud,
> sino que se note que entiendes lo que has hecho.

---

## 1. Instalación de entornos (CE 2.a)

### 1.1. Entorno vacío (paso 3)

Resultado de `java -version` y `node -v` **antes** de instalar nada:

```
pega aquí
"name": "Entorno DAW",
  "image": "mcr.microsoft.com/devcontainers/base:jammy"
```

¿Por qué crees que aparece ese mensaje? (relaciónalo con la diapositiva «Problemas habituales del entorno»)


> 

### 1.2. Después de la 1.ª reconstrucción (paso 5)

Resultado de `java -version`, `node -v` y `jupyter lab --version` **después**:

```
pega aquí
```

¿Qué líneas nuevas han aparecido en `devcontainer.json`? Explica con tus palabras qué hace cada una:

"ghcr.io/devcontainers/features/node:1": {},
"ghcr.io/devcontainers/features/python:1": {
"installJupyterlab": true
> 

### 1.3. Comparativa de los dos IDE (paso 6)

|                                         | Editor de GitHub Codespaces | JupyterLab |
|-----------------------------------------|-----------------------------|------------|
| ¿Libre o propietario?                   |       propietario           | libre
| Licencia / empresa o comunidad          |  microsoft                   abierto     |
| ¿Tiene coste? ¿Con qué límites?         |    si y horas               |  gratis    |
| ¿Se puede usar fuera de GitHub?         |     no                      |    si    |
| Lo que más me ha gustado                |                             |            |
| Lo que menos me ha gustado              |                             |            |
| ¿Para qué tipo de trabajo lo elegiría?  |         web                 |   IA         |

---

## 2. Módulos y extensiones (CE 2.b)

| Extensión | ¿Para qué sirve? | ¿Qué cambió al instalarla? | ¿La mantengo? ¿Por qué? |
|-----------|------------------|----------------------------|-------------------------|
| Extension Pack for Java | Añade herramientas para programar en Java, como autocompletado, avisos de errores y depuración. | Aparecieron funciones de Java en el editor y pude compilar y depurar código desde VS Code. | Sí, porque facilita trabajar con Java. Además, está incluido en `devcontainer.json` para que se instale al crear el entorno. |
| Code Spell Checker      | Detecta posibles errores ortográficos en el texto del código y la documentación. | Subraya palabras que no reconoce y ofrece sugerencias. | Sí, porque ayuda a corregir erratas en comentarios y documentación. No está incluido en `devcontainer.json`, así que cada persona tendría que instalarlo por separado. |

¿Qué diferencia hay entre instalar una extensión **solo desde el panel** y añadirla **también a `devcontainer.json`**?
Instalarla solo desde el panel la añade a tu entorno personal, mientras que incluirla en devcontainer.json permite que se instale automáticamente para todo el equipo al crear el entorno.
> 

---

## 3. Personalización y automatización (CE 2.c)

- **Tema visual elegido** (paso 10) y por qué:he elegido el de visual code studio ya que me resulta mas comodo.
- **Ajuste del proyecto** (paso 10). ¿Qué archivo se ha creado y qué contiene?
un JSON sin haber sin haber escrito, contiene que esta seguro

```
pega aquí el contenido de .vscode/settings.json
``` 
"editor.formatOnSave": true

- **Atajo de teclado** (paso 11). ¿Qué acción, qué combinación y para qué te sirve?

 para hacer rebuild, combinacion: comd+option+m

- **Snippet** (paso 12). ¿Qué escribes y qué aparece? 

una nueva carpeta con el nombre daw

- **Automatización al crear el entorno** (paso 14). ¿Qué hace `postCreateCommand` y qué archivos/carpetas han aparecido después de reconstruir?

node_modules y package-lock.json. 

- **Tareas** (paso 13). ¿Cuántas tareas hay en `tasks.json` y qué hace cada una?
Hay 3 tareas:
 Java: compilar, empaquetar y ejecutar.
 TypeScript: compilar y ejecutar.
 Build completo: ejecutar las dos tareas anteriores en orden.

¿Qué parte de toda esta configuración es **personal** (solo para ti) y qué parte es **del proyecto** (la recibe cualquiera que abra el repositorio)?

Personal: las extensiones instaladas solo desde el panel y las preferencias de VS Code.

Del proyecto: los archivos devcontainer.json, tasks.json, package.json y el código subido a GitHub.
> 

---

## 4. Ejecutables de diferentes lenguajes en el mismo entorno (CE 2.e)

Salida completa de la tarea **Build completo** (paso 15):

```
pega aquí
 === FACTURA generada con Java 27 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR
 *  Las tareas reutilizarán el terminal, presione cualquier tecla para cerrarlo. 

 *  Ejecutando tarea: npm run build && npm start 


> plantilla-entorno-daw@1.0.0 build
> tsc


> plantilla-entorno-daw@1.0.0 start
> node dist/factura.js

=== FACTURA generada con Node.js v24.22.1 ===
Dominio web anual              12.00 EUR
Alojamiento web                59.90 EUR
Logotipo corporativo          150.00 EUR
-----------------------------------------
Base imponible                221.90 EUR
IVA (21 %)                     46.60 EUR
TOTAL                         268.50 EUR
```

| Lenguaje | Archivo fuente | Herramienta que lo traduce | Archivo generado | Cómo se ejecuta |
|----------|----------------|----------------------------|------------------|-----------------|
| Java       | `src/java/Factura.java` |   |   |   |
| TypeScript | `src/ts/factura.ts`     |   |   |   |

**Opcional:** ¿has podido ejecutar los mismos archivos desde JupyterLab (paso 19)? ¿Por qué funciona en los dos IDE sin instalar nada más?

> 
no he podido entrar en jupyterlab
---

## 5. Sistema de actualizaciones (CE 2.d)

| Elemento | ¿Quién lo actualiza? | Modo (automático / manual / ninguno) | Qué he configurado yo |
|----------|----------------------|--------------------------------------|-----------------------|
| El editor de Codespaces | GitHub | Automático | Nada; uso el editor proporcionado por Codespaces. |
| Las extensiones         | Sus autores y el Marketplace de VS Code | Automático | He añadido Extension Pack for Java a `devcontainer.json`; se instala al crear el entorno. |
| Java                    | La Feature de Java de Dev Containers | Manual (al reconstruir) | He fijado la versión mayor 21 en `devcontainer.json`. |
| Node.js                 | La Feature de Node.js de Dev Containers | Manual (al reconstruir) | He añadido la Feature de Node.js sin fijar versión. |
| Dependencias npm (lodash, typescript…) | Los autores de cada paquete publican versiones; yo decido cuándo instalarlas | Manual | He fijado versiones concretas en `package.json` y las actualizo cuando lo decido. |

Versión de Java **antes** (paso 5) y **después** (paso 18):

```
Paso 5 (antes): no tengo guardada aquí la salida de `java -version`.
Paso 18 (después): no puedo confirmar la salida exacta del paso; ahora `java -version` muestra OpenJDK 21.

Nota: la salida del Build completo que pegué antes muestra Java 27, pero la configuración actual fija Java 21. Las dos salidas no coinciden; debo comprobar cuál corresponde al paso 18.
```

Resultado de `npm outdated` (paso 17):

```
pega aquí
Package         Current    Wanted   Latest  Location                    Depended by
@types/lodash  4.14.202  4.14.202  4.17.27  node_modules/@types/lodash  Practica-entorno-digital-2
@types/node    20.11.30  20.11.30   26.6.5  node_modules/@types/node    Practica-entorno-digital-2
lodash          4.17.20   4.17.20   4.18.1  node_modules/lodash         Practica-entorno-digital-2
typescript        5.4.5     5.4.5    7.0.2  node_modules/typescript     Practica-entorno-digital-2
```

Resultado de `npm audit` **antes** de actualizar lodash (solo el resumen final):

```
pega aquí
1 high severity vulnerability

To address all issues, run:
  npm audit fix --force
```

Resultado de `npm audit` **después**:

```
pega aquí
found 0 vulnerabilities
```

**Mi política de actualizaciones**: si este entorno lo usara un equipo de 5 personas durante todo el curso, ¿qué dejarías en automático y qué fijarías a mano? Justifícalo.

Dejaría en automático las actualizaciones de seguridad, pero fijaría a mano las versiones de los programas

> 

---

## 6. Incidencias

Anota cualquier problema que hayas tenido y cómo lo resolviste (también si usaste un fragmento completo).
La verdad he tenido bastanes complicaciones para completarlo, ya que era mi primera vez haciendo esto, pero he conseguido completarlo, incidencias:
-a la hora de asceder a jupiter se me quedaba cargando sin avanzar teniendo que dejar esa actividad.
-en el primer rebuild ya que al principio no me funcionaba pero lo consigui al poco
> 

## 7. Reflexión final

¿Qué ventaja tiene describir el entorno «como código» frente a instalar cada programa a mano en tu ordenador? Piensa en un equipo con Mac y Windows.

Permite que todos tengan los mismos programas y versiones en Mac y Windows, evitando errores y ahorrando tiempo de instalación.
> 
