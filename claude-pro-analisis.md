# Análisis del plan Claude Pro (Anthropic)

> Fecha de la consulta: 8 de octubre de 2026.
> Los precios, límites y modelos de este plan cambian con frecuencia. Los puntos marcados con ⚠️ son datos sobre los que las fuentes se contradicen o que no pude confirmar con certeza.

## Índice

1. [Resumen ejecutivo](#1-resumen-ejecutivo)
2. [Características exclusivas](#2-características-exclusivas)
3. [Límites de uso reales](#3-límites-de-uso-reales)
4. [Tabla comparativa: Free vs. Pro](#4-tabla-comparativa-free-vs-pro)
5. [Veredicto objetivo](#5-veredicto-objetivo)
6. [Datos no confirmados](#6-datos-no-confirmados)
7. [Fuentes](#7-fuentes)

---

## 1. Resumen ejecutivo

Pro es el plan de pago individual del chat de Claude.

- **Precio:** US$20 por mes en EE. UU., con precio en moneda local donde esté soportado. El precio varía según la región y en algunas regiones los impuestos se suman al pagar.
- **Suscripción anual:** existe. Una fuente de terceros la ubica en US$200 al año (unos US$17 por mes), pero no lo verifiqué en una página oficial.
- **Beneficios declarados por Anthropic:** acceso prioritario en horas de alto tráfico y acceso anticipado a funciones nuevas.
- **API:** el plan **no** incluye uso de la API. Ese acceso se paga aparte mediante la Consola de Anthropic.
- **Descuentos:** Anthropic no ofrece descuentos estándar ni cupones puntuales para ningún plan de pago.

Para el precio exacto en cada país, consultar claude.ai/upgrade o la tienda de aplicaciones.

---

## 2. Características exclusivas

### Modelos

| Modelo | Free | Pro |
|---|---|---|
| Haiku | Sí | Sí |
| Sonnet | Sí | Sí |
| Opus 5.5 (lanzado el 22/09/2026) | No | Sí, dentro de los límites del plan |
| Fable 5 / 5.1 | No | Solo con créditos de uso (pago por consumo) |

- **Opus 5.5** está disponible para usuarios de Pro, Max, Team y Enterprise, según la página de producto de Anthropic.
- **Fable** es la excepción importante. En Pro no entra en los límites de uso del plan y se consume con créditos de uso a tarifas de API. Una promoción que lo incluía en los límites semanales terminó el 19 de julio de 2026 a las 23:59:59 PT.
- En la práctica, el modelo más potente incluido en Pro es Opus 5.5.

### Funciones

Según la página de precios de Anthropic, Pro suma lo siguiente sobre Free:

- Claude Code (terminal, web y escritorio).
- Cowork.
- Proyectos ilimitados.
- Research (investigación de varios pasos).
- Memoria entre conversaciones (⚠️ ver [datos no confirmados](#6-datos-no-confirmados)).
- Acceso prioritario y acceso anticipado a funciones nuevas.

La versión alemana de la página de precios también lista Claude Design y Claude Science dentro de Pro.

El plan gratuito ya permite generar código, visualizar datos, crear archivos, ejecutar código y usar conectores MCP remotos. Según una fuente de terceros, Artifacts también está disponible en Free desde una actualización de febrero de 2026.

---

## 3. Límites de uso reales

Pro **no es ilimitado**. Hay dos límites que corren al mismo tiempo:

1. **Sesión de 5 horas.** Es una ventana móvil que arranca con tu primer mensaje. Anthropic la describe como al menos cinco veces el uso por sesión del plan gratuito en horas pico.
2. **Límite semanal.** Aplica a todos los modelos y se reinicia una vez por semana, en un horario fijo asignado a tu cuenta (no un lunes global).

Puntos adicionales:

- **Pool compartido:** el uso se comparte entre las apps de Claude y Claude Code.
- **No es un número fijo de mensajes.** Lo que consume cada mensaje depende de su longitud, del tamaño de la conversación, del modelo y de las herramientas usadas. Opus gasta la cuota más rápido que Sonnet o Haiku.
- **Dónde verlo:** Configuración > Uso muestra el consumo de la sesión y de la semana.
- **Al llegar al tope** hay tres opciones: esperar al reinicio, subir a Max o activar créditos de uso para seguir trabajando más allá de lo incluido.
- **Max** ofrece 5x o 20x la capacidad de Pro por sesión (desde US$100 al mes), y ambos tienen límites semanales.

### Cambios recientes

- En marzo de 2026, Anthropic confirmó que "ajustaba" los límites de sesión de cinco horas en horas pico para Free, Pro y Max, sin modificar los límites semanales.
- Según una fuente de terceros, con el lanzamiento de Opus 5.5 Anthropic subió los límites de cinco horas en Pro, Max, Team y Enterprise por asientos. No encontré la cifra exacta.

### Ventana de contexto

⚠️ **Sin certeza.** Las fuentes discrepan:

- Varias fuentes de terceros indican 200.000 tokens por conversación.
- Otras reportan que Anthropic lanzó soporte de un millón de tokens para Opus y Sonnet, y en Claude Code existen alias con contexto de 1M.
- No pude confirmar qué ventana corresponde hoy a Pro en el chat de claude.ai.

---

## 4. Tabla comparativa: Free vs. Pro

| Aspecto | Free | Pro |
|---|---|---|
| Precio | US$0 | US$20/mes (varía por región; anual más barato) |
| Modelos | Haiku y Sonnet | Haiku, Sonnet y Opus 5.5 incluidos; Fable solo con créditos |
| Uso por sesión | Base | Al menos 5x Free |
| Ventana de sesión | Móvil, de 5 h | Móvil, de 5 h |
| Límite semanal | Sí | Sí, en todos los modelos |
| Claude Code | No | Incluido (pool compartido) |
| Cowork | No | Incluido |
| Research | No | Incluido |
| Proyectos | ⚠️ Fuentes discrepan (una indica hasta 5) | Ilimitados |
| Memoria entre conversaciones | ⚠️ Fuentes discrepan | Incluida |
| Artifacts, creación de archivos, conectores MCP | Sí | Sí |
| Acceso prioritario y anticipado | No | Sí |
| Acceso a la API | No | No (se paga aparte) |
| Uso extra de pago | ⚠️ No confirmado | Sí, con créditos de uso |
| Ventana de contexto | ⚠️ No confirmada | ⚠️ No confirmada (200K vs. 1M según la fuente) |

---

## 5. Veredicto objetivo

### Tiene sentido pagarlo si...

- Usás Claude a diario y chocás con los límites del plan gratuito.
- Necesitás Opus 5.5 para razonamiento complejo, análisis largo o redacción exigente.
- Querés Claude Code, Cowork o Research y tu uso es moderado.
- Trabajás con muchos documentos organizados por proyecto.
- Preferís una tarifa fija predecible a pagar por token.

### Probablemente no te convenga si...

- Tu uso es esporádico: Free cubre chat, archivos, código y conectores.
- Necesitás la API para una aplicación: Pro no la incluye.
- Querés Fable de forma habitual: en Pro es un gasto medido aparte.
- Esperás sesiones largas de agentes de código: Max ofrece mucha más capacidad por sesión, y una fuente de terceros advierte que ese perfil puede toparse con el límite de Pro en poco tiempo.

---

## 6. Datos no confirmados

| Dato | Estado |
|---|---|
| Precio anual exacto | Solo fuente de terceros (US$200/año) |
| Ventana de contexto en Pro (chat) | Fuentes discrepan: 200K vs. 1M |
| Proyectos en Free | Una fuente indica hasta 5; versiones de la página de precios discrepan |
| Memoria en Free | Versiones de la página de precios discrepan |
| Magnitud del aumento de límites con Opus 5.5 | Sin cifra confirmada |
| Cuota exacta de mensajes en Free y Pro | Anthropic no publica un número fijo |

Antes de decidir, verificar precio local, ventana de contexto y límites actuales en [claude.ai/upgrade](https://claude.ai/upgrade) y en [support.claude.com](https://support.claude.com).

---

## 7. Fuentes

**Oficiales (Anthropic)**

- Qué es el plan Pro: https://support.claude.com/en/articles/8325606-what-is-claude-pro
- Modelos Fable en tu plan: https://support.claude.com/en/articles/15424964-claude-fable-models-on-your-plan
- Página de producto de Claude Opus: https://www.anthropic.com/claude/opus
- Precios: https://claude.com/pricing
- Guía de elección de modelo (Claude Academy): https://academy.claude.com/tutorials/choosing-the-right-claude-model

**Terceros (usadas como contraste; menor fiabilidad)**

- PCWorld, sobre ajustes de límites en marzo de 2026: https://www.pcworld.com/article/3099983/
- Fast.io, guía del plan Pro: https://fast.io/resources/claude-pro-plan-guide/
- ClaudeFa.st, Opus 5.5 y Fable 5: https://claudefa.st/blog/models/claude-opus-5-5
- Verdent, límites de uso: https://www.verdent.ai/guides/claude/usage-limits
- Zenken, Free vs. Pro: https://ai.zenken.co.jp/en/post/claude-free-vs-pro/
- UsageBar, tokens y contexto: https://usagebar.com/blog/how-many-tokens-does-claude-pro-give
