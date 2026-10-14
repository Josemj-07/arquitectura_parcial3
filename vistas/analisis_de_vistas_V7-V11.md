# Resumen de las vistas V7 a V11 — SGMF AeroAgro Drones

Este documento resume qué muestra cada una de las vistas  del modelo en Archi y por qué se tomaron las decisiones principales.


---

## V7 — Lenguaje ubicuo (ArchiMate de negocio)

**Objetivo:** mostrar los términos del negocio y qué significan en cada contexto, para que todos hablen el mismo idioma.

**Análisis**
- Se tomaron los términos de la entrevista para los 9 contextos. El glosario completo tiene 105 términos y queda en la carpeta Business del modelo.
- Se encontraron 7 **homónimos**, palabras que cambian de significado según el contexto. Ejemplo: «ciclo» es un despegue y un aterrizaje para Registro de uso, pero una descarga y recarga de batería para Configuración de flota.
- La entrevista dice dónde se registra hoy cada dato (formatos FM-01 a FM-06, el Excel maestro, Siigo, carpetas). Eso permitió usar el elemento **representación** con información real.

**Decisiones**
- Se usan los tres elementos de la vista:
  - **Objeto de negocio:** el término.
  - **Significado:** qué quiere decir.
  - **Representación:** cómo se ve o se registra.
- Se agregaron 25 significados y 12 representaciones. Las representaciones se unen al término con «representa» y los significados con «significa».
- **V7.1 Términos clave:** uno o dos términos por contexto, cada uno en su grupo. Cada fila se lee así: representación → término → significado.
- **V7.2 Homónimos:** un grupo por palabra, con el término y el significado en cada uno de sus dos contextos.
- Tres representaciones son a futuro: el tablero de estado, el libro en PDF y las notificaciones. Lo indica su propiedad «Momento».
- Los homónimos llevan **borde rojo** y el relleno de cada término sigue la clasificación de su contexto.

---

## V8 — Mapa de contextos (ArchiMate de aplicaciones)

**Objetivo:** mostrar cómo se relacionan los 9 contextos entre sí y con los sistemas externos, y con qué patrón.

**Análisis**
- Las relaciones entre contextos salen de los eventos de V6. Por ejemplo, cuando Planeación publica «TareaVencida», Aeronavegabilidad pone el dron en tierra.
- A cada relación se le asignó un patrón de DDD:
  - **Socios:** se coordinan de igual a igual, como Órdenes de trabajo y Planeación.
  - **Cliente–Proveedor:** uno alimenta al otro, como Registro de uso a Configuración de flota.
  - **Conformista:** acepta el modelo del otro tal cual, como Indicadores y Notificaciones.
  - **Servicio abierto:** como la consulta de habilitación de Personal.
  - **Capa anticorrupción (ACL):** traduce a los sistemas externos (DJI, XAG, Siigo, Programación).

**Decisiones**
- **V8.1 Contextos y patrones:** los 9 contextos en tres bandas (núcleo, soporte y genérico) y los 6 sistemas externos a los lados, cerca de los contextos con que se integran. Cada flujo lleva el patrón en el nombre y un color.
- **V8.2 Interfaces y servicios:** cada contexto con sus interfaces y el servicio que expone cada una. Las líneas moradas de «servida por» muestran las consultas que usan otros contextos.
- La distribución se calculó para que las líneas fueran cortas y no tapen cajas.
- Las relaciones de ida y vuelta (por ejemplo, Órdenes de trabajo ⇄ Planeación) se dibujan como dos líneas separadas para que no se encimen.
- Indicadores y reportes no publica servicios: solo consume datos de los demás.

---

## V9 — Interoperabilidad y anticorrupción (ArchiMate de aplicaciones)

**Objetivo:** mostrar cómo el SGMF se integra con lo que está fuera de él y cómo se protege de los modelos externos.

**Análisis**
- El modelo ya tenía los servicios de interoperabilidad de la capa 5, pero faltaba ver qué interfaz y qué servicio de aplicación los hacían realidad.
- Hay 18 integraciones con 15 contrapartes:
  - 6 sistemas externos;
  - 3 áreas internas (Agronomía, Finanzas y SST);
  - 6 entidades sin API (Aerocivil, ICA, aseguradora, clientes, gestor de residuos y distribuidores).

**Decisiones**
- Los dos diagramas se leen de izquierda a derecha en cuatro columnas: contraparte ⇄ flujo ⇄ contexto, que se compone de una interfaz, y la interfaz expone un servicio.
- **V9.1 Sistemas externos:** DJI, XAG, Siigo, Programación, Excel de talento humano y Google Workspace.
- **V9.2 Áreas internas y entidades sin API:** el intercambio se hace por pantalla, documento o correo.
- Las contrapartes sin sistema propio se modelaron como **actores de negocio** y no como componentes externos, para no inventar sistemas que no existen.
- **Inferencia:** a reguladores, aseguradora y clientes se les asignó el patrón Conformista, porque el SGMF entrega el documento en el formato que ellos piden.
- Lo que entra de un sistema externo pasa por un adaptador anticorrupción (ACL); hacia Programación se publica una interfaz abierta (OHS).
- Los colores de los flujos son los mismos de V8, para que el patrón se reconozca igual en las dos vistas.

---

## V10 — Trazabilidad vertical

**Objetivo:** demostrar que cada meta del negocio llega hasta un componente del software y que cada componente sirve a alguna meta.

**Análisis**
- V1 y V2 ya tenían metas, resultados, requisitos, cursos de acción y capacidades, pero la cadena se cortaba antes de llegar al software:
  - los requisitos los cumplía «el SGMF completo», sin decir qué contexto se encargaba;
  - las capacidades no tenían ninguna función de negocio que las llevara a cabo.
- La entrevista, al preguntar «en qué punto entraría la digitalización», relaciona casi uno a uno cada requisito con un contexto.

**Decisiones**
- Se agregaron 35 relaciones y ningún elemento. Solo 2 relaciones son inferencia.
- La trazabilidad se separó en sus dos caminos, uno por diagrama, para que cada uno se lea de arriba abajo:
  - **V10.1 Camino de motivación:** problemas –influyen→ metas ← resultados ← requisitos y restricciones ← contextos (realización).
  - **V10.2 Camino de estrategia:** metas ← cursos de acción ← capacidades ← funciones de negocio ← contextos (realización y servicio). Los recursos se asignan a las capacidades.
- Así aparecen los cuatro tipos de relación pedidos: realización, influencia, servicio y asignación.
- Para no recargar el diagrama, los principios no se dibujaron; sus relaciones siguen en el modelo.
- Resultado: los 9 contextos llegan al menos a una meta.
- Personal habilitado no tiene requisito propio; sube a las metas por el camino de estrategia.

---

## V11 — Bounded Context Canvas (ArchiMate canvas)

**Objetivo:** resumir en una página el diseño de un contexto, con el formato del Bounded Context Canvas de DDD Crew.

**Análisis**
- Casi todo el contenido ya estaba en las vistas anteriores:
  - propósito (V5) y lenguaje (V7);
  - mensajes (eventos y comandos de V6, servicios de V8 y V9);
  - reglas (invariantes de V6) y métricas (resultados de V1, vía V10).
- El modelo de negocio, la evolución y los roles del dominio no estaban en el modelo. Se completaron como **inferencia** y quedaron marcados así.

**Decisiones**
- Se hicieron dos canvas, ambos de contextos núcleo:
  - **V11.1 Aeronavegabilidad:** responde la pregunta central del negocio, «¿este dron puede volar hoy?».
  - **V11.2 Planeación:** concentra las reglas propias de la empresa.
- Elementos elegidos y su justificación:
  - el componente de aplicación representa el contexto;
  - eventos, servicios, procesos y eventos de negocio representan los mensajes;
  - las restricciones son las decisiones de negocio;
  - los resultados son las métricas;
  - las notas guardan los textos.
- Distribución: arriba, propósito, clasificación y roles; en el centro, el contexto, con lo que entra a la izquierda y lo que sale a la derecha; abajo, lenguaje (máximo 12 términos), decisiones, supuestos, métricas y preguntas abiertas.
- Queda pendiente definir qué rol de usuario inicia cada comando y validar las partes inferidas.
