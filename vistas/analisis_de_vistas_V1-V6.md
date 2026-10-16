# Resumen de las vistas V1 a V6 — SGMF AeroAgro Drones

Este documento resume qué muestra cada una de las vistas del modelo en Archi y por qué se tomaron las decisiones principales.


---

## V1 — Motivación (ArchiMate de motivación)

**Objetivo:** explicar por qué existe el SGMF y conectarlo con lo que le importa al negocio.

**Análisis**
- Los elementos salen de la entrevista. El jefe de mantenimiento describió cuatro problemas concretos:
  - las horas registradas a mano no cuadran con la plataforma del fabricante;
  - los componentes y las baterías pierden su historia al rotar entre drones;
  - los drones se quedan parados por repuestos que nadie anticipó;
  - no hay indicadores confiables.
- La entrevista también entregó metas con cifras: disponibilidad de al menos 90 %, cumplimiento del plan preventivo de al menos 95 %, cero vuelos con mantenimiento vencido y costo máximo de 80.000 COP por hora de vuelo.
- Las restricciones vienen de la operación real: en campo no hay señal, Siigo no se reemplaza y la empresa no tiene área de TI.

**Decisiones**
- Se usan los ocho tipos de elementos de motivación: 7 interesados, 4 impulsores, 5 evaluaciones, 4 metas, 5 resultados, 3 principios, 6 requisitos y 3 restricciones.
- La vista se lee de arriba abajo: interesados → impulsores → evaluaciones (problemas) → metas ← resultados ← requisitos ← SGMF.
- Relaciones usadas:
  - **Asociación:** entre interesados, impulsores y evaluaciones.
  - **Influencia:** de los problemas hacia las metas, y de las restricciones hacia lo que condicionan.
  - **Realización:** de los resultados a las metas, de los requisitos a los resultados y del SGMF a los requisitos.
- Cada meta tiene al menos un resultado medible. Por ejemplo, la meta de normatividad se mide con «libro de mantenimiento de cualquier dron exportable en minutos», porque hoy reunir los registros para la Aerocivil toma dos días.
- Los tres principios («el estado del dron es la pieza central», «componentes y baterías tienen vida propia» y «nada se borra») resumen lo que el experto repitió como no negociable.

---

## V2 — Mapa de capacidades (ArchiMate de estrategia)

**Objetivo:** mostrar todo lo que la empresa sabe hacer y en qué capacidades impacta el sistema.

**Análisis**
- El mapa cubre la empresa completa, no solo el mantenimiento: comercial, agronomía, programación, ejecución, reporte, inventario, talento humano, SST, finanzas y TI.
- «Gestión del mantenimiento de la flota» es la capacidad que el SGMF transforma. Se descompuso en ocho subcapacidades: registro de uso, configuración y componentes, planeación preventiva, ejecución, aeronavegabilidad y liberación, baterías, taller externo y medición del desempeño.
- Otras capacidades se ven afectadas sin ser el foco. Por ejemplo, Programación recibe la disponibilidad de los drones y Agronomía consulta las calibraciones.

**Decisiones**
- 23 capacidades en tres agrupaciones: estratégicas, misionales y de apoyo. Mantenimiento quedó como misional porque es el proceso que más detiene la operación.
- Colores:
  - **Naranja fuerte:** impacto directo.
  - **Naranja claro:** impacto indirecto.
  - **Sin color:** el sistema no la toca.
- Cada capacidad de impacto indirecto tiene una relación de servicio que explica por qué lo es.
- 4 recursos (flota, repuestos, técnicos certificados y manual de tareas) se asignan a la capacidad que los usa.
- 4 cursos de acción (digitalizar, planear a 30 días, integrar con capa anticorrupción y medir el desempeño) conectan las subcapacidades con las metas de V1. Así el mapa queda justificado por la motivación, como pide el enunciado.

---

## V3 — Cadena de valor y proceso E2E (ArchiMate de negocio)

**Objetivo:** mostrar en qué momento del negocio trabaja el sistema.

**Análisis**
- El experto describió el flujo completo en diez pasos, desde que el cliente pide la aplicación hasta que paga.
- Dijo también que el mantenimiento corre en paralelo a todo esto: consume las horas y los ciclos que salen del campo y entrega disponibilidad de drones a la programación.

**Decisiones**
- Tres niveles, de arriba abajo:
  - **Flujo de valor:** 6 etapas vistas por el cliente.
  - **Proceso E2E:** los 10 pasos, encadenados con disparo. Cada paso realiza su etapa de valor.
  - **Actores:** 9 actores asignados a los pasos que ejecutan.
- El mantenimiento no se puso como un paso más de la cadena, sino como un proceso aparte dentro de la agrupación «Alcance de la aplicación SGMF». Ahí está la respuesta a dónde se ubica la aplicación.
- Se conecta con relaciones de **flujo**:
  - «Cerrar jornada» le pasa horas y ciclos.
  - El mantenimiento le pasa la disponibilidad a «Programar servicio».
- Lo disparan dos eventos: «Falla reportada en campo» (correctivo) y «Tarea preventiva próxima a vencer» (preventivo). Termina con «Dron liberado a servicio».
- La capacidad de mantenimiento sirve a las etapas de programar y ejecutar, lo que une V3 con V2.

---

## V4 — Descomposición de servicios (ArchiMate de negocio)

**Objetivo:** descomponer el proceso en capas de servicio, decidir qué se construye y qué no, y definir los contratos de los servicios más importantes.

**Análisis**
- Se usó la jerarquía de servicios vista en clase, con siete capas: proceso E2E, servicios de plataforma, servicios de dominio, servicios básicos, anticorrupción, datos maestros e infraestructura.
- El experto dejó claro qué no espera del sistema: telemetría en tiempo real, mantenimiento predictivo con IA, planeación de vuelos y facturación.
- Para la capa anticorrupción, la entrevista identificó con quién se intercambia información y en qué dirección:
  - sistemas (DJI, XAG, Siigo, la hoja de programación);
  - áreas internas (talento humano, agronomía, finanzas);
  - proveedores (distribuidores, gestor de residuos);
  - entidades sin API (Aerocivil, ICA, aseguradora, clientes);
  - dispositivos (drones y baterías inteligentes, a través de las plataformas de los fabricantes).

**Decisiones**
- **V4a Siete capas:** 3 servicios de plataforma, 7 de dominio, 15 básicos, 10 de anticorrupción, 4 de datos maestros y 4 de infraestructura. Las capas inferiores sirven a las superiores. Los 6 servicios excluidos quedan en una agrupación gris.
- Cada servicio tiene tres propiedades, que forman la tabla de inclusión y exclusión:
  - **Alcance:** incluido o excluido.
  - **Justificación:** por qué se decidió así.
  - **Fase:** en qué orden se construye, según la prioridad que dio el experto.
- Los servicios anticorrupción indican además la contraparte, su tipo y la dirección del intercambio, que se ve dentro de la caja.
- La telemetría quedó excluida aunque el enunciado la sugería, porque el experto dijo que no la necesita. Se reemplazó por la importación de los registros de vuelo que exportan los fabricantes.
- **V4b Responsables:** completa los servicios con actores, roles, funciones y objetos de negocio. Se separó actor de rol porque un mismo técnico puede ser ejecutor en una tarea e inspector en otra, pero nunca las dos en la misma tarea crítica.
- **V4c Contratos:** se aplicó Contract First a los 10 servicios más importantes. Son los que responden si un dron puede volar, alimentan el cálculo de vencimientos, cierran las órdenes de trabajo y planean, más las tres integraciones principales (fabricantes, Siigo y Programación). Cada contrato define entrada, salida, errores, protocolo y requisito no funcional, en una línea por campo.

---

## V5 — Dominios (ArchiMate de aplicaciones)

**Objetivo:** dividir el problema en dominios y clasificarlos según su importancia para el negocio.

**Análisis**
- Los dominios se extrajeron agrupando las responsabilidades del proceso de mantenimiento que cambian juntas.
- El experto contó que un software de mantenimiento genérico fracasó en 2023. Eso ayudó a separar lo que es propio de AeroAgro de lo que cualquier sistema resuelve.

**Decisiones**
- 9 dominios, cada uno como agrupación con su componente de aplicación (candidato a contexto delimitado) y los objetos de negocio que posee:
  - **Núcleo:** Aeronavegabilidad y estado, Planeación del mantenimiento, Configuración de flota y vida de componentes. Son la pregunta central («¿este dron puede volar hoy?»), las reglas propias de vencimiento y la vida de cada pieza.
  - **Soporte:** Registro de uso, Órdenes de trabajo y Abastecimiento de repuestos. Son necesarios, pero no diferencian a la empresa.
  - **Genérico:** Personal habilitado, Indicadores y reportes, Identidad y notificaciones. Se resuelven con soluciones conocidas.
- Cada dominio tiene en su documentación el argumento de su clasificación. Una nota en la vista explica el criterio.
- Abajo está el ecosistema externo: DJI, XAG, Siigo, la hoja de programación, el Excel de talento humano y Google Workspace, con flujos hacia el contexto con el que se integran.
- Los contextos núcleo van en naranja y los sistemas externos en gris.

---

## V6 — Agregados, comandos y eventos (ArchiMate de aplicaciones)

**Objetivo:** mostrar cómo funciona por dentro cada dominio: qué datos protege, qué órdenes recibe, qué avisa y qué reglas no se pueden romper.

**Análisis**
- Las reglas de negocio de la entrevista se convirtieron en invariantes de los agregados. Por ejemplo:
  - la doble firma en tareas críticas;
  - el retiro de una batería a los 1.000 ciclos;
  - «un dron con tarea vencida no vuela»;
  - el diferimiento solo una vez y con límite.
- El experto insistió en que componentes y baterías tienen vida propia. Por eso Dron, Componente controlado y Batería son tres agregados distintos y no uno solo.

**Decisiones**
- Para poder exponerla, la vista se condensó en tres diagramas, uno por clasificación:
  - **V6.1 Dominios núcleo:** 9 agregados (estado de aeronavegabilidad, diferimiento, novedad, plan maestro, seguimiento de vencimientos, plan semanal, dron, componente y batería).
  - **V6.2 Dominios de soporte:** 5 agregados (lote de importación, registro de uso, orden de trabajo, reserva de repuestos y necesidad proyectada).
  - **V6.3 Dominios genéricos:** 3 agregados (habilitación, indicadores y libro, notificación).
- Elementos usados:
  - la **agrupación** marca el dominio y el límite del agregado;
  - el **objeto de datos** representa la raíz, las entidades y los objetos de valor, y el nombre indica cuál es cuál;
  - el **proceso de aplicación** representa los comandos;
  - el **evento de aplicación** representa los eventos, escritos en pasado;
  - la **restricción** representa las invariantes.
- Todos los agregados siguen la misma plantilla: comandos a la izquierda, raíz y partes al centro, eventos a la derecha e invariantes debajo.
- Solo se dejaron los comandos y eventos principales de cada agregado, para que la vista se pueda explicar en la sustentación.
- Los dominios se comunican por eventos, no se llaman entre sí. A la derecha de cada diagrama hay una columna con los eventos que llegan de otros dominios. Por ejemplo, «UsoRegistrado» acumula horas en el dron y en sus componentes, y «OTCerrada» libera el dron.
- Estas conexiones entre dominios son la base del mapa de contextos de V8.
