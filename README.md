# QA API Testing - Restful Booker

## Descripción del proyecto

Este proyecto tiene como objetivo realizar pruebas de API utilizando **Postman y Newman**, aplicando técnicas de pruebas funcionales sobre la API Restful Booker.

Se busca validar el funcionamiento de los diferentes endpoints, verificar códigos de respuesta HTTP, probar la autenticación, gestionar información de reservas e identificar posibles defectos mediante pruebas automatizadas.

## Herramientas y tecnologías utilizadas

- **Postman 12.6.2:** Diseño y ejecución de pruebas de API.
- **Newman 6.2.3:** Ejecución de colecciones de Postman desde la línea de comandos.
- **Newman HTML Extra Reporter:** Generación de reportes HTML.
- **JavaScript:** Desarrollo de scripts de prueba y validaciones.
- **Node.js 24.15.0:** Entorno de ejecución.
- **Git y GitHub:** Control de versiones y gestión del repositorio.

## API bajo prueba

- **Nombre:** Restful Booker
- **URL base:** https://restful-booker.herokuapp.com

## Estructura del proyecto

```text
QA-API-Testing-Restful-Booker/
│
├── 1 Collections/
│   └── QA API Testing - Restful Booker.postman_collection.json
│
├── 2 Environment/
│   └── New_Environment.postman_environment.json
│
├── 3 Evidencia/
│   ├── 1 Get
│   │   └── Get.docx
│   ├── 2 Post
│   │   └── Post.docx
│   ├── 3 Put
│   │   └── Put.docx
│   ├── 4 Patch
│   │   └── Patch.docx
│   └── 5 Delete
│   │   └── Delete.docx
│
├── 4 Reporte/
│   ├── Reporte QA API - Restful Booker.xlsx
│   └── Reporte_API.html
│
├── .gitignore
└── README.md
```

## Cobertura de pruebas

La colección incluye los siguientes escenarios de pruebas:

- Autenticación y generación de token.
- Solicitudes GET para consultar información de reservas.
- Solicitudes POST para crear reservas.
- Solicitudes PUT para actualizar información de reservas.
- Solicitudes PATCH para actualizar parcialmente una reserva.
- Solicitudes DELETE para eliminar reservas.
- Pruebas positivas y negativas.
- Validación de códigos de respuesta HTTP.
- Validación del contenido y estructura de las respuestas.
- Gestión de variables de entorno.

## Autenticación y variables de entorno

El proyecto utiliza variables de entorno de Postman para gestionar los datos de prueba:

| Variable | Descripción |
|---|---|
| `username` | Usuario para la autenticación de la API |
| `password` | Contraseña para la autenticación |
| `authToken` | Token generado dinámicamente |
| `bookingId` | Identificador de reserva generado durante la ejecución |

El token de autenticación y el identificador de reserva se almacenan dinámicamente durante la ejecución de las pruebas.

El proyecto utiliza un Environmet de Postman para gestionar las variables necesarias durante la ejecución. El archivo publicado contiene valores de demostración y no incluye tokens de autenticación generados durante las pruebas.

## Ejecución de pruebas con Newman

### 1. Instalar Newman

```bash
npm install -g newman
```

### 2. Instalar Newman HTML Extra Reporter

```bash
npm install -g newman-reporter-htmlextra
```

### 3. Ejecutar la colección

Desde la carpeta principal del proyecto, ejecutar:

```bash
newman run "1 Collections/QA API Testing - Restful Booker.postman_collection.json" -e "2 Environments/New_Environment.postman_environment.json"
```

### 4. Generar reporte HTML

```bash
newman run "1 Collections/QA API Testing - Restful Booker.postman_collection.json" -e "2 Environments/New_Environment.postman_environment.json" -r cli,htmlextra --reporter-htmlextra-export "4 Reporte/Reporte_API.html"
```

El reporte HTML contiene información detallada sobre la ejecución, tiempos de respuesta, aserciones aprobadas y fallidas.

## Resultados de ejecución

En la última ejecución con Newman se obtuvieron los siguientes resultados:

| Indicador | Resultado |
|---|---:|
| Iteraciones | 1 |
| Solicitudes ejecutadas | 13 |
| Aserciones ejecutadas | 41 |
| Aserciones fallidas | 1 |

### Hallazgo identificado

Durante la ejecución se mantuvo una validación para detectar posibles respuestas HTTP 500 (Internal Server Error).

Este resultado se conserva como un hallazgo de QA pendiente de investigación. No se considera un defecto confirmado hasta realizar un análisis adicional.

## Evidencias y reportes

- La carpeta `3 Evidencia` contiene las evidencias de las ejecuciones de pruebas.
- La carpeta `4 Reporte` contiene el reporte HTML generado mediante Newman HTML Extra Reporter.

## Autor
Nadia Castillo Lara
Proyecto de portafolio QA Automation.

**Áreas de conocimiento:** API Testing | Postman | Newman | JavaScript | Pruebas funcionales | Reportes de automatización