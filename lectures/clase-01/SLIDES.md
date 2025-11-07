# Slides · Clase 1 — Introducción al Proyecto
## Sistema Multi-Red Social con LLM

**Fecha:** Jueves 7 de noviembre de 2025

---

## Slide 1 · Bienvenida
- **Curso:** Tópicos Avanzados — LLM Applications
- **Proyecto:** Sistema de Publicación Multi-Red Social
- **Duración:** 6 clases + presentación final
- **Modalidad:** Trabajo individual

---

## Slide 2 · El Problema Real
**Escenario:**
- Portal de noticias que publica en 5 redes sociales
- Facebook, Instagram, LinkedIn, TikTok, WhatsApp

**Problema actual:**
- ⏱️ Adaptar contenido manualmente toma mucho tiempo
- 📝 Cada red tiene formato, tono y límites diferentes
- ⚠️ Riesgo de inconsistencias entre plataformas
- 🔄 Proceso tedioso y repetitivo

---

## Slide 3 · La Solución
**Sistema automatizado que:**

1. 📄 Recibe una noticia original
2. 🤖 LLM adapta el contenido para cada red
3. 📤 Publica automáticamente en las 5 plataformas
4. 📊 Registra y monitorea estado de publicaciones

**Valor:**
- ⚡ Ahorro de tiempo (80-90%)
- ✅ Consistencia en el mensaje
- 🎯 Optimización por plataforma
- 📈 Escalabilidad

---

## Slide 4 · Arquitectura del Sistema
```
┌─────────────┐
│ Portal Web  │
│ (React/Vue) │
└──────┬──────┘
       │
       ▼
┌──────────────────┐      ┌─────────┐
│  Backend Central │─────▶│   LLM   │
│ (FastAPI/NestJS) │      │ Service │
└────┬─────────────┘      └─────────┘
     │
     ├──▶ Facebook API
     ├──▶ Instagram API
     ├──▶ LinkedIn API
     ├──▶ TikTok API
     └──▶ WhatsApp API
```

---

## Slide 5 · Componentes Técnicos

**1. Motor LLM**
- Adaptación de contenido (tono, longitud, hashtags)
- OpenAI, Claude, o Llama (Ollama)

**2. APIs de Redes Sociales**
- Meta Business (FB + IG)
- LinkedIn, TikTok, WhatsApp

**3. Backend**
- PostgreSQL, Redis, API REST

**4. Frontend**
- Portal para crear y gestionar publicaciones

---

## Slide 6 · Diferencias entre Redes

| Red | Max Chars | Tono | Hashtags | Especial |
|-----|-----------|------|----------|----------|
| Facebook | 63,206 | Casual/Formal | Opcional | Texto largo |
| Instagram | 2,200 | Visual | ⭐⭐⭐ | Imagen principal |
| LinkedIn | 3,000 | Profesional | Moderado | Corporativo |
| TikTok | 2,200 | Joven/Viral | ⭐⭐⭐ | Requiere video |
| WhatsApp | 65,536 | Directo | Raro | Conversacional |

---

## Slide 7 · Ejemplo de Adaptación

**Contenido original:**
> "Lanzamos nueva funcionalidad de reportes avanzados en la plataforma"

**Facebook:** 🎉 ¡Gran noticia! Lanzamos reportes avanzados en nuestra plataforma...

**LinkedIn:** Nos complace anunciar el lanzamiento de nuestra nueva funcionalidad de reportes avanzados...

**Instagram:** ✨ Nueva función desbloqueada 📊 Reportes avanzados ya disponibles! #Tech #Innovation

**TikTok:** ¿Viste lo nuevo? 🔥 Reportes que te van a volar la cabeza 🤯 #TechTok

**WhatsApp:** Hola! 👋 Te cuento: acabamos de lanzar reportes avanzados...

---

## Slide 8 · Calendario del Curso

| Fecha | Tema | Entregable |
|-------|------|------------|
| **Hoy - 7 nov** | Intro | - |
| **12 nov** | Investigación | Documento + Comparativa |
| **14 nov** | LLM Prototype | Sistema adaptación |
| **19 nov** | APIs (1) | FB + IG + LinkedIn |
| **21 nov** | APIs (2) | TikTok + WhatsApp + Backend |
| **26 nov** | Frontend | Portal completo |
| **28 nov** | **FINAL** | Sistema + Demo |

---

## Slide 9 · Estructura de Entregables

**Cada clase:**

**1. Exposición (40%)**
- 10-20 minutos de presentación
- Conceptos investigados
- Decisiones técnicas
- Challenges y soluciones

**2. Código/Demo (60%)**
- Repositorio Git actualizado
- Código funcional
- Demo en vivo
- README documentado

---

## Slide 10 · Criterios de Evaluación

**Por clase (60% total):**
- Investigación: 10%
- Implementación: 30%
- Demo en vivo: 15%
- Documentación: 5%

**Presentación final (40%):**
- Funcionalidad: 20%
- Calidad código: 5%
- Documentación: 5%
- Presentación: 10%

---

## Slide 11 · Tarea para el Martes 12 nov

**Entregable: Documento de Investigación**

**4 partes:**

1. **Investigación de APIs (40%)**
   - Meta, LinkedIn, TikTok, WhatsApp
   - Requisitos, permisos, limitaciones

2. **Tabla de Características (30%)**
   - Detalles de cada red social

3. **Selección de LLM (20%)**
   - Comparar modelos y elegir uno

4. **Propuesta de Arquitectura (10%)**
   - Diagrama + stack tecnológico

---

## Slide 12 · APIs a Investigar

**Meta Business API**
- Facebook + Instagram
- Graph API
- OAuth 2.0

**LinkedIn Share API**
- Publicación de contenido
- Autenticación

**TikTok Content Posting API**
- ⚠️ Puede tener restricciones
- Plan B requerido

**WhatsApp Business API**
- Twilio (recomendado) vs Meta
- Sandbox gratuito disponible

---

## Slide 13 · Opciones de LLM

| Modelo | Costo | Calidad | Acceso | Uso |
|--------|-------|---------|--------|-----|
| GPT-4o-mini | $$ | ⭐⭐⭐⭐⭐ | API | Producción |
| GPT-3.5 | $ | ⭐⭐⭐⭐ | API | Desarrollo |
| Claude Sonnet | $$ | ⭐⭐⭐⭐⭐ | API | Producción |
| Llama 3.1 | Gratis | ⭐⭐⭐ | Local | Demo |

**Recomendación:** Empieza con Ollama (gratis), migra a OpenAI para producción

---

## Slide 14 · Stack Tecnológico Sugerido

**Backend:**
- Python (FastAPI) o Node.js (NestJS)

**Base de datos:**
- PostgreSQL o MongoDB

**Colas:**
- Redis + Bull/Celery

**Frontend:**
- React + Tailwind CSS

**LLM:**
- OpenAI/Claude API o Ollama local

---

## Slide 15 · Recursos Entregados

📄 **PROYECTO-REDES-SOCIALES.md**
- Documento completo del proyecto
- Plan detallado clase por clase
- Criterios de evaluación
- Checklist final

📎 **Links útiles:**
- Documentación de APIs
- Tutoriales de LLM
- Herramientas de desarrollo

---

## Slide 16 · Preguntas Frecuentes

**P: ¿Las APIs son gratuitas?**
R: Meta y LinkedIn sí. OpenAI tiene costo (pero hay créditos gratis). WhatsApp con Twilio tiene sandbox gratis.

**P: ¿Qué pasa si no puedo acceder a TikTok API?**
R: Documenta el intento y al menos genera el caption optimizado.

**P: ¿Repositorio público o privado?**
R: Como prefieras, pero comparte acceso con el docente.

**P: ¿Puedo usar otro lenguaje/framework?**
R: Sí, pero justifica tu elección técnicamente.

---

## Slide 17 · Tips para el Éxito

✅ **Empieza simple:** No intentes perfección desde día 1

✅ **Commitea frecuentemente:** Git es tu amigo

✅ **Documenta todo:** README, comentarios, decisiones

✅ **Prueba temprano:** No esperes al último día

✅ **Usa .env:** NUNCA hagas commit de API keys

⚠️ **No dejes todo para el final**

---

## Slide 18 · Para la Próxima Clase

**Traer:**
- ✅ Documento de investigación completo (PDF o MD)
- ✅ Decisión de stack tecnológico
- ✅ Ambiente de desarrollo instalado
- ✅ Cuentas creadas en plataformas de desarrolladores

**Formato:**
- Exposición de 15 min por estudiante
- Discusión grupal de hallazgos
- Preparación para empezar a codear

---

## Slide 19 · Contacto y Soporte

**Documentación del proyecto:**
`/PROYECTO-REDES-SOCIALES.md`

**Recursos adicionales:**
- Meta Graph API Explorer
- OpenAI Playground
- Postman para testing

**Dudas:** [Definir canal de comunicación]

---

## Slide 20 · ¡Manos a la Obra!

🚀 **Próximos pasos:**
1. Leer `PROYECTO-REDES-SOCIALES.md` completo
2. Revisar documentación de APIs
3. Crear cuentas de desarrollador
4. Empezar investigación
5. Preparar documento para el martes

**¡Éxito con el proyecto!** 🎯

---

## Discusión Final (si hay tiempo)

**Preguntas para reflexionar:**

1. ¿Qué red social creen que será más difícil de integrar? ¿Por qué?

2. ¿Qué aspectos del contenido son más críticos al adaptar entre redes?

3. ¿Qué riesgos ven en automatizar publicaciones?

4. ¿Cómo medirían el éxito de las adaptaciones del LLM?
