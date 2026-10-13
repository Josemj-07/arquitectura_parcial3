# Resumen de las vistas V7 a V11 — SGMF AeroAgro Drones

Este documento resume qué se hizo en cada una de las cinco vistas (V7-V11) del modelo en Archi y por qué se tomaron las decisiones principales.

---

## V7 — Lenguaje ubicuo (ArchiMate de negocio)

**Objetivo:** reunir en un solo lugar las palabras que usa el negocio, separadas por contexto, para que todos hablen el mismo idioma.

**Análisis**
- Se revisó la entrevista y se extrajeron los términos propios de cada uno de los 9 contextos: núcleo (Aeronavegabilidad, Planeación, Configuración de flota), soporte (Registro de uso, Órdenes de trabajo, Abastecimiento) y genérico (Personal, Indicadores, Identidad y notificaciones).
- Se cruzaron con el modelo para no repetir lo que ya existía: de 105 términos, 28 ya estaban y se reutilizaron; 77 se crearon.
- Se encontraron 7 **homónimos**, es decir, palabras con distinto significado según el contexto: ciclo, contador, vencimiento, disponibilidad, servicio, inspección y traslado.
- Ejemplo: «ciclo» es un despegue y un aterrizaje para Registro de uso, pero una descarga y recarga de batería para Configuración de flota.
- También se anotaron los sinónimos que usa la gente. Por ejemplo, «estado de aeronavegabilidad» también se dice «estado del dron».

**Decisiones**
- Aunque esta vista se suele asociar al elemento Representación, la regla acordada fue modelar cada término como **objeto de negocio**. De los términos nuevos, solo 2 son **eventos de negocio**, porque describen algo que ocurre.
- Cada término lleva su definición y las propiedades Contexto, Clasificación, Sinónimos y Fuente (la cita de la entrevista).
- Los estados del dron (en tierra, fuera de servicio, disponible con restricción) también se modelaron como objetos de negocio, para que aparezcan en el glosario.
- Los homónimos se resaltan con **borde rojo**, y el relleno de cada término sigue la clasificación de su contexto.
- Cada contexto quedó en su propio grupo, y solo cruzan de un grupo a otro las relaciones entre contextos.
- Se hizo una vista general (V7.0) y una por contexto (V7.1 a V7.7). Los tres genéricos comparten la V7.7. Además se entregó un glosario en tabla.
- Los términos se relacionan con verbos sencillos, por ejemplo «tiene», «genera», «registra» o «deja el dron», para que la vista se lea como frases del negocio.

---

## V8 — Mapa de contextos (ArchiMate de aplicaciones)

**Objetivo:** mostrar cómo se relacionan los 9 contextos entre sí y con los sistemas externos, y qué tipo de relación tiene cada pareja.

**Análisis**
- Las relaciones entre contextos se dedujeron de los eventos que ya existían en V6. Por ejemplo, cuando Planeación publica «TareaVencida», Aeronavegabilidad pone el dron en tierra.
- A cada pareja se le asignó un patrón de DDD:
  - **Socios:** se coordinan de igual a igual, como Órdenes de trabajo y Planeación.
  - **Cliente–Proveedor:** uno depende del otro, como Registro de uso, que alimenta a Configuración de flota.
  - **Conformista:** acepta el modelo del otro tal cual; es el caso de Indicadores y de Notificaciones.
  - **Servicio abierto:** como la consulta de habilitación de Personal.
  - **Capa anticorrupción (ACL):** traduce el modelo externo, como con DJI, XAG, Siigo y la hoja de Programación.

**Decisiones**
- Cada contexto recibió **interfaces** y **servicios de aplicación** (14 de cada uno) para mostrar por dónde se comunica.
- Los **flujos** llevan el patrón en el nombre, por ejemplo «[C/P] uso de vuelos», y una línea de color según el patrón.
- La vista general muestra solo contextos e interfaces, para que no se sature. Los servicios aparecen en las 7 vistas de detalle.
- En cada detalle, lo que llega al contexto queda a la izquierda y lo que sale, a la derecha.
- Resultado: los contextos núcleo quedan protegidos. Lo que viene de afuera siempre pasa por una traducción (ACL) antes de entrar.

---

## V9 — Interoperabilidad y anticorrupción (ArchiMate de aplicaciones)

**Objetivo:** mostrar cómo el SGMF se integra con los sistemas y las entidades de fuera, y cómo se protege de modelos externos.

**Análisis**
- El modelo ya tenía los 10 servicios de interoperabilidad (capa 5 de V4a) con sus contratos, pero solo 4 tenían una interfaz y un servicio que los hicieran realidad.
- Se identificaron 18 integraciones con 15 contrapartes:
  - 6 con sistemas: DJI, XAG, Siigo, Programación, Excel de talento humano y Google Workspace;
  - 3 con áreas internas: Agronomía, Finanzas y SST;
  - 6 entidades sin API: Aerocivil, ICA, aseguradora, clientes, gestor de residuos y distribuidores.

**Decisiones**
- Las contrapartes que no tienen un sistema propio (Aerocivil, gestor de residuos, etc.) se modelaron como **actores de negocio** y no como componentes externos, para no inventar sistemas que no existen.
- Se crearon 7 interfaces y 8 servicios nuevos. Por ejemplo: «Exportador de evidencia en PDF», «Registro de avisos del fabricante» y «Consulta de calibración para Agronomía».
- Cada servicio se conecta con el servicio de capa 5 que cumple, para mantener la trazabilidad con V4a.
- **Inferencia:** a reguladores, aseguradora y clientes se les asignó el patrón Conformista, porque el SGMF entrega el documento en el formato que ellos piden.
- El contrato con los fabricantes se dividió en dos partes: avisos técnicos (Planeación) y taller y garantías (Órdenes de trabajo).
- Las contrapartes se separaron en tres grupos: sistemas externos, procesos internos fuera del SGMF y entidades externas sin API.
- Se hizo una vista general y una por contexto. Además se entregó un catálogo de las 18 integraciones con su protocolo y su dirección.

---

## V10 — Trazabilidad vertical

**Objetivo:** demostrar que cada meta del negocio llega hasta un componente del software, y que cada componente sirve a alguna meta.

**Análisis**
- V1 y V2 ya tenían la parte alta: metas, resultados, requisitos, cursos de acción y capacidades. Pero la cadena se cortaba en dos puntos:
  - los requisitos los cumplía «el SGMF completo», sin decir qué contexto se encargaba de cada uno;
  - las capacidades no tenían ninguna función de negocio que las llevara a cabo.
- La pregunta de la entrevista sobre «en qué punto entraría la digitalización» relacionaba casi uno a uno cada requisito con un contexto.

**Decisiones**
- No se creó ningún elemento: solo **35 relaciones nuevas**.
  - **Realización:** cada contexto cumple sus requisitos y restricciones, y cada función hace realidad una capacidad.
  - **Servicio:** cada contexto apoya a su función de negocio.
- Las relaciones de influencia (problemas → metas) y de asignación (recursos → capacidades) ya existían y se reutilizaron.
- La vista se lee de arriba abajo por dos caminos que terminan en el mismo contexto:
  - a la izquierda, el de motivación;
  - a la derecha, el de estrategia y negocio.
- Se hizo una vista general y una por cada meta (disponible, segura, normatividad, costo).
- Resultado: los 9 contextos llegan al menos a una meta. Solo 2 relaciones son inferencia.

---

## V11 — Bounded Context Canvas (ArchiMate canvas)

**Objetivo:** resumir el diseño de cada contexto en una sola página, con el formato del Bounded Context Canvas de DDD Crew.

**Análisis**
- Casi todo el contenido del canvas ya estaba en las vistas anteriores:
  - propósito (V5);
  - mensajes (eventos y comandos de V6, servicios de V8 y V9);
  - lenguaje (V7);
  - reglas o invariantes (V6);
  - métricas (resultados de V1 vía V10).
- Lo único que no estaba en el modelo eran el modelo de negocio, la evolución y los roles del dominio. Se completaron como **inferencia** y quedaron marcados así.

**Decisiones**
- Como los elementos eran de libre elección, se usaron:
  - el componente de aplicación para el contexto;
  - eventos, servicios, procesos y eventos de negocio para los mensajes;
  - restricciones para las decisiones de negocio;
  - resultados para las métricas;
  - notas para los textos.
- Se hicieron 9 canvas (V11.1 a V11.9) más una guía de lectura (V11.0).
- Cada canvas sigue la misma distribución:
  - arriba, propósito, clasificación y roles;
  - en el centro, el contexto, con lo que entra a la izquierda y lo que sale a la derecha;
  - abajo, lenguaje, decisiones, supuestos, métricas y preguntas abiertas.
- No se crearon elementos; se agregaron 116 relaciones que muestran en una página quién envía cada mensaje y quién lo recibe.
- Queda pendiente definir qué rol de usuario inicia cada comando y validar las partes inferidas.