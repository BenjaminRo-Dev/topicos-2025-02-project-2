# Clase 1 · Introducción al Proyecto
## Sistema Multi-Red Social con LLM

**Fecha:** Jueves 7 de noviembre de 2025

---

## Propósito de la sesión
- Presentar el proyecto del curso: adaptación automática de contenido para redes sociales
- Entender el problema que resolveremos y su valor real
- Conocer la estructura del curso y los entregables
- Asignar el proyecto y definir expectativas

## Objetivos de aprendizaje
- Comprender qué es un sistema de publicación multi-red social
- Identificar los componentes técnicos necesarios (LLM, APIs, Backend)
- Conocer las características de cada red social y sus diferencias
- Planificar el trabajo para las próximas 6 clases

---

## El Problema Real

**Escenario:** Una organización tiene un portal de noticias y necesita publicar contenido en 5 redes sociales:
- Facebook
- Instagram
- LinkedIn
- TikTok
- WhatsApp

**Problema actual:**
- Adaptar manualmente el contenido para cada red toma mucho tiempo
- Cada red tiene formato, tono y límites diferentes
- Riesgo de inconsistencias entre plataformas
- Proceso tedioso y propenso a errores

**Solución propuesta:**
Un sistema automatizado que:
1. Recibe una noticia/contenido original
2. Usa LLM para adaptar el contenido al formato de cada red
3. Publica automáticamente en las 5 plataformas
4. Registra y monitorea el estado de cada publicación

---

## Componentes del Sistema

### 1. Motor LLM (Adaptación de Contenido)
**¿Qué hace?**
- Transforma el contenido original al formato de cada red
- Ajusta tono, longitud, hashtags, emojis
- Genera sugerencias de imágenes (opcional)

**Tecnologías:**
- OpenAI API (GPT-4o-mini, GPT-3.5)
- Claude API
- Ollama (local, gratis)
- LangChain para orquestación

### 2. Integración con APIs de Redes Sociales
**¿Qué hace?**
- Publica contenido en cada plataforma
- Maneja autenticación y permisos
- Gestiona rate limiting y errores

**APIs necesarias:**
- Meta Business API (Facebook + Instagram)
- LinkedIn Share API
- TikTok Content Posting API
- WhatsApp Business API (Twilio o Meta)

### 3. Backend y Orquestación
**¿Qué hace?**
- Coordina el flujo completo
- Base de datos para gestión de publicaciones
- Sistema de colas para publicaciones asíncronas
- API REST para el frontend

**Tecnologías:**
- Backend: FastAPI (Python) o NestJS (Node.js)
- Base de datos: PostgreSQL o MongoDB
- Colas: Redis + Bull/Celery
- Docker para deployment

### 4. Portal Web
**¿Qué hace?**
- Interfaz para crear publicaciones
- Preview de contenido adaptado
- Dashboard de estado de publicaciones

**Tecnologías:**
- React o Vue.js
- Tailwind CSS
- Axios para HTTP

---

## Características de Cada Red Social

| Red Social | Max Caracteres | Tono | Hashtags | Emojis | Especial |
|------------|---------------|------|----------|--------|----------|
| **Facebook** | 63,206 | Casual/Formal | Opcional | ✅ Sí | Links, texto largo |
| **Instagram** | 2,200 | Visual/Casual | Muy importante | ✅ Sí | Imagen principal |
| **LinkedIn** | 3,000 | Profesional | Moderado | ⚠️ Poco | Tono corporativo |
| **TikTok** | 2,200 | Joven/Trending | Importante | ✅ Sí | Requiere video |
| **WhatsApp** | 65,536 | Directo | Raro | ✅ Sí | Conversacional |

---

## Calendario del Curso

**Total:** 6 clases + presentación final

| Fecha | Tema | Entregables |
|-------|------|-------------|
| **Hoy - 7 nov** | Clase Introductoria | - |
| **12 nov** | Investigación de APIs + LLM | Documento de investigación + Tabla comparativa |
| **14 nov** | Prototipo LLM | Sistema de adaptación funcionando + Demo |
| **19 nov** | APIs Meta + LinkedIn | Publicaciones en 3 redes + Código |
| **21 nov** | TikTok + WhatsApp + Backend | Sistema end-to-end + API REST |
| **26 nov** | Portal Web + Sistema Completo | UI funcionando + Las 5 redes |
| **28 nov** | **PRESENTACIÓN FINAL** | Sistema completo + Documentación |

---

## Estructura de Entregables

### Cada clase tendrá 2 componentes:

#### 1. Exposición (40%)
- Presentación de 10-20 minutos
- Explicar conceptos investigados
- Mostrar decisiones técnicas
- Discutir challenges encontrados

#### 2. Código/Demo (60%)
- Repositorio Git actualizado
- Código funcional del componente de la clase
- Demo en vivo
- Documentación básica (README)

### Criterios de evaluación por clase:
- **Investigación:** Profundidad y calidad de la investigación (10%)
- **Implementación:** Código funcionando correctamente (30%)
- **Demo:** Demostración en vivo exitosa (15%)
- **Documentación:** Claridad del código y README (5%)

---

## Tarea para la Próxima Clase (Martes 12 nov)

### Entregable: Documento de Investigación

**Parte 1: Investigación de APIs (40%)**

Investigar y documentar:

1. **Meta Business API (Facebook + Instagram)**
   - ¿Cómo crear una app de desarrollador?
   - ¿Qué permisos se necesitan?
   - ¿Cuáles son los rate limits?
   - ¿Cómo funciona la autenticación?

2. **LinkedIn Share API**
   - Requisitos de acceso
   - Proceso de autenticación
   - Limitaciones

3. **TikTok Content Posting API**
   - ¿Es accesible para desarrollo académico?
   - ¿Requiere verificación?
   - Plan B si no es viable

4. **WhatsApp Business API**
   - Comparar: Twilio vs Meta
   - Costos (si aplica)
   - Facilidad de setup

**Parte 2: Características de Redes Sociales (30%)**

Completar tabla detallada con:
- Límites de caracteres
- Tono recomendado
- Uso de hashtags
- Formato especial
- Mejores prácticas

**Parte 3: Selección de LLM (20%)**

Comparar modelos:
- OpenAI (GPT-4o-mini, GPT-3.5)
- Claude (Sonnet, Haiku)
- Llama 3.1 (Ollama local)

Elegir uno y justificar.

**Parte 4: Propuesta de Arquitectura (10%)**

- Diagrama de arquitectura del sistema
- Stack tecnológico elegido
- Diseño preliminar de base de datos

### Formato de entrega:
- **Documento:** PDF o Markdown
- **Extensión:** 5-10 páginas
- **Incluir:** Fuentes, capturas de pantalla, diagramas
- **Subir a:** Repositorio Git personal

---

## Material de Apoyo

### Documentación de APIs
- [Meta Graph API](https://developers.facebook.com/docs/graph-api)
- [LinkedIn API](https://docs.microsoft.com/en-us/linkedin/)
- [TikTok API](https://developers.tiktok.com/)
- [WhatsApp Business API](https://developers.facebook.com/docs/whatsapp)
- [Twilio WhatsApp](https://www.twilio.com/docs/whatsapp)

### LLM Resources
- [OpenAI Platform](https://platform.openai.com/docs)
- [Anthropic Claude](https://docs.anthropic.com)
- [Ollama](https://ollama.ai)
- [LangChain](https://python.langchain.com/)

### Herramientas
- [Postman](https://www.postman.com/) - Para probar APIs
- [ngrok](https://ngrok.com/) - Para webhooks en desarrollo
- [Meta Graph API Explorer](https://developers.facebook.com/tools/explorer)

---

## Recursos Entregados Hoy

1. **PROYECTO-REDES-SOCIALES.md** - Documento completo del proyecto
2. **Estas slides** - Presentación de la clase introductoria
3. **Links de documentación** - Recursos para empezar a investigar

---

## Preguntas Frecuentes

**P: ¿Necesito pagar por las APIs?**
R: Depende. OpenAI tiene costo (pero hay crédito gratis inicial). Meta, LinkedIn son gratuitas para desarrollo. WhatsApp con Twilio tiene sandbox gratis.

**P: ¿Qué pasa si no puedo acceder a alguna API?**
R: Documenta el intento y propón alternativa (ej: para TikTok, al menos genera el caption).

**P: ¿Puedo usar otro stack tecnológico?**
R: Sí, pero justifica tu elección en la investigación.

**P: ¿Trabajo solo o en equipo?**
R: Individual. Cada estudiante desarrolla su propio sistema completo.

**P: ¿Dónde subo el código?**
R: GitHub o GitLab. Repositorio público o privado (compartir acceso con el docente).

---

## Próxima Clase (Martes 12 nov)

**Tema:** Investigación de APIs y Estrategia de Adaptación de Contenido

**Qué traer:**
- Documento de investigación completo
- Decisión de stack tecnológico
- Ambiente de desarrollo preparado (Node.js o Python)
- Cuentas creadas en plataformas de desarrolladores

**Formato:**
- Exposición de investigación (15 min por estudiante)
- Discusión grupal de hallazgos
- Preparación para empezar a codear

---

## Contacto

**Proyecto en:** `/PROYECTO-REDES-SOCIALES.md`

---

¡Éxito con la investigación! 🚀
