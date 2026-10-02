# Observatorio de Conservación — Xochimilco

## Descripción

El Observatorio de Conservación es una plataforma de monitoreo ciudadano que integra múltiples fuentes de datos en un mapa interactivo del humedal de Xochimilco. Permite visualizar en tiempo real el estado del ecosistema, reportar incidencias ambientales y consultar avistamientos de ajolotes, actores del humedal, noticias y publicaciones científicas.

## Fuentes de Datos

### 1. Avistamientos de Ajolotes (Sighting)
- Registros de avistamientos de ajolotes silvestres y en cautiverio
- Datos: especie, morfo de color, estado de salud, hábitat, número de especímenes
- Filtros: verificado, pendiente, rechazado
- Coordenadas georreferenciadas

### 2. Reportes de Incidencias Ambientales (EnvironmentalReport)
- Reportes ciudadanos de contaminación, descargas ilegales, basura, tala, etc.
- Datos: tipo de contaminación, nivel de severidad, áreas afectadas
- Tipos: alcantarillas y drenajes, contaminación del agua, basura, ruido, lanchas de motor, tala, invasión de suelo, incendio, descarga química, pesca ilegal, maltrato animal, noticia relevante
- Niveles de severidad: crítico, alto, moderado, bajo

### 3. Actores del Humedal (Actor)
- Actores positivos: organizaciones, cooperativas, investigadores
- Actores negativos: contaminadores, invasores, operadores irregulares
- Vinculación con reportes ambientales

### 4. Noticias Automáticas (HistoricalDocument)
- Noticias generadas automáticamente con IA sobre drenajes, calidad del agua y ajolotes
- Actualización diaria
- Categorías: drenajes, contaminación, ajolotes, crisis hídrica, extinción, chinampas, restauración

### 5. Publicaciones Científicas (ScientificPublication)
- Publicaciones comunitarias y académicas
- Datos: autores, institución, país, año, DOI, resumen
- Filtros: aprobado, pendiente, rechazado

## Funcionalidades del Mapa

### Capas Ambientales
- **Calidad del agua:** Capa de monitoreo de parámetros físico-químicos
- **Alertas:** Alertas de incidencias críticas y severidad alta
- **Marcadores de actividad:** Eventos, voluntariados, brigadas

### Filtros
- Por tipo de dato: avistamientos, reportes, actores, noticias, publicaciones
- Por categoría: tipo de incidencia ambiental
- Por estado: verificado, pendiente, rechazado

### Panel de Resumen
- Total de avistamientos registrados
- Total de reportes ambientales
- Número de actores positivos y negativos
- Estadísticas de severidad

### Panel de Impacto Climático
- Proyecciones de impacto climático en el humedal
- Datos de temperatura y precipitación
- Proyecciones de pérdida de hábitat

### Formulario de Reporte Ciudadano
- Reporte de actores (positivos/negativos) con geolocalización
- Subida de evidencia fotográfica
- Notificación automática a administradores
- Estados: pendiente, aprobado, rechazado

## Tipos de Incidencias Ambientales

| Tipo | Emoji | Descripción |
|------|-------|-------------|
| Alcantarillas y drenajes | 🚧 | Descargas de drenaje en canales |
| Contaminación del agua | ☣️ | Contaminación química o biológica |
| Basura | 🗑️ | Residuos sólidos en canales y chinampas |
| Ruido | 🔊 | Contaminación acústica (motores, eventos) |
| Lanchas de motor | ⛵ | Embarcaciones motorizadas en zona protegida |
| Violencia | ⚡ | Incidentes de violencia |
| Tala | 🪚 | Tala de árboles nativos (ahuejote) |
| Invasión de suelo | 🏚️ | Asentamientos irregulares |
| Incendio | 🔥 | Incendios en chinampas o vegetación |
| Descarga química | 🧪 | Descargas industriales o químicas |
| Pesca ilegal | 🎣 | Pesca no autorizada |
| Maltrato animal | 🐾 | Maltrato a fauna silvestre |
| Noticia relevante | 📰 | Noticias ambientales relevantes |

## Coordenadas de Referencia

- **Centro de Xochimilco:** 19.285°N, -99.055°W
- **San Gregorio Atlapulco:** 19.257°N, -99.092°W
- **Cuemanco:** 19.272°N, -99.018°W
- **Tláhuac:** 19.286°N, -99.062°W

## Tecnologías Utilizadas

- **Frontend:** React + Leaflet (mapas interactivos)
- **Backend:** Base44 (entidades, SDK, autenticación)
- **Datos:** Entidades Sighting, EnvironmentalReport, Actor, HistoricalDocument, ScientificPublication
- **Tiempo real:** Suscripciones a cambios de entidades
- **IA:** Generación automática de noticias diarias

## Modelo de Datos

### Sighting (Avistamiento)
```
- title: string (título del avistamiento)
- description: string
- latitude: number
- longitude: number
- location_name: string
- date_observed: date
- species: enum (ambystoma_mexicanum, etc.)
- color_morph: enum (wild_type, leucistic, albino, etc.)
- health_status: enum (healthy, injured, sick, deceased, unknown)
- habitat_type: enum (canal, lake, wetland, river, captive, laboratory)
- specimen_count: number
- status: enum (pending, verified, rejected)
- photo_urls: string[]
```

### EnvironmentalReport (Reporte Ambiental)
```
- title: string
- description: string
- location: string
- latitude: number
- longitude: number
- contamination_types: string[]
- affected_areas: string[]
- severity_level: enum (critical, high, moderate, low)
- source: string
- date_reported: date
- media_urls: string[]
- status: enum (pending, verified, reported)
```

### Actor (Actor del Humedal)
```
- name: string
- description: string
- type: enum (good, bad)
- latitude: number
- longitude: number
- status: enum (pending, approved, rejected)
- media_urls: string[]
```

## Acceso

El Observatorio de Conservación está disponible en:
- Pestaña "Mapa" dentro de la página de Ciencia
- Ruta directa: /map

## Seguridad y Permisos

- **Lectura:** Pública para registros verificados
- **Creación:** Cualquier usuario autenticado puede reportar
- **Moderación:** Solo administradores pueden verificar/rechazar
- **Eliminación:** Solo administradores

---
*Santuario Ajolote · CIMA A.C. — Observatorio de Conservación de Xochimilco*
