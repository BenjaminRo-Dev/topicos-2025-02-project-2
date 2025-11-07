# PROYECTO: Sistema Multi-Red Social con LLM
## "Adaptación Automática de Contenido para Redes Sociales"

---

## DESCRIPCIÓN DEL PROYECTO

**Objetivo:** Desarrollar un portal que tome noticias/contenido y las adapte automáticamente para publicar en 5 redes sociales diferentes (Facebook, TikTok, Instagram, LinkedIn, WhatsApp).

**Modalidad:** Trabajo individual

**Duración:** 6 clases (del 12 nov al 28 nov)

**Componentes principales:**
1. **Procesamiento de contenido con LLM** - Adaptar contenido al formato y tono de cada red
2. **Integración con APIs** - Conectar con las APIs de cada plataforma para publicar
3. **Backend y orquestación** - Sistema central que coordina todo
4. **Portal web** - Interfaz para gestionar publicaciones

---

## CALENDARIO DE CLASES

**Fechas:**
- **HOY - Jueves 7 nov:** Clase introductoria
- **Martes 12 nov:** Clase 1
- **Jueves 14 nov:** Clase 2
- **Martes 19 nov:** Clase 3
- **Jueves 21 nov:** Clase 4
- **Martes 26 nov:** Clase 5
- **Jueves 28 nov:** PRESENTACIÓN FINAL

---

## HOY - Jueves 7 nov - CLASE INTRODUCTORIA

**Contenido de la clase:**
1. Presentación del problema real
2. Explicación del proyecto
3. Roadmap general
4. Entrega de recursos iniciales

**Material entregado:**
- Documento del proyecto (este archivo)
- Arquitectura general del sistema
- Links de documentación de APIs
- Criterios de evaluación

---

## CLASE 1 - Martes 12 nov
### Tema: Investigación y Feasibility Study

**Objetivos:**
- Investigar todas las APIs necesarias
- Entender características de cada red social
- Elegir stack tecnológico
- Diseñar arquitectura del sistema

**Entregables:**

### 1. Investigación de APIs (30%)

Documento que incluya:

**Meta Business API (Facebook + Instagram):**
- Documentación oficial revisada
- Requisitos para crear app de desarrollador
- Permisos necesarios
- Limitaciones y rate limits
- Proceso de autenticación OAuth 2.0

**LinkedIn API:**
- Documentación de Share API
- Requisitos de acceso
- Limitaciones
- Proceso de autenticación

**TikTok API:**
- Documentación de Content Posting API
- Requisitos de verificación (si aplica)
- Limitaciones
- Plan B si no es accesible para desarrollo académico

**WhatsApp Business API:**
- Comparativa: Twilio vs Meta Business
- Costos (si aplica)
- Facilidad de implementación
- Limitaciones

### 2. Características de Redes Sociales (30%)

Tabla comparativa:

| Red Social | Max caracteres | Tono | Hashtags | Emojis | Formato especial | Notas |
|------------|---------------|------|----------|--------|------------------|-------|
| Facebook   | 63,206        | Casual/Formal | Opcional | Sí | Links, imágenes | Texto largo permitido |
| Instagram  | 2,200         | Visual/Casual | Importante | Sí | Hashtags al final | Enfoque en imagen |
| LinkedIn   | 3,000         | Profesional | Moderado | Poco | Artículos | Tono corporativo |
| TikTok     | 2,200 (caption) | Joven/Trending | Importante | Sí | Video corto | Requiere video |
| WhatsApp   | 65,536        | Directo | Raro | Sí | Formato libre | Conversacional |

### 3. Investigación de LLM (20%)

Comparativa de modelos:

| Modelo | Costo | Latencia | Calidad | Accesibilidad | Recomendado para |
|--------|-------|----------|---------|---------------|------------------|
| GPT-4o-mini | $$ | Rápido | Alta | API Key | Producción |
| GPT-3.5 | $ | Muy rápido | Media-Alta | API Key | Desarrollo |
| Claude Sonnet | $$ | Rápido | Alta | API Key | Producción |
| Llama 3.1 (Ollama) | Gratis | Medio | Media | Local | Desarrollo/Demo |
| Gemini | $ | Rápido | Alta | API Key | Alternativa |

**Selección justificada:** Elegir 1 modelo y justificar por qué

### 4. Propuesta de Arquitectura (20%)

Incluir:
- Diagrama de arquitectura del sistema completo
- Stack tecnológico elegido (Backend: FastAPI/NestJS, Frontend: React/Vue, etc.)
- Diseño de base de datos (schema básico)
- Flujo de datos desde input hasta publicación

**Formato de exposición:** 15 minutos de presentación

---

## CLASE 2 - Jueves 14 nov
### Tema: Primer Prototipo - LLM y Adaptación de Contenido

**Objetivos:**
- Sistema LLM funcionando que adapta contenido
- Demo de transformación para las 5 redes
- Primeros prompts diseñados

**Entregables:**

### 1. Sistema de Adaptación de Contenido (50%)

API REST o módulo que reciba:

```json
{
  "titulo": "Nueva funcionalidad en nuestra plataforma",
  "contenido": "Hoy lanzamos una nueva característica que permite...",
  "target_networks": ["facebook", "instagram", "linkedin", "tiktok", "whatsapp"]
}
```

Y retorne:

```json
{
  "facebook": {
    "text": "🎉 Nueva funcionalidad en nuestra plataforma...",
    "hashtags": ["#Innovación", "#Tecnología"],
    "character_count": 245
  },
  "instagram": {
    "text": "✨ Gran noticia para nuestra comunidad...",
    "hashtags": ["#Tech", "#Innovation", "#NewFeature"],
    "character_count": 180,
    "suggested_image_prompt": "Modern tech interface with..."
  },
  "linkedin": {
    "text": "Nos complace anunciar el lanzamiento de...",
    "hashtags": ["#Technology", "#Innovation"],
    "character_count": 420,
    "tone": "professional"
  },
  "tiktok": {
    "text": "¿Viste lo nuevo? 🔥 Ahora puedes...",
    "hashtags": ["#Tech", "#Viral", "#NewFeature"],
    "character_count": 156,
    "video_hook": "Primera frase llamativa para el video"
  },
  "whatsapp": {
    "text": "Hola! 👋 Te cuento una novedad importante...",
    "character_count": 312,
    "format": "conversational"
  }
}
```

### 2. Diseño de Prompts (30%)

Documentar los prompts utilizados para cada red social.

**Ejemplo de estructura de prompt:**

```
Sistema: Eres un experto en marketing de redes sociales especializado en [RED_SOCIAL].

Contexto: Vas a recibir un contenido de noticia que debes adaptar específicamente para [RED_SOCIAL].

Características de [RED_SOCIAL]:
- Máximo de caracteres: [X]
- Tono: [profesional/casual/juvenil]
- Uso de hashtags: [importante/moderado/raro]
- Emojis: [sí/no/moderado]

Tarea: Transforma el siguiente contenido...

Formato de salida: JSON con...
```

### 3. Demo Funcional (20%)

- Repositorio Git con código limpio y documentado
- README con instrucciones de setup
- 3 casos de prueba diferentes:
  1. Noticia formal/corporativa
  2. Noticia de producto/servicio
  3. Anuncio de evento

**Formato de exposición:** 20 minutos (10 min presentación + 10 min demo en vivo)

---

## CLASE 3 - Martes 19 nov
### Tema: Integración con APIs - Parte 1 (Meta + LinkedIn)

**Objetivos:**
- Publicación funcional en Facebook
- Publicación funcional en Instagram
- Publicación funcional en LinkedIn
- Sistema de autenticación implementado

**Entregables:**

### 1. Integración Meta Business API (40%)

**Facebook:**
- App de Meta creada y configurada
- Autenticación OAuth 2.0 funcionando
- Endpoint que publica texto + imagen en Facebook
- Código de ejemplo:
  ```python
  POST /api/publish/facebook
  {
    "text": "Contenido adaptado...",
    "image_url": "https://...",
    "access_token": "..."
  }
  ```
- Manejo de errores (token expirado, permisos insuficientes, etc.)
- Al menos 1 publicación de prueba exitosa (screenshot)

**Instagram:**
- Publicación de imagen + caption funcionando
- Container creation + publish flow implementado
- Al menos 1 publicación de prueba exitosa (screenshot)

### 2. Integración LinkedIn API (30%)

- Autenticación OAuth 2.0 funcionando
- Publicación de texto funcionando
- Share API correctamente implementada
- Al menos 1 publicación de prueba exitosa (screenshot)

### 3. Manejo de Errores y Logging (20%)

- Sistema de logs estructurado (JSONL)
- Manejo de rate limiting
- Reintentos automáticos en caso de fallo temporal
- Validaciones antes de publicar

### 4. Documentación (10%)

- Guía de cómo crear y configurar las apps de desarrollador
- Variables de entorno necesarias (.env.example)
- Proceso de obtención de tokens de acceso
- Troubleshooting de errores comunes

**Formato de exposición:** 20 minutos (10 min + 10 min demo en vivo con publicaciones reales)

---

## CLASE 4 - Jueves 21 nov
### Tema: Integración con APIs - Parte 2 (TikTok + WhatsApp) + Backend

**Objetivos:**
- TikTok funcionando (al menos caption)
- WhatsApp funcionando
- Backend central que orquesta todo
- Sistema end-to-end básico

**Entregables:**

### 1. Integración TikTok (20%)

**Nota:** TikTok es el más complejo por el tema de videos

**Opción A (ideal):**
- Publicación de video corto con caption
- TikTok Content Posting API funcionando

**Opción B (mínimo aceptable):**
- Al menos generación automática de caption optimizado para TikTok
- Investigación documentada de limitaciones
- Plan de cómo se subiría el video (manual o automatizado)

### 2. Integración WhatsApp (25%)

**Opción recomendada:** Twilio WhatsApp API (más fácil para desarrollo)

- Envío de mensajes funcionando
- Formateo apropiado (saltos de línea, emojis)
- Puede ser a número de prueba o WhatsApp Business Sandbox
- Al menos 3 mensajes de prueba enviados (screenshots)

### 3. Backend Central y Orquestación (40%)

**Base de datos:**

Tablas principales:
```sql
-- Tabla de posts
CREATE TABLE posts (
  id UUID PRIMARY KEY,
  title VARCHAR(500),
  content TEXT,
  created_at TIMESTAMP,
  status VARCHAR(50) -- draft, processing, published, failed
);

-- Tabla de publicaciones por red
CREATE TABLE publications (
  id UUID PRIMARY KEY,
  post_id UUID REFERENCES posts(id),
  network VARCHAR(50), -- facebook, instagram, linkedin, tiktok, whatsapp
  adapted_content TEXT,
  status VARCHAR(50), -- pending, published, failed
  published_at TIMESTAMP,
  error_message TEXT,
  metadata JSONB -- IDs de publicación, URLs, etc.
);
```

**API REST:**

```
POST   /api/posts              - Crear nuevo post
GET    /api/posts              - Listar posts
GET    /api/posts/:id          - Ver detalles de un post
POST   /api/posts/:id/adapt    - Adaptar contenido (llamar a LLM)
POST   /api/posts/:id/publish  - Publicar en redes seleccionadas
GET    /api/posts/:id/status   - Ver estado de publicaciones
```

**Sistema de colas:**
- Redis + Bull/BullMQ o Celery
- Cola para publicaciones asíncronas
- Manejo de reintentos

### 4. Integración Completa (15%)

Flujo end-to-end funcionando:
1. Crear post en BD
2. Adaptar contenido con LLM
3. Guardar contenido adaptado
4. Publicar en las redes (las que ya funcionen)
5. Registrar resultado

**Formato de exposición:** 25 minutos (15 min + 10 min demo del flujo completo)

---

## CLASE 5 - Martes 26 nov
### Tema: Portal Web y Sistema Completo

**Objetivos:**
- Interfaz web funcionando
- Sistema 100% integrado
- Todas las redes funcionando
- Preparación para demo final

**Entregables:**

### 1. Portal Web (40%)

**Funcionalidades mínimas:**

**Página 1: Crear Publicación**
- Formulario con:
  - Título
  - Contenido (textarea)
  - Checkboxes para seleccionar redes destino
  - Botón "Generar Preview"
  - Botón "Publicar"

**Página 2: Preview de Adaptaciones**
- Vista previa del contenido adaptado para cada red
- Muestra character count
- Permite editar antes de publicar
- Botón "Confirmar y Publicar"

**Página 3: Dashboard**
- Lista de publicaciones recientes
- Estado de cada publicación por red (✅ exitoso, ⏳ pendiente, ❌ fallido)
- Filtros por estado y fecha
- Links a las publicaciones en cada red

**Tecnología sugerida:**
- React + Vite o Vue.js
- Tailwind CSS o Material-UI
- Axios para llamadas API

### 2. Sistema Completo Funcionando (40%)

**Las 5 redes deben estar funcionales:**
- ✅ Facebook
- ✅ Instagram
- ✅ LinkedIn
- ✅ WhatsApp
- ✅ TikTok (al menos caption, video opcional)

**Features adicionales:**
- Validación de contenido antes de publicar
- Manejo robusto de errores con mensajes claros
- Logs detallados
- Sistema de reintentos
- Notificaciones de éxito/error

### 3. Documentación Completa (10%)

**README.md:**
- Descripción del proyecto
- Arquitectura del sistema (diagrama)
- Tecnologías utilizadas
- Setup instructions paso a paso
- Variables de entorno necesarias
- Cómo ejecutar el proyecto

**Documentación de API:**
- Endpoints disponibles
- Request/Response examples
- Códigos de error

**Guía de deployment (opcional):**
- Cómo deployar cada componente
- Servicios cloud sugeridos

### 4. Video Demo (10%)

- Video de 2-3 minutos mostrando:
  - Interfaz del portal
  - Creación de una publicación
  - Preview de adaptaciones
  - Publicación en las 5 redes
  - Verificación de publicaciones exitosas

**Formato de exposición:** 30 minutos (ensayo de presentación final)

---

## CLASE 6 - Jueves 28 nov - PRESENTACIÓN FINAL

### Formato de Presentación

**Duración total:** 60 minutos

### Parte 1: Presentación Técnica (25 min)

**1. Introducción (3 min)**
- Problema que resuelve el sistema
- Objetivos del proyecto

**2. Arquitectura y Tecnologías (7 min)**
- Diagrama de arquitectura
- Stack tecnológico utilizado
- Justificación de elecciones técnicas
- Componentes principales

**3. Componente LLM (5 min)**
- Modelo elegido y por qué
- Estrategia de prompts
- Ejemplo de adaptación
- Challenges y soluciones

**4. Integraciones con APIs (7 min)**
- Proceso de integración con cada red
- Challenges específicos por plataforma
- Cómo se manejan rate limits y errores
- Autenticación y seguridad

**5. Backend y Orquestación (3 min)**
- Base de datos y modelo de datos
- Sistema de colas
- Manejo de estados

### Parte 2: Demo en VIVO (20 min)

**Escenario:** Publicar una noticia real en las 5 redes

**Paso 1 (3 min):** Ingresar contenido en el portal
- Mostrar interfaz
- Llenar formulario con noticia preparada
- Seleccionar las 5 redes

**Paso 2 (5 min):** Generar adaptaciones
- Click en "Generar Preview"
- Mostrar cómo el LLM adapta el contenido
- Explicar diferencias entre cada versión
- Mostrar character counts y validaciones

**Paso 3 (2 min):** Publicar
- Click en "Publicar"
- Mostrar sistema de colas trabajando
- Ver logs en tiempo real

**Paso 4 (8 min):** Verificar publicaciones
- Abrir Facebook y mostrar post publicado
- Abrir Instagram y mostrar post publicado
- Abrir LinkedIn y mostrar post publicado
- Mostrar mensaje enviado por WhatsApp
- Mostrar TikTok (caption al menos)

**Paso 5 (2 min):** Dashboard
- Mostrar historial de publicaciones
- Ver estados
- Explicar manejo de errores

### Parte 3: Challenges y Aprendizajes (10 min)

- Principales retos técnicos enfrentados
- Soluciones implementadas
- Lecciones aprendidas
- Posibles mejoras futuras

### Parte 4: Q&A (5 min)

---

## ARQUITECTURA TÉCNICA DEL SISTEMA

```
┌──────────────────────────────────────────────────────────┐
│                    PORTAL WEB                            │
│               (React/Vue + Tailwind)                     │
│                                                          │
│  ┌─────────────┐  ┌──────────────┐  ┌───────────────┐  │
│  │   Crear     │  │   Preview    │  │   Dashboard   │  │
│  │ Publicación │  │ Adaptaciones │  │   Historial   │  │
│  └─────────────┘  └──────────────┘  └───────────────┘  │
└────────────────────────┬─────────────────────────────────┘
                         │ HTTP REST
                         ▼
┌──────────────────────────────────────────────────────────┐
│              BACKEND CENTRAL                             │
│           (FastAPI o NestJS)                             │
│                                                          │
│  ┌─────────────────────────────────────────────────┐    │
│  │          API REST Layer                         │    │
│  │  /posts, /publish, /status, etc.                │    │
│  └──────────────────┬──────────────────────────────┘    │
│                     │                                    │
│  ┌─────────────────┴──────────────────────────────┐    │
│  │     Orchestration Service                      │    │
│  │  - Coordina flujo completo                     │    │
│  │  - Maneja transacciones                        │    │
│  └──────┬─────────────────────────────────┬───────┘    │
│         │                                 │             │
│  ┌──────▼────────┐                 ┌──────▼────────┐   │
│  │  PostgreSQL   │                 │  Redis Queue  │   │
│  │  - posts      │                 │  - Bull/      │   │
│  │  - publications│                 │    BullMQ     │   │
│  └───────────────┘                 └───────────────┘   │
└────┬────────┬────────┬────────┬────────┬────────────────┘
     │        │        │        │        │
     │        │        │        │        │
     ▼        ▼        ▼        ▼        ▼
┌─────────┐ ┌────┐ ┌────┐ ┌────┐ ┌────────┐
│   LLM   │ │ FB │ │ IG │ │ LI │ │TikTok/ │
│ Service │ │API │ │API │ │API │ │WhatsApp│
│         │ │    │ │    │ │    │ │  API   │
│ OpenAI/ │ └─┬──┘ └─┬──┘ └─┬──┘ └───┬────┘
│ Claude/ │   │      │      │        │
│ Llama   │   │      │      │        │
└─────────┘   │      │      │        │
              ▼      ▼      ▼        ▼
        ┌──────────────────────────────────┐
        │       REDES SOCIALES             │
        │  Facebook | Instagram | LinkedIn │
        │       TikTok | WhatsApp           │
        └──────────────────────────────────┘
```

---

## STACK TECNOLÓGICO SUGERIDO

### Backend
**Opción A: Python**
- Framework: FastAPI
- ORM: SQLAlchemy
- Queue: Celery + Redis
- HTTP Client: httpx
- LLM: LangChain + OpenAI/Anthropic SDK

**Opción B: Node.js**
- Framework: NestJS
- ORM: Prisma o TypeORM
- Queue: Bull/BullMQ + Redis
- HTTP Client: Axios
- LLM: OpenAI SDK / Anthropic SDK

### Frontend
- React + Vite + TypeScript
- Tailwind CSS o Material-UI
- React Query para manejo de estado
- Axios para HTTP

### Base de Datos
- PostgreSQL (preferido por JSONB support)
- Alternativa: MongoDB

### Infraestructura
- Redis (para colas)
- Docker + Docker Compose (para desarrollo)

---

## RECURSOS Y DOCUMENTACIÓN

### APIs de Redes Sociales

**Meta (Facebook + Instagram):**
- Docs: https://developers.facebook.com/docs/graph-api
- Graph API Explorer: https://developers.facebook.com/tools/explorer
- Crear App: https://developers.facebook.com/apps

**LinkedIn:**
- Docs: https://docs.microsoft.com/en-us/linkedin/marketing/integrations/community-management/shares/share-api
- Developer Portal: https://www.linkedin.com/developers

**TikTok:**
- Docs: https://developers.tiktok.com/
- Content Posting API: https://developers.tiktok.com/doc/content-posting-api-get-started

**WhatsApp:**
- Meta: https://developers.facebook.com/docs/whatsapp
- Twilio: https://www.twilio.com/docs/whatsapp
- Recomendado: Twilio (más fácil para empezar)

### LLMs

**OpenAI:**
- Docs: https://platform.openai.com/docs
- Pricing: https://openai.com/pricing
- Modelos recomendados: gpt-4o-mini, gpt-3.5-turbo

**Anthropic (Claude):**
- Docs: https://docs.anthropic.com
- Models: claude-3-haiku, claude-3-sonnet

**Ollama (Local):**
- Web: https://ollama.ai
- Modelos: llama3.1, mistral, gemma

**LangChain:**
- Docs: https://python.langchain.com/
- Útil para: prompt templates, chains, output parsing

### Herramientas

**Postman/Insomnia:** Para probar APIs

**ngrok:** Para webhooks en desarrollo local

**GitHub:** Para control de versiones

---

## CRITERIOS DE EVALUACIÓN

### Evaluación por Clase (60%)

| Clase | Peso | Criterios |
|-------|------|-----------|
| Clase 1 | 10% | Investigación completa, tabla comparativa, propuesta de arquitectura |
| Clase 2 | 10% | LLM funcionando, prompts bien diseñados, demo con 3 casos |
| Clase 3 | 15% | Meta + LinkedIn funcionando, publicaciones reales exitosas |
| Clase 4 | 15% | TikTok + WhatsApp funcionando, backend con BD y API |
| Clase 5 | 10% | Portal web completo, 5 redes funcionando, documentación |

### Presentación Final (40%)

| Aspecto | Peso | Criterios |
|---------|------|-----------|
| Funcionalidad | 20% | Sistema completo end-to-end, las 5 redes publicando correctamente |
| Calidad de código | 5% | Código limpio, organizado, con buenas prácticas |
| Documentación | 5% | README completo, API docs, guías de setup |
| Presentación | 10% | Claridad, estructura, manejo de Q&A, demo en vivo exitoso |

**Total: 100%**

---

## TIPS Y MEJORES PRÁCTICAS

### Para el desarrollo

1. **Empieza simple:** No intentes hacer todo perfecto desde el inicio
2. **Usa .env para credenciales:** NUNCA hagas commit de API keys
3. **Versionado:** Commitea frecuentemente con mensajes descriptivos
4. **Testing:** Usa cuentas de prueba, no tu cuenta personal
5. **Rate limiting:** Implementa delays entre publicaciones
6. **Logs:** Registra TODO (requests, responses, errores)

### Para las APIs

1. **Meta:** Usa Graph API Explorer para probar queries primero
2. **LinkedIn:** Los tokens expiran, maneja refreshing
3. **TikTok:** Es la más restrictiva, ten plan B
4. **WhatsApp:** Empieza con Twilio Sandbox (gratis)
5. **Tokens:** Guarda los access tokens de forma segura

### Para el LLM

1. **Temperature:** Usa ~0.7 para creatividad balanceada
2. **System prompt:** Define bien el rol y contexto
3. **Few-shot:** Da ejemplos de buenas adaptaciones
4. **Output format:** Especifica JSON schema en el prompt
5. **Caché:** No regeneres si ya existe una adaptación guardada

### Para la presentación

1. **Prepara backup:** Ten screenshots si la demo falla
2. **Testa TODO:** Prueba el flujo completo antes
3. **Internet:** Asegúrate de tener buena conexión
4. **Tiempo:** Practica para no pasarte del tiempo
5. **Q&A:** Anticipa preguntas difíciles

---

## CHECKLIST FINAL

Antes de la presentación final, verifica:

### Funcionalidad
- [ ] Portal web carga correctamente
- [ ] Puedo crear un nuevo post
- [ ] LLM genera adaptaciones para las 5 redes
- [ ] Facebook publica correctamente
- [ ] Instagram publica correctamente
- [ ] LinkedIn publica correctamente
- [ ] TikTok funciona (mínimo caption)
- [ ] WhatsApp envía mensaje
- [ ] Dashboard muestra historial
- [ ] Manejo de errores funciona

### Código
- [ ] Repositorio Git actualizado
- [ ] README.md completo
- [ ] .env.example con todas las variables
- [ ] Código comentado donde es necesario
- [ ] Sin credenciales hardcodeadas
- [ ] Dependencias documentadas (requirements.txt o package.json)

### Documentación
- [ ] Diagrama de arquitectura
- [ ] Guía de setup paso a paso
- [ ] Documentación de API
- [ ] Screenshots de publicaciones exitosas
- [ ] Video demo de 2-3 min

### Presentación
- [ ] Slides preparadas
- [ ] Demo testeada y funcionando
- [ ] Backup plan si algo falla
- [ ] Respuestas a posibles preguntas
- [ ] Tiempo cronometrado

---

## CONTACTO Y SOPORTE

**Para dudas técnicas:**
- Documentación oficial de cada API
- Stack Overflow
- Discord/Slack del curso (si existe)

**Para consultas con el docente:**
- Horario de consultas: [Definir]
- Email: [Definir]

---

## ENTREGA FINAL

**Fecha límite:** Jueves 28 nov

**Formato de entrega:**

1. **Repositorio Git:**
   - Link al repositorio público (GitHub/GitLab)
   - README completo
   - Todo el código fuente

2. **Documentación (en el repo):**
   - ARCHITECTURE.md con diagramas
   - API.md con documentación de endpoints
   - SETUP.md con guía de instalación

3. **Video demo:**
   - 2-3 minutos
   - Subido a YouTube/Drive
   - Link en el README

4. **Presentación:**
   - Slides (PDF o link)
   - En el repositorio en carpeta `/docs`

**Formato del repositorio:**
```
proyecto-redes-sociales/
├── README.md
├── backend/
│   ├── src/
│   ├── requirements.txt (o package.json)
│   ├── .env.example
│   └── ...
├── frontend/
│   ├── src/
│   ├── package.json
│   └── ...
├── docs/
│   ├── ARCHITECTURE.md
│   ├── API.md
│   ├── SETUP.md
│   ├── presentacion.pdf
│   └── diagramas/
├── docker-compose.yml (opcional)
└── .gitignore
```

---

**¡Éxito con el proyecto! 🚀**
