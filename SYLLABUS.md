# SYLLABUS - Tópicos Avanzados
## LLM Applications - Sistema Multi-Red Social

**Universidad:** Universidad Autónoma Gabriel René Moreno (UAGRM)
**Facultad:** Ingeniería en Sistemas
**Semestre:** 2025-02
**Período:** 7 de noviembre - 28 de noviembre de 2025
**Modalidad:** Presencial - Trabajo Individual

---

## 1. INFORMACIÓN GENERAL

### 1.1 Datos del Curso
- **Nombre:** Tópicos Avanzados - LLM Applications
- **Código:** [Código del curso]
- **Créditos:** [Número de créditos]
- **Nivel:** Pregrado Avanzado
- **Requisitos:** Programación Avanzada, Bases de Datos, Desarrollo Web

### 1.2 Docente
- **Nombre:** [Nombre del docente]
- **Email:** [Email institucional]
- **Horario de consultas:** [Definir]
- **Ubicación:** [Oficina/Aula]

### 1.3 Horario de Clases
- **Días:** Martes y Jueves
- **Horario:** [Definir horario]
- **Aula:** [Definir aula]
- **Duración:** 6 clases + 1 presentación final

---

## 2. DESCRIPCIÓN DEL CURSO

### 2.1 Propósito

Este curso intensivo de 4 semanas ofrece una experiencia práctica en el desarrollo de aplicaciones con Large Language Models (LLMs). Los estudiantes construirán un sistema completo de publicación automatizada en redes sociales, integrando múltiples APIs y tecnologías modernas.

### 2.2 Justificación

En el contexto actual, las organizaciones necesitan optimizar su presencia en redes sociales. Este proyecto aborda un problema real: la adaptación manual de contenido para diferentes plataformas es ineficiente y propensa a errores. Los estudiantes aprenderán a:

- Aplicar LLMs a problemas reales de negocio
- Integrar APIs de terceros (Meta, LinkedIn, TikTok, WhatsApp)
- Desarrollar sistemas full-stack completos
- Implementar arquitecturas escalables con colas y microservicios

### 2.3 Enfoque Pedagógico

**Aprendizaje Basado en Proyectos (ABP):**
- Proyecto único que se desarrolla incrementalmente
- Entregables semanales que construyen sobre el anterior
- Demo y exposición en cada clase
- Presentación final del sistema completo

---

## 3. COMPETENCIAS Y OBJETIVOS

### 3.1 Competencia General

Desarrollar sistemas de software completos que integran Large Language Models y APIs de terceros para resolver problemas reales de automatización de contenido en redes sociales.

### 3.2 Competencias Específicas

**C1. Integración de LLMs:**
- Diseñar prompts efectivos para diferentes contextos
- Implementar APIs de LLM (OpenAI, Claude, Ollama)
- Optimizar respuestas mediante prompt engineering
- Manejar limitaciones y errores de modelos

**C2. Integración de APIs de Redes Sociales:**
- Implementar autenticación OAuth 2.0
- Publicar contenido en múltiples plataformas
- Manejar rate limiting y reintentos
- Cumplir con políticas de uso de APIs

**C3. Arquitectura de Sistemas:**
- Diseñar arquitecturas escalables
- Implementar sistemas de colas (Redis + Bull/Celery)
- Desarrollar APIs REST
- Gestionar estado con bases de datos

**C4. Desarrollo Full-Stack:**
- Backend (FastAPI o NestJS)
- Frontend (React)
- Base de datos (PostgreSQL/MongoDB)
- Deployment con Docker

**C5. Buenas Prácticas:**
- Versionado con Git
- Documentación técnica
- Seguridad (manejo de credenciales)
- Testing y logging

### 3.3 Objetivos de Aprendizaje

Al finalizar el curso, el estudiante será capaz de:

1. **Diseñar e implementar** sistemas que utilicen LLMs para transformación de contenido
2. **Integrar** múltiples APIs de terceros en un sistema cohesivo
3. **Desarrollar** aplicaciones full-stack con arquitectura de microservicios
4. **Aplicar** buenas prácticas de desarrollo, documentación y seguridad
5. **Presentar** soluciones técnicas de manera clara y profesional

---

## 4. CONTENIDO DEL CURSO

### Clase Introductoria - Jueves 7 nov
**Tema:** Presentación del Proyecto

**Contenido:**
- Introducción al problema de publicación multi-red social
- Arquitectura general del sistema
- Componentes: LLM, APIs, Backend, Frontend
- Calendario y sistema de evaluación
- Asignación del proyecto

**Material:**
- PROYECTO-REDES-SOCIALES.md
- TAREAS-Y-ENTREGABLES.md
- Links a documentación de APIs

**Sin entregables**

---

### Clase 1 - Martes 12 nov
**Tema:** Investigación de APIs y Selección de Stack

**Objetivos:**
- Investigar y comparar APIs de redes sociales
- Seleccionar modelo LLM apropiado
- Diseñar arquitectura del sistema
- Definir stack tecnológico

**Contenido:**
- Meta Business API (Facebook + Instagram)
- LinkedIn Share API
- TikTok Content Posting API
- WhatsApp Business API (Twilio vs Meta)
- Comparativa de LLMs (GPT, Claude, Llama)
- Arquitectura de microservicios
- Diseño de base de datos

**Entregables:**
- **Exposición (40%):** Presentación de investigación (15 min)
- **Documento (60%):** Investigación completa (PDF/MD, 5-10 páginas)
  - Investigación de APIs (40%)
  - Tabla de características de redes (30%)
  - Selección de LLM (20%)
  - Propuesta de arquitectura (10%)

**Evaluación:** 10% de la nota final

---

### Clase 2 - Jueves 14 nov
**Tema:** Prototipo de Adaptación con LLM

**Objetivos:**
- Implementar sistema de adaptación de contenido
- Diseñar prompts para cada red social
- Validar transformaciones de texto

**Contenido:**
- Prompt engineering para redes sociales
- Integración con API de LLM elegida
- Diseño de prompts system
- Validación de límites de caracteres
- Manejo de errores del LLM

**Entregables:**
- **Exposición (40%):** Demo de adaptación (15 min)
- **Código + Demo (60%):**
  - Sistema de adaptación funcionando
  - API/módulo que transforma contenido para 5 redes
  - Documentación de prompts
  - 3 casos de prueba demostrados
  - Repositorio Git con código

**Evaluación:** 10% de la nota final

---

### Clase 3 - Martes 19 nov
**Tema:** Integración con APIs - Parte 1 (Meta + LinkedIn)

**Objetivos:**
- Publicar contenido en Facebook
- Publicar contenido en Instagram
- Publicar contenido en LinkedIn
- Implementar manejo robusto de errores

**Contenido:**
- Meta Graph API: autenticación y publicación
- Instagram: Container creation flow
- LinkedIn Share API
- OAuth 2.0 implementation
- Rate limiting y reintentos
- Logging estructurado

**Entregables:**
- **Exposición (40%):** Proceso de integración (15 min)
- **Código + Demo (60%):**
  - Facebook funcionando (mínimo 1 post real)
  - Instagram funcionando (mínimo 1 post real)
  - LinkedIn funcionando (mínimo 1 post real)
  - Endpoints para publicación
  - Manejo de errores implementado
  - Sistema de logs
  - Guía de setup de apps

**Evaluación:** 15% de la nota final

---

### Clase 4 - Jueves 21 nov
**Tema:** Integración con APIs - Parte 2 (TikTok + WhatsApp) + Backend

**Objetivos:**
- Completar integración de redes sociales
- Implementar backend central con BD
- Sistema de colas para publicaciones
- API REST completa

**Contenido:**
- TikTok Content Posting (o alternativa)
- WhatsApp Business API (Twilio)
- Base de datos (PostgreSQL/MongoDB)
- Sistema de colas (Redis + Bull/Celery)
- API REST para orquestación
- Flujo end-to-end completo

**Entregables:**
- **Exposición (40%):** Arquitectura completa (20 min)
- **Código + Demo (60%):**
  - TikTok funcionando (mínimo caption)
  - WhatsApp funcionando (mínimo 3 mensajes)
  - Base de datos con migrations
  - API REST implementada
  - Sistema de colas funcionando
  - Demo de flujo completo: crear post ’ adaptar ’ publicar

**Evaluación:** 15% de la nota final

---

### Clase 5 - Martes 26 nov
**Tema:** Portal Web y Sistema Completo

**Objetivos:**
- Implementar interfaz web
- Integrar todos los componentes
- Sistema funcionando end-to-end
- Preparación para presentación final

**Contenido:**
- Frontend con React
- Páginas: Crear, Preview, Dashboard
- Integración frontend-backend
- UX para preview de adaptaciones
- Monitoreo de estado de publicaciones
- Refinamiento del sistema completo

**Entregables:**
- **Exposición (40%):** Demo del portal (20 min)
- **Código + Demo (60%):**
  - Portal web completo y funcional
  - 3 páginas implementadas
  - Las 5 redes publicando correctamente
  - Documentación completa (README, API docs, SETUP)
  - Video demo de 2-3 min
  - Sistema listo para presentación final

**Evaluación:** 10% de la nota final

---

### Clase 6 - Jueves 28 nov
**PRESENTACIÓN FINAL**

**Formato:**
- **Presentación técnica (25 min):**
  - Introducción al problema
  - Arquitectura y tecnologías
  - Componente LLM
  - Integraciones con APIs
  - Backend y orquestación

- **Demo en VIVO (20 min):**
  - Crear publicación en portal
  - Generar adaptaciones con LLM
  - Publicar en las 5 redes
  - Verificar publicaciones en cada plataforma
  - Mostrar dashboard

- **Challenges y Aprendizajes (10 min)**
- **Q&A (5 min)**

**Entregables:**
- Sistema completo funcionando
- Repositorio Git con todo el código
- Documentación completa
- Video demo (2-3 min)
- Slides de presentación

**Evaluación:** 40% de la nota final
- Funcionalidad: 20%
- Calidad código: 5%
- Documentación: 5%
- Presentación: 10%

---

## 5. METODOLOGÍA

### 5.1 Estrategias Didácticas

**Aprendizaje Basado en Proyectos:**
- Proyecto único desarrollado incrementalmente
- Cada clase construye sobre la anterior
- Entregables tangibles semanalmente

**Learning by Doing:**
- 60% del tiempo en implementación
- Demos en vivo obligatorias
- Experimentación con tecnologías reales

**Peer Learning:**
- Discusiones grupales de soluciones
- Compartir challenges y soluciones
- Retroalimentación constructiva

### 5.2 Estructura de Clases

**Antes de clase:**
- Lectura de material asignado
- Investigación previa
- Setup de ambiente

**Durante clase:**
- Exposiciones de estudiantes (40%)
- Demos en vivo (60%)
- Discusión de challenges
- Retroalimentación del docente

**Después de clase:**
- Desarrollo del siguiente entregable
- Consultas asíncronas
- Documentación del progreso

---

## 6. EVALUACIÓN

### 6.1 Sistema de Calificación

**Clases 1-5 (60% total):**

| Clase | Peso | Componentes |
|-------|------|-------------|
| Clase 1 | 10% | Exposición (4%) + Investigación (6%) |
| Clase 2 | 10% | Exposición (4%) + Código/Demo (6%) |
| Clase 3 | 15% | Exposición (6%) + Código/Demo (9%) |
| Clase 4 | 15% | Exposición (6%) + Código/Demo (9%) |
| Clase 5 | 10% | Exposición (4%) + Código/Demo (6%) |

**Presentación Final (40% total):**

| Componente | Peso | Criterios |
|------------|------|-----------|
| Funcionalidad | 20% | Sistema completo funcionando, las 5 redes publicando |
| Calidad código | 5% | Código limpio, organizado, buenas prácticas |
| Documentación | 5% | README, API docs, guías de setup completas |
| Presentación | 10% | Claridad, estructura, demo exitoso, Q&A |

### 6.2 Criterios de Evaluación por Clase

**Exposición (40% de cada clase):**
- Claridad y organización: 15%
- Profundidad técnica: 15%
- Manejo de preguntas: 10%

**Código/Demo (60% de cada clase):**
- Funcionalidad correcta: 30%
- Calidad del código: 15%
- Demo en vivo exitoso: 10%
- Documentación: 5%

### 6.3 Escala de Calificación

- **90-100:** Excelente - Supera expectativas
- **80-89:** Muy bueno - Cumple todas las expectativas
- **70-79:** Bueno - Cumple expectativas básicas
- **60-69:** Suficiente - Cumple mínimos
- **<60:** Insuficiente - No cumple requisitos

### 6.4 Políticas de Entrega

**Puntualidad:**
- Las exposiciones son en el horario de clase (no hay prórroga)
- El código debe estar en Git antes de la clase
- Demos deben ejecutarse en tiempo real

**Integridad Académica:**
- Trabajo individual obligatorio
- Se permite consultar documentación y recursos
- Copiar código de otros estudiantes = 0 puntos
- Uso de IA para generar código debe ser documentado

**Asistencia:**
- Asistencia obligatoria a todas las clases
- Más de 2 faltas = reprobación automática
- Las exposiciones no se pueden recuperar

---

## 7. RECURSOS

### 7.1 Recursos Obligatorios

**Documentación del Proyecto:**
- PROYECTO-REDES-SOCIALES.md
- TAREAS-Y-ENTREGABLES.md
- Material en `/lectures`

**Documentación de APIs:**
- Meta Graph API: https://developers.facebook.com/docs/graph-api
- LinkedIn API: https://docs.microsoft.com/en-us/linkedin/
- TikTok API: https://developers.tiktok.com/
- WhatsApp Business: https://developers.facebook.com/docs/whatsapp
- Twilio: https://www.twilio.com/docs/whatsapp

**Documentación de LLMs:**
- OpenAI: https://platform.openai.com/docs
- Anthropic: https://docs.anthropic.com
- Ollama: https://ollama.ai

### 7.2 Herramientas Necesarias

**Software:**
- Editor: VS Code (recomendado)
- Control de versiones: Git + GitHub/GitLab
- Testing: Postman o Insomnia
- Containers: Docker (opcional)

**Cuentas:**
- GitHub/GitLab (gratuito)
- Meta for Developers (gratuito)
- LinkedIn Developers (gratuito)
- OpenAI (de pago, créditos gratis iniciales)
- Twilio (sandbox gratuito)

### 7.3 Bibliografía Recomendada

**Artículos Académicos:**
- Brown et al. (2020) - "Language Models are Few-Shot Learners"
- Lewis et al. (2020) - "Retrieval-Augmented Generation"
- Wei et al. (2022) - "Chain-of-Thought Prompting"

**Libros:**
- "Designing Data-Intensive Applications" - Martin Kleppmann
- "Building Microservices" - Sam Newman
- "The Pragmatic Programmer" - Hunt & Thomas

**Recursos Online:**
- Anthropic Prompt Library
- OpenAI Cookbook
- FastAPI/NestJS Official Docs

---

## 8. POLÍTICAS DEL CURSO

### 8.1 Código de Conducta

**Respeto:**
- Trato respetuoso entre todos
- Feedback constructivo en discusiones
- No discriminación de ningún tipo

**Integridad:**
- Trabajo individual honesto
- Citar fuentes apropiadamente
- No plagio de código

**Profesionalismo:**
- Puntualidad en entregas y asistencia
- Comunicación clara y oportuna
- Preparación adecuada para clases

### 8.2 Comunicación

**Canales:**
- Email: [Definir]
- Horario de consultas: [Definir]
- [Plataforma de comunicación]: [Definir]

**Tiempos de respuesta:**
- Email: 24-48 horas
- Durante horario de consultas: Inmediato

### 8.3 Casos Especiales

**Problemas técnicos:**
- Si una API no es accesible: Documentar intento y proponer alternativa
- Si el LLM falla: Tener plan B (screenshots, respuestas pre-generadas)
- Si la demo falla: Tener video/screenshots de respaldo

**Situaciones especiales:**
- Problemas de salud: Contactar inmediatamente
- Emergencias: Evaluación caso por caso
- Problemas de acceso a herramientas: Solicitar ayuda temprano

---

## 9. CALENDARIO DETALLADO

| Semana | Fecha | Día | Actividad | Entregable |
|--------|-------|-----|-----------|------------|
| 1 | 07 nov | J | Clase Introductoria | - |
| 2 | 12 nov | M | Clase 1: Investigación | Documento investigación |
| 2 | 14 nov | J | Clase 2: Prototipo LLM | Sistema adaptación |
| 3 | 19 nov | M | Clase 3: APIs Meta+LI | 3 redes funcionando |
| 3 | 21 nov | J | Clase 4: TikTok+WA+BE | Sistema end-to-end |
| 4 | 26 nov | M | Clase 5: Portal Web | Sistema completo |
| 4 | 28 nov | J | Presentación Final | Proyecto + docs |

---

## 10. RESULTADOS DE APRENDIZAJE ESPERADOS

Al completar exitosamente este curso, los estudiantes habrán:

1. **Desarrollado** un sistema full-stack completo con arquitectura de microservicios
2. **Integrado** al menos 4 APIs de terceros (Meta, LinkedIn, WhatsApp, y TikTok o alternativa)
3. **Implementado** un sistema de adaptación de contenido usando LLM
4. **Aplicado** buenas prácticas de desarrollo (Git, documentación, seguridad)
5. **Demostrado** capacidad de presentar soluciones técnicas profesionalmente

---

## 11. CAMBIOS AL SYLLABUS

Este syllabus puede ser modificado durante el curso si es necesario. Cualquier cambio será comunicado oportunamente a los estudiantes.

**Última actualización:** 7 de noviembre de 2025

---

**Firma del Docente:** ___________________

**Fecha:** ___________________

---

¡Bienvenidos al curso! =€
