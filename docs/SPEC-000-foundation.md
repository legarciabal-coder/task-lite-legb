# PC-000 — Foundation

## Propósito

Establecer la base técnica y las convenciones iniciales de **TaskFlow Lite**, de manera que el proyecto pueda evolucionar incrementalmente hacia una herramienta web simple para registrar, visualizar y actualizar tareas.

Esta SPEC define únicamente la estructura, tecnologías, restricciones y criterios técnicos iniciales. No implementa funcionalidades de gestión de tareas.

## Alcance

La fundación inicial comprende:

* Configuración de un proyecto web basado en **HTML5, CSS3 y JavaScript ES Modules**.
* Organización del código fuente dentro de `src/`.
* Preparación de una estructura inicial que permita incorporar funcionalidades posteriormente.
* Definición de convenciones de nombres para archivos, carpetas, variables, funciones y módulos.
* Definición de convenciones básicas para el uso de Git.
* Establecimiento de una **Definition of Done técnica inicial**.
* Preparación conceptual para incorporar **localStorage** como mecanismo de persistencia en una etapa posterior.

No se desarrollarán todavía historias funcionales ni lógica relacionada con tareas.

## Estructura inicial del proyecto

La estructura base será:

```text
TaskFlow-Lite/
├── src/
│   ├── index.html
│   ├── css/
│   └── js/
├── .gitignore
└── PC-000-foundation.md
```

### Responsabilidad inicial

* `src/index.html`: documento HTML principal de la aplicación.
* `src/css/`: hojas de estilo del proyecto.
* `src/js/`: módulos JavaScript de la aplicación.
* `.gitignore`: archivos y directorios que no deben versionarse.
* `PC-000-foundation.md`: especificación de fundación del proyecto.

La estructura podrá crecer conforme se incorporen nuevas capacidades, manteniendo la organización dentro de `src/`.

## Restricciones técnicas

* El proyecto utilizará únicamente **HTML5, CSS3 y JavaScript con ES Modules**.
* No se utilizarán frameworks de frontend o backend.
* No se utilizarán librerías externas salvo que una decisión posterior las autorice explícitamente.
* No existirá backend ni API propia.
* La aplicación deberá poder ejecutarse localmente desde **VSCode** mediante un entorno HTTP local.
* La persistencia de datos se implementará posteriormente mediante **localStorage**.
* En esta etapa no se implementará almacenamiento ni recuperación de tareas.
* El código fuente de la aplicación deberá permanecer dentro de `src/`.
* La solución deberá ser ejecutable en un navegador web moderno con soporte para JavaScript ES Modules.
* No se introducirán herramientas o tecnologías que contradigan las restricciones definidas en esta SPEC.

## Convenciones de nombres

### Archivos y carpetas

* Carpetas: nombres en minúsculas.
* Archivos HTML y CSS: nombres en minúsculas utilizando `kebab-case` cuando exista más de una palabra.
* Archivos JavaScript: nombres en minúsculas utilizando `kebab-case`.
* Los módulos deberán representar claramente su responsabilidad.

Ejemplos:

```text
src/css/
src/js/
src/js/task-manager.js
src/css/task-list.css
```

### JavaScript

* Variables y funciones: `camelCase`.
* Clases: `PascalCase`.
* Constantes: `UPPER_SNAKE_CASE` cuando representen valores constantes globales o de configuración.
* Los nombres deberán describir su propósito y evitar abreviaturas innecesarias.
* Cada módulo deberá tener una responsabilidad clara.

Ejemplos:

```text
taskList
createTask()
TaskManager
MAX_TASKS
```

## Convenciones de Git

Se utilizará Git para controlar la evolución incremental del proyecto.

### Ramas

* `main`: versión estable del proyecto.
* Para trabajo incremental se utilizarán ramas descriptivas con el formato:

```text
feature/<nombre>
fix/<nombre>
docs/<nombre>
```

Ejemplos:

```text
feature/task-registration
fix/task-validation
docs/update-foundation
```

### Commits

Los commits deberán ser:

* Pequeños y enfocados en un único cambio lógico.
* Descriptivos.
* Escritos preferentemente en infinitivo o de forma imperativa.
* Relacionados con el objetivo o historia correspondiente cuando esta exista.

Formato recomendado:

```text
tipo: descripción breve
```

Tipos iniciales:

* `feat`: nueva funcionalidad.
* `fix`: corrección.
* `docs`: documentación.
* `refactor`: reorganización sin cambio funcional.
* `test`: pruebas.
* `chore`: mantenimiento técnico.

Ejemplo:

```text
docs: define foundation specification
```

## Definition of Done técnica inicial

La fundación se considerará terminada cuando:

* La estructura inicial del proyecto exista dentro de `src/`.
* El proyecto pueda abrirse y ejecutarse localmente desde VSCode en un navegador mediante un entorno HTTP local.
* HTML, CSS y JavaScript estén separados de acuerdo con la estructura definida.
* JavaScript utilice el modelo de **ES Modules**.
* No existan frameworks ni backend.
* La configuración inicial pueda ser versionada correctamente mediante Git.
* Exista un `.gitignore` apropiado para evitar archivos generados o específicos del entorno.
* Las convenciones de nombres y Git establecidas en esta SPEC sean aplicables al código futuro.
* No se hayan incorporado funcionalidades de negocio que pertenezcan a historias posteriores.

## Fuera de alcance

Queda explícitamente fuera de esta SPEC:

* Registro de tareas.
* Edición o actualización de tareas.
* Visualización funcional de tareas.
* Estados de tareas.
* Validaciones funcionales de tareas.
* Persistencia real mediante `localStorage`.
* Backend, base de datos o API.
* Autenticación y autorización.
* Frameworks o librerías de frontend.
* Diseño visual definitivo de la aplicación.
* Historias de usuario y sus criterios de aceptación.
* Pruebas funcionales de las capacidades del producto.

Esta fundación únicamente prepara el terreno técnico para implementar las capacidades de TaskFlow Lite de manera incremental.
