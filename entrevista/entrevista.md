# Entrevista al experto del negocio: Mantenimiento preventivo de drones de fumigación agrícola
[Clic acá para ir a la conversación 👇](https://claude.ai/share/37c5164b-e30a-4a69-a0ac-568ea3279903)

## REGLAS PARA EL MODELO DE IA

no se permite pedir a la IA en esta conversación que proponga el mapa de capacidades, los dominios, los agregados, el mapa de contextos ni las vistas ArchiMate. Esos productos son la evaluación del equipo, debe actuar como un cliente que conoce su negocio y sus procesos de manera completa para que nosotros como equipo de desarrollo diagnostiquemos todos los requerimientos. Ten en cuenta entonces que el ejercicio es para un curso de arquietctura de software universitario, no te vayas a un nivel sumamente crítico/empresa grande porque somos solamente un equipo de 2 personas, trata de que tenga una exigencia adecuada para poder aplicar conocimientos técnicos de manera posterior como SOLID, Patrones de diseño, Arquitectura empresarial, Diagramación en archimate, y Arquitecturas de Microservicios con cada microservicio modelado con arquitecturas DDD; vete entonces con los requermientos justos para un sistema informático competente con una escala de dificultad de 5-6.5

---

## CONTEXTO

Contexto en el cual la IA es un conocedor del negocio de manera profunda:

**Mantenimiento preventivo de drones de fumigación agrícola**

### Solicitud

«Somos una empresa que presta servicios de fumigación de cultivos con una flota de drones. Necesitamos un software que apoye nuestro proceso de mantenimiento preventivo para mantener la flota disponible, segura y dentro de la normatividad aeronáutica».

### Alcance

- Registro de horas de vuelo y ciclos de cada dron, a partir de las operaciones realizadas.
- Despiece de cada dron (subsistemas y componentes como motores, hélices, baterías, bombas y boquillas) con las condiciones de mantenimiento preventivo de cada pieza: por horas, ciclos, calendario o estado.
- Repuestos y consumibles requeridos para cada cambio.
- Plan de mantenimiento que programe las intervenciones según esas condiciones.
- Indicadores del proceso, por ejemplo disponibilidad de la flota, cumplimiento del plan, tiempo medio entre fallas y costo de mantenimiento por hora de vuelo.

### Interoperabilidades a explorar

Programación de servicios a clientes, inventario y compras de repuestos, telemetría de los drones, técnicos certificados y autoridad aeronáutica.

---

## CONVENCIONES PARA LAS PREGUNTAS

- **[A]** abierta
- **[P]** profundización
- **[V]** validación

---

## GUION DE ENTREVISTA

### 1. Contexto de la organización

- [A] ¿A qué se dedica la organización? Cuéntenos su historia, misión y visión.

> **Respuesta:** Buenas tardes. Yo soy Mauricio Gaviria, director técnico y de mantenimiento de **AeroAgro Drones S.A.S.** Llevo en la empresa desde que arrancó, así que conozco tanto la operación de campo como el taller.
>
> Somos una empresa colombiana que presta **servicios de aspersión agrícola con drones**: aplicamos fungicidas, insecticidas, herbicidas, fertilizantes foliares y bioinsumos sobre cultivos de nuestros clientes. No vendemos drones ni productos químicos; vendemos el servicio de aplicación por hectárea.
>
> La empresa nació en 2018 en Rionegro (Antioquia). La fundaron una ingeniera agrónoma que trabajaba con cultivadores de aguacate y flores, y un técnico aeronáutico que venía de la aviación agrícola tradicional (avionetas fumigadoras). Arrancamos con 2 drones. En 2021 entramos a Urabá a trabajar con fincas bananeras, porque allá el control de sigatoka negra exige aplicaciones muy frecuentes y los drones empezaron a reemplazar parte de las aplicaciones aéreas con avioneta en lotes pequeños o cerca de viviendas. En 2023 abrimos una base en El Espinal (Tolima) para arroz y algodón.
>
> **Misión:** proteger la productividad de los cultivos de nuestros clientes con aplicaciones precisas, seguras y trazables, reduciendo el desperdicio de producto y la exposición de las personas a los agroquímicos.
>
> **Visión:** para 2028 ser la empresa de aplicación con drones de referencia en Antioquia y el centro del país, con una flota de más de 40 equipos y operación certificada en calidad.

- [A] ¿Qué bien o servicio ofrece y a qué clientes o stakeholders?

> **Respuesta:** Nuestro servicio principal es la **aplicación aérea de agroinsumos con drones**, cobrada por hectárea aplicada. Alrededor de eso ofrecemos:
>
> - **Visita técnica y levantamiento del lote:** el agrónomo revisa el cultivo, los linderos, obstáculos (cables, árboles, viviendas, fuentes de agua) y define con el cliente la receta de aplicación.
> - **Aplicación programada o por contrato:** hay clientes que nos contratan aplicaciones sueltas y otros (sobre todo bananeras) que tienen un contrato anual con ciclos fijos cada 10 a 14 días.
> - **Reporte de aplicación:** al cliente le entregamos un reporte con mapa de la zona aplicada, hectáreas, producto, dosis, condiciones de viento y hora, que le sirve a él para sus certificaciones.
>
> **Clientes:** fincas bananeras de Urabá (el 50 % de nuestros ingresos), productores de aguacate Hass y flores en el Oriente antioqueño (20 %), y arroceros y algodoneros del Tolima (30 %). Son unos 60 clientes activos, de los cuales 12 tienen contrato anual.
>
> **Otros stakeholders:** la Aeronáutica Civil (Aerocivil), el ICA, las autoridades ambientales regionales, la aseguradora con la que tenemos la póliza de la flota, los distribuidores de los fabricantes de drones (DJI y XAG), los proveedores de repuestos y, claro, nuestros pilotos y técnicos.

- [P] ¿Por qué lo entregan de la forma en que lo hacen y qué los diferencia de otras empresas del sector?

> **Respuesta:** Lo entregamos con drones porque en muchos lotes la avioneta no es viable (lotes pequeños, laderas, cercanía a viviendas o a ríos) y la aplicación manual con bomba de espalda es lenta y expone mucho al trabajador. El dron aplica con menos agua por hectárea, con más precisión y sin poner a una persona dentro de la nube de producto.
>
> Lo que nos diferencia, y lo que nuestros clientes más valoran, es:
>
> 1. **Cumplimiento:** si nos comprometemos a aplicar el martes, aplicamos el martes. En banano un retraso de dos o tres días en el ciclo de sigatoka se traduce en pérdida de fruta. Para eso necesitamos la flota disponible, y ahí entra el mantenimiento.
> 2. **Trazabilidad:** entregamos reportes con evidencia de qué se aplicó, dónde y cuándo. Las bananeras exportadoras están certificadas en GlobalG.A.P. y Rainforest Alliance y nos exigen esa evidencia, incluida la constancia de que el equipo estaba calibrado.
> 3. **Seguridad:** no hemos tenido accidentes con daño a terceros. Tuvimos dos caídas de drones en 2025 sin heridos, pero las dos nos dejaron lecciones sobre mantenimiento (una fue por un motor con rodamiento desgastado y otra por una batería que ya debía estar retirada).
>
> Muchos competidores son operadores pequeños con 2 o 3 drones que hacen el mantenimiento "cuando el dron avisa". Nosotros queremos competir siendo más confiables.

- [P] ¿Cuál es su tamaño (empleados, número de drones, hectáreas atendidas, sedes)?

> **Respuesta:**
>
> | Concepto | Cifra actual |
> |---|---|
> | Empleados | 42 |
> | Pilotos de drones | 14 |
> | Técnicos de mantenimiento | 6 (más el jefe de mantenimiento, que soy yo) |
> | Coordinadores de base | 3 (uno por base) |
> | Agrónomos | 4 |
> | Auxiliares de campo (mezcla, logística) | 8 |
> | Almacén y compras | 2 (un almacenista y una auxiliar de compras) |
> | Administración, comercial, talento humano / SST, gerencia | 4 |
> | Drones de aspersión | 26 (16 DJI Agras T40, 6 DJI Agras T50, 4 XAG P100) |
> | Baterías inteligentes de vuelo | 112 |
> | Hectáreas aplicadas por mes | ~6.500 ha (contando aplicaciones repetidas sobre el mismo lote) |
> | Horas de vuelo por mes (flota) | ~400 h |
> | Ciclos (despegue–aterrizaje) por mes | ~2.600 |
> | Sedes | 1 sede administrativa + 3 bases operativas |
>
> Para que se hagan una idea: un dron típico vuela entre 12 y 20 horas al mes, pero en temporada alta de banano algunos llegan a 30 horas. Cada salida dura entre 8 y 12 minutos (lo que dura un tanque y una batería), por eso los ciclos crecen muy rápido comparados con las horas.

- [P] ¿Dónde operan geográficamente (sedes, zonas de operación, bases de drones)?

> **Respuesta:**
>
> - **Rionegro (Antioquia):** sede administrativa, taller principal y almacén central. Aquí se hacen los servicios mayores, las reparaciones de mayor complejidad y desde aquí se compran los repuestos. Base de 7 drones que atienden aguacate y flores del Oriente.
> - **Apartadó (Urabá):** base de 11 drones. Es la más exigente: humedad muy alta, salinidad, mucho fungicida en emulsión con aceite, y jornadas largas. Tiene un taller pequeño con 2 técnicos.
> - **El Espinal (Tolima):** base de 8 drones para arroz y algodón. Calor fuerte y mucho polvo. Taller pequeño con 2 técnicos.
>
> Los drones **no se quedan siempre en su base**: cuando hay picos, trasladamos drones entre bases (por ejemplo, 3 drones de Rionegro se van a Urabá por un mes). También enviamos drones a Rionegro cuando la base no puede hacer cierto mantenimiento. Así que la "ubicación actual" de cada dron cambia y eso hay que tenerlo en cuenta.
>
> Además, para 2027 tenemos planeada una cuarta base en el Meta (Villavicencio / Puerto López) para arroz.

- [A] ¿Qué los motiva a digitalizar este proceso? ¿Qué problema concreto quieren resolver?

> **Respuesta:** Hay cuatro dolores muy concretos:
>
> 1. **No sabemos con certeza cuándo le toca mantenimiento a cada pieza.** Llevamos las horas en una hoja de Excel por base que alimentan los pilotos a mano. Muchas veces se les olvida, la llenan días después o la llenan "aproximada". Las horas que dice el Excel casi nunca cuadran con las que muestra la plataforma del fabricante.
> 2. **Los componentes se mueven entre drones y perdemos su historia.** Si un motor sale del dron 07 y se instala en el dron 12, nadie actualiza nada, y ese motor queda con sus horas "perdidas". Con las baterías es peor: son 112 rotando entre drones y bases. Una de las caídas de 2025 fue justamente por una batería que tenía muchos más ciclos de los que creíamos.
> 3. **Nos varamos por repuestos.** Cuando el técnico abre el dron y se da cuenta de que necesita una bomba, no hay en la base; se pide a Rionegro y el dron se queda parado tres o cuatro días. Si supiéramos con anticipación qué mantenimientos vienen, podríamos tener los repuestos listos.
> 4. **No tenemos indicadores confiables.** La gerencia pregunta cuánto nos cuesta mantener un dron por hora de vuelo o qué tan disponible está la flota y yo tengo que pasar dos días armando un Excel, y aun así no confío en los números.
>
> En resumen: queremos **saber en todo momento el estado real de cada dron y de cada pieza importante, anticiparnos al mantenimiento y tener evidencia ordenada** para los clientes, la aseguradora y la Aerocivil.

- [P] ¿Qué tan receptiva es la organización a adoptar software en sus procesos? ¿Hubo experiencias previas, buenas o malas?

> **Respuesta:** En general somos receptivos; somos una empresa de tecnología agrícola, la gente joven maneja bien el celular y las apps de los drones. Pero hay matices:
>
> - **Buena experiencia:** cuando pasamos la contabilidad y facturación a Siigo Nube en 2022 funcionó muy bien, porque era sencillo y resolvía un problema claro.
> - **Mala experiencia:** en 2023 compramos una licencia de un software genérico de mantenimiento (un CMMS pensado para plantas industriales). Fracasó por tres razones: era complicadísimo de configurar para drones, no funcionaba sin internet y los técnicos tenían que llenar 15 campos para registrar un cambio de hélices. A los tres meses todo el mundo había vuelto al Excel.
>
> La lección que nos quedó: **si el sistema le exige al piloto o al técnico más trabajo del que hace hoy, no lo van a usar.** Tiene que ser rápido de llenar en campo y en el taller, y debe calcular solo lo que hoy calculamos a mano.

### 2. Proceso E2E de la organización

- [A] Describa el flujo completo desde que un cliente solicita el servicio hasta que se entrega y se cobra.

> **Respuesta:** El flujo, de punta a punta, es este:
>
> 1. **Solicitud:** el cliente llama o escribe por WhatsApp al área comercial (o al coordinador de base, si ya es cliente). Si es un cliente con contrato, las aplicaciones ya vienen pactadas por ciclos.
> 2. **Visita técnica y cotización:** para clientes nuevos o lotes nuevos, un agrónomo visita el predio, toma el polígono del lote, identifica obstáculos y define con el cliente producto, dosis y volumen de mezcla por hectárea. Comercial envía la cotización.
> 3. **Aceptación y receta:** el cliente acepta y el agrónomo emite la **orden de aplicación** con la receta (producto, dosis, volumen, restricciones como distancia a fuentes de agua).
> 4. **Programación:** el coordinador de base, junto con operaciones, asigna fecha, pilotos y **drones**. Hoy esto se hace en una hoja de Google Sheets compartida y en Google Calendar. Aquí es donde chocamos con mantenimiento, porque a veces se programa un dron que tenía mantenimiento pendiente.
> 5. **Alistamiento:** el día anterior se cargan los drones, las baterías (normalmente 3 o 4 por dron), cargadores, generador y el producto (que casi siempre lo pone el cliente).
> 6. **Ejecución en campo:** el piloto hace la **inspección prevuelo**, revisa clima (viento máximo, lluvia), carga la misión y vuela. Cada salida es un ciclo. Al final de la jornada se hace limpieza del sistema de aspersión.
> 7. **Cierre de jornada:** el piloto llena la bitácora de vuelo (Excel o formato en papel en algunas bases) con horas, ciclos, hectáreas y novedades. La plataforma del fabricante también guarda los registros de vuelo.
> 8. **Reporte al cliente:** el agrónomo arma el reporte de aplicación con el mapa y los datos y lo envía al cliente, que lo aprueba (a veces con observaciones).
> 9. **Facturación:** administración factura en Siigo Nube (factura electrónica) por hectáreas aplicadas y aprobadas.
> 10. **Cobro:** los clientes pagan a 30 o 60 días. Cartera hace seguimiento.
>
> **El mantenimiento corre en paralelo a todo esto:** consume las horas y ciclos que salen de la ejecución en campo (paso 6 y 7) y entrega disponibilidad de drones a la programación (paso 4).

- [P] ¿Qué áreas participan y cuál es su rol en cada etapa?

> **Respuesta:**
>
> | Área | Rol principal |
> |---|---|
> | **Comercial** | Atiende al cliente, cotiza, firma contratos. |
> | **Agronomía** | Visita técnica, receta de aplicación, calidad de la aplicación, reporte al cliente. Exige que los drones estén calibrados. |
> | **Operaciones** (coordinadores de base + pilotos + auxiliares) | Programa y ejecuta los servicios. Reporta horas, ciclos y fallas. |
> | **Mantenimiento** (jefe + técnicos) | Planea y ejecuta mantenimiento preventivo y correctivo, libera los drones para vuelo, lleva el historial técnico. |
> | **Almacén y compras** | Custodia repuestos y consumibles por base, hace traslados entre bases, cotiza y compra a proveedores. |
> | **Talento humano y SST** | Lleva las certificaciones de pilotos y técnicos y sus vencimientos, el sistema de seguridad y salud en el trabajo. |
> | **Administración y finanzas** | Facturación, cartera, costos, contabilidad. |
> | **Gerencia** | Decisiones de inversión (compra o baja de drones), indicadores, relación con aseguradora y autoridades. |

- [P] ¿Cómo se comunican entre sí (herramientas, reuniones, formatos, WhatsApp, correo)?

> **Respuesta:** Siendo honesto, **WhatsApp es el sistema nervioso de la empresa**. Tenemos un grupo por base, un grupo de mantenimiento y un grupo de coordinadores. Ahí se reportan fallas con fotos, se piden repuestos y se avisa qué dron no puede volar. El problema es que la información se pierde entre cientos de mensajes.
>
> Además usamos:
>
> - **Google Sheets:** programación de servicios, bitácora de vuelo por base, matriz de mantenimiento, inventario de baterías.
> - **Correo (Google Workspace):** para comunicación formal con clientes, proveedores, aseguradora y Aerocivil.
> - **Formatos en papel:** órdenes de trabajo de mantenimiento con firma del técnico, checklist de servicio y en algunas bases el prevuelo.
> - **Reunión semanal de operaciones** (lunes, virtual): coordinadores, mantenimiento y comercial revisan la semana. Ahí se negocia qué drones entran a taller.

- [P] ¿Cuáles son los procesos críticos de cada área? ¿Cuáles detendrían la operación si fallan?

> **Respuesta:**
>
> - **Operaciones:** la ejecución en campo y la programación. Si falla la programación, llegamos tarde al ciclo del cliente.
> - **Mantenimiento:** la **liberación de drones para vuelo** (decir "este dron puede volar") y la **gestión de baterías**. Si no tenemos drones liberados o baterías en buen estado, no hay operación. Es el proceso que más detiene la operación.
> - **Almacén y compras:** la disponibilidad de repuestos críticos (motores, hélices, bombas, baterías). Un dron sin repuesto es un dron parado.
> - **Talento humano:** la vigencia de certificaciones. Un piloto con certificado vencido no puede volar, y un técnico sin certificación vigente no debería firmar la liberación.
> - **Agronomía:** la receta y la calibración. Sin receta no se aplica.
> - **Finanzas:** facturación y cobro; no detiene la operación del día pero sí la caja.
>
> Un dron parado en temporada nos cuesta: un dron hace en promedio 30 a 40 hectáreas en un día de operación y cobramos en promedio $75.000 COP por hectárea, así que **cada día-dron perdido son entre 2 y 3 millones de pesos** en ingreso, más la penalidad si incumplimos el contrato.

- [P] ¿Dónde está hoy el proceso físico (papel, formatos, bitácoras) y dónde el digital?

> **Respuesta:**
>
> | Información | Dónde está hoy |
> |---|---|
> | Programación de servicios | Digital: Google Sheets + Calendar |
> | Bitácora de vuelo (horas, ciclos, piloto, dron) | Mixto: Excel en Rionegro y El Espinal; papel en Urabá que luego se transcribe |
> | Registros de vuelo del fabricante | Digital: plataformas de DJI y XAG en la nube |
> | Inspección prevuelo | Papel en todas las bases (formato FM-02) |
> | Matriz de mantenimiento (qué tarea, cada cuánto) | Digital: un Excel maestro que mantengo yo |
> | Órdenes de trabajo de mantenimiento | Papel (formato FM-03), firmadas; se escanean y se guardan en Drive |
> | Hoja de vida de cada dron | Mixto: carpeta física por dron + carpeta en Drive |
> | Control de baterías (ciclos, estado) | Excel por base, muy desactualizado |
> | Inventario de repuestos | Siigo Nube (módulo de inventario, una bodega por base), aunque las bases a veces no registran las salidas |
> | Compras | Siigo Nube |
> | Certificaciones de personal | Excel de talento humano + carpetas físicas |
> | Reportes a Aerocivil y aseguradora | Correo con documentos adjuntos |

### 3. Actores y reglas de negocio

- [A] ¿Quiénes son los actores clave (pilotos, técnicos, jefe de flota, operaciones, compras, calidad, gerencia, clientes)?

> **Respuesta:** Los actores que tendrían relación con el sistema son:
>
> - **Piloto de drone:** vuela, hace la inspección prevuelo, reporta horas, ciclos y fallas.
> - **Coordinador de base:** responde por la operación de su base; asigna drones y pilotos a servicios.
> - **Técnico de mantenimiento:** ejecuta las tareas de mantenimiento y registra lo que hizo. Hay dos niveles: **técnico** y **técnico inspector** (este último puede hacer la verificación independiente de tareas críticas).
> - **Jefe de mantenimiento** (mi rol): define el plan, aprueba excepciones, libera o restringe drones, decide bajas de componentes.
> - **Almacenista / auxiliar de compras:** despacha repuestos, traslada entre bases, compra.
> - **Agrónomo:** usa la información de calibración de boquillas y bombas.
> - **Talento humano / SST:** mantiene las certificaciones del personal.
> - **Gerente general:** consulta indicadores, aprueba la baja de un dron completo y presupuestos.
> - **Externos:** clientes (piden constancias), aseguradora, Aerocivil, distribuidor del fabricante.

- [P] Para cada actor: ¿qué decide, qué ejecuta y qué información necesita?

> **Respuesta:**
>
> | Actor | Decide | Ejecuta | Información que necesita |
> |---|---|---|---|
> | **Piloto** | Si vuela o no según el prevuelo y el clima (puede negarse a volar un dron que considere inseguro). | Prevuelo, vuelos, reporte de novedades, limpieza diaria del sistema de aspersión. | Si el dron está liberado, si tiene restricciones, qué baterías puede usar, alertas de mantenimiento próximo. |
> | **Coordinador de base** | Qué dron va a qué servicio. | Programación diaria, traslado de drones. | Disponibilidad de cada dron por día, mantenimientos programados, drones con restricción. |
> | **Técnico** | Si un componente está bien o hay que cambiarlo (dentro de los criterios del manual). | Tareas de mantenimiento, cambios de componentes, calibraciones. | Órdenes de trabajo asignadas, checklist de cada tarea, repuestos reservados, historial del dron y del componente. |
> | **Técnico inspector** | Si una tarea crítica quedó bien hecha. | Verificación independiente y firma. | La tarea ejecutada y su evidencia. |
> | **Jefe de mantenimiento** | Plan de mantenimiento, intervalos, diferimientos, liberación a servicio, baja de componentes. | Planeación semanal, aprobaciones, análisis de fallas. | Estado de toda la flota, vencimientos, backlog, indicadores, repuestos disponibles. |
> | **Almacenista / compras** | Cuándo comprar y a quién; traslados entre bases. | Despacho, reserva, traslado y compra de repuestos. | Necesidades futuras de repuestos según el plan, consumos reales. |
> | **Agrónomo** | Si un dron sirve para una aplicación de precisión. | Revisión de la calibración. | Fecha y resultado de la última calibración de cada dron. |
> | **Talento humano** | Si una persona está habilitada. | Registro y renovación de certificaciones. | Vencimientos próximos. |
> | **Gerente** | Inversión, bajas de drones, presupuesto de mantenimiento. | Revisión mensual. | Indicadores consolidados por base, modelo y periodo. |

- [A] ¿Qué reglas de negocio gobiernan la operación y el mantenimiento? Por ejemplo, horas de vuelo, ciclos de batería, condiciones climáticas o aprobaciones.

> **Respuesta:** Estas son las reglas más importantes. Las agrupo para que sea más fácil:
>
> **A. Conteo de uso**
>
> 1. Una **hora de vuelo** se cuenta desde que despega hasta que aterriza (tiempo en el aire, no tiempo con el motor encendido en tierra).
> 2. Un **ciclo de dron** es un despegue y un aterrizaje. Cada salida de aspersión es un ciclo.
> 3. Un **ciclo de batería** es una descarga en vuelo y su recarga. El ciclo lo cuenta la propia batería y se ve en la app del fabricante.
> 4. Las horas y ciclos se acumulan al **dron** y también a **cada componente controlado que estaba instalado en ese momento** (motores, bombas, hélices, controlador de vuelo, etc.). Si el componente se pasa a otro dron, se lleva su acumulado.
> 5. Las baterías **no pertenecen a un dron**: pertenecen a la base y rotan. Su uso se cuenta por la batería misma.
>
> **B. Condiciones de mantenimiento preventivo**
>
> 6. Cada tarea preventiva puede tener una o varias condiciones: **por horas, por ciclos, por calendario o por estado (condición)**. Cuando tiene varias, **aplica la que ocurra primero**. Por ejemplo: "calibrar boquillas cada 50 horas o cada 15 días, lo que ocurra primero".
> 7. Cuando se ejecuta la tarea, su contador se reinicia desde ese momento.
> 8. Cuando se **reemplaza un componente**, las tareas de ese componente se reinician con el componente nuevo (o con el acumulado del componente usado que se instaló).
> 9. Las tareas tienen una **ventana de tolerancia**: se pueden hacer antes sin problema; a partir del 90 % del intervalo se considera "próxima a vencer" y se debe programar.
> 10. Algunas tareas son **por estado**: se hacen solo si una inspección o una medición lo indica. Por ejemplo, si en la inspección de hélices se encuentra una fisura, se cambia el juego; si la salud de una batería baja de cierto umbral, se retira.
>
> **C. Aeronavegabilidad y liberación**
>
> 11. **Un dron con alguna tarea preventiva vencida no puede volar**, salvo que exista un diferimiento aprobado (ver sección 4).
> 12. **Un dron con una falla reportada no resuelta queda en tierra** hasta que un técnico la evalúe.
> 13. Después de cualquier mantenimiento, el dron debe ser **liberado a servicio** por un técnico con certificación vigente para ese modelo.
> 14. Las tareas marcadas como **críticas** (motores, hélices, controladores electrónicos de velocidad, controlador de vuelo, baterías) requieren **doble firma**: el técnico que ejecuta y un técnico inspector distinto que verifica.
> 15. Después de una caída o un aterrizaje brusco, el dron entra a **inspección completa** sin importar cómo se vea.
>
> **D. Baterías**
>
> 16. Política interna: una batería se **retira de vuelo** al llegar a **1.000 ciclos** o cuando su salud reportada baja del **80 %**, lo que ocurra primero.
> 17. Cada 100 ciclos se le hace inspección (hinchazón, conectores, desbalance de celdas).
> 18. Si una batería pasa más de **30 días sin usarse**, debe hacérsele un ciclo de mantenimiento de carga antes de volver a volar.
> 19. Una batería con golpe, hinchazón o recalentamiento queda en **cuarentena** y no vuelve a vuelo sin evaluación.
>
> **E. Operación**
>
> 20. No se vuela con viento sostenido mayor a 20 km/h ni con lluvia. (Esta regla es de operaciones, no de mantenimiento, pero la menciono porque afecta las horas reales.)
> 21. Antes de cada jornada el piloto hace la inspección prevuelo; si algún punto falla, el dron no vuela y se reporta la novedad.
> 22. La **calibración de boquillas y caudal** debe estar vigente para aplicar; si está vencida, el agrónomo no autoriza la aplicación aunque el dron esté mecánicamente bien.
>
> **F. Personal**
>
> 23. Solo un **piloto con certificación vigente** puede volar, y solo puede volar modelos para los que esté habilitado.
> 24. Solo un **técnico certificado para el modelo** puede ejecutar y firmar mantenimientos de ese modelo.

- [P] ¿Cuáles de esas reglas son físicas (papel, firmas) y cuáles ya son digitales?

> **Respuesta:** Casi todo es físico o "de cabeza":
>
> - **Digitales a medias:** los intervalos de mantenimiento están en mi Excel maestro, pero el cálculo de "cuánto falta" lo hacemos a ojo comparando con la bitácora. Los ciclos de batería están en la app del fabricante, pero nadie los consolida.
> - **Físicas:** las firmas de órdenes de trabajo, la doble firma de tareas críticas, el prevuelo, la liberación a servicio, la cuarentena de baterías (literalmente las ponemos en un estante con cinta roja).
> - **De cabeza / costumbre:** el seguimiento de componentes que se mueven entre drones, el bloqueo de un dron con mantenimiento vencido (depende de que el coordinador se acuerde de preguntarme), y la validación de certificaciones (nadie revisa antes de asignar).
>
> Lo que esperamos es que el sistema **aplique automáticamente** las reglas de cálculo y bloqueo, y que las firmas pasen a ser **firmas digitales sencillas** (usuario autenticado + confirmación), con registro de quién firmó y cuándo.

- [V] ¿Hay reglas no escritas que se aplican por costumbre?

> **Respuesta:** Sí, varias, y sería bueno que algunas quedaran formalizadas:
>
> 1. **Las hélices se cambian por juego del mismo eje**, aunque solo una esté dañada, para no desbalancear.
> 2. **En Urabá cambiamos filtros y revisamos bombas más seguido** que en las otras bases, porque el fungicida con aceite agrícola tapa más. En la práctica aplicamos los intervalos al 80 % allá. Nos gustaría que el intervalo de ciertas tareas se pudiera **ajustar por base**.
> 3. **No se mezclan en una misma jornada baterías con diferencias grandes de ciclos** en un mismo dron (por ejemplo, una de 100 ciclos con una de 900), porque se descargan distinto y el piloto pierde referencia.
> 4. **El técnico que hizo el trabajo no puede ser quien lo inspecciona.** Esto sí está escrito para tareas críticas, pero en la práctica, cuando hay un solo técnico en la base, se termina firmando por teléfono con el inspector de otra base mirando fotos. Queremos que esto quede registrado como **inspección remota con evidencia fotográfica**, que es lo que realmente pasa.
> 5. **Un dron recién salido de servicio mayor hace un vuelo de prueba** sin carga antes de volver a aplicación.
> 6. Antes de un traslado largo a otra base, se le hace una inspección rápida al dron para no llevar un problema.

### 4. Excepciones y gestión de problemas

- [A] ¿Qué pasa cuando algo sale mal en un área (falla en campo, repuesto no disponible, dron fuera de servicio)?

> **Respuesta:**
>
> **Falla en campo:** el piloto aterriza el dron (si puede), lo deja en tierra y manda por WhatsApp una foto y una descripción al grupo de mantenimiento. El coordinador de base intenta reemplazarlo con otro dron de la base para no perder la jornada. El técnico de la base evalúa en el sitio o cuando el dron vuelve al taller y decide si es una reparación rápida o si entra a taller. Lo que queremos: que el piloto registre la **novedad** desde el celular aunque no tenga señal, con categoría de falla, foto y el dron queda automáticamente **en tierra**.
>
> **Repuesto no disponible:** el técnico avisa al almacén, el almacén revisa si hay en otra base y lo traslada (1 a 2 días por transportadora) o lo compra (de 3 a 15 días según el repuesto; los de DJI suelen tener stock en el distribuidor en Bogotá, los de XAG a veces tardan semanas). Si es urgente, el jefe de mantenimiento puede **autorizar canibalización**: sacar el componente de un dron que ya está parado por otra razón e instalarlo en el que se necesita. Esto debe quedar registrado como movimiento del componente.
>
> **Dron fuera de servicio prolongado:** si un dron va a estar parado más de 7 días (por ejemplo, porque se envía al distribuidor por garantía), se marca como **fuera de servicio** y se informa a operaciones para que no lo cuenten en la programación. Hay que registrar la salida al taller externo y su regreso.

- [P] ¿Cómo identifican y resuelven los cuellos de botella? Dé un ejemplo reciente.

> **Respuesta:** Hoy los identificamos **cuando ya explotaron**, que es justamente el problema.
>
> **Ejemplo reciente (julio de 2026):** en Urabá coincidieron en la misma semana el servicio de 200 horas de 4 drones T40 que habían llegado juntos en 2025. Los cuatro necesitaban kit de rodamientos de motor y tubos de bomba. En la base había kits para uno solo. Resultado: 3 drones parados entre 4 y 6 días en plena temporada de sigatoka, y tuvimos que trasladar 2 drones desde Rionegro, con el costo del traslado y dejando a Rionegro corto.
>
> Si el sistema nos hubiera mostrado **con 3 o 4 semanas de anticipación** qué servicios venían, y qué repuestos requerían, hubiéramos escalonado los servicios (adelantando dos de ellos) y comprado los kits a tiempo. Eso es exactamente lo que esperamos: **proyección de mantenimientos futuros** basada en el ritmo de vuelo de cada dron y **proyección de repuestos** asociada.

- [P] ¿Qué pasa si se vence un mantenimiento preventivo y el dron debe operar? ¿Quién autoriza la excepción?

> **Respuesta:** Esto lo llamamos **diferimiento**. Las reglas son:
>
> 1. Solo lo puede autorizar el **jefe de mantenimiento**. En mi ausencia, el técnico inspector de mayor antigüedad que yo designe.
> 2. **No se pueden diferir tareas críticas** (motores, hélices, controladores de velocidad, controlador de vuelo, baterías que llegaron a su límite). Esas son absolutas.
> 3. Las tareas no críticas (por ejemplo, limpieza profunda de radar, revisión de tornillería del tren, calibración de RTK) se pueden diferir **una sola vez**, hasta un máximo del **10 % del intervalo** o **7 días calendario**, lo que ocurra primero.
> 4. El diferimiento debe tener **justificación escrita** y queda registrado con quién lo aprobó, cuándo y hasta qué límite.
> 5. El dron queda en estado **"disponible con restricción"** y el piloto debe verlo así en el prevuelo.
> 6. Si se alcanza el límite del diferimiento sin hacer la tarea, el dron queda en tierra automáticamente.
>
> Hoy esto se hace por WhatsApp con un "dale, vuela hasta el viernes", y no queda rastro. Eso, frente a una auditoría o a un siniestro con la aseguradora, es un riesgo enorme.

- [P] ¿Cómo manejan los mantenimientos correctivos que interrumpen el plan preventivo?

> **Respuesta:** Un correctivo siempre tiene prioridad sobre el preventivo, porque el dron ya está parado. Lo que hacemos (o queremos hacer bien) es:
>
> 1. **Aprovechar la parada:** si el dron entra por un correctivo y tiene preventivos que vencen en los próximos días o que están por encima del 80 % de su intervalo, el jefe de mantenimiento decide si se **adelantan** en la misma intervención. Así evitamos sacarlo dos veces.
> 2. **Si el correctivo reemplaza un componente**, las tareas preventivas de ese componente se reinician. Por ejemplo, si se cambió un motor por falla, la tarea de "cambio de rodamientos a 500 h" ya no aplica para el motor viejo y empieza a contar para el nuevo.
> 3. **Si el correctivo incluye trabajo equivalente a un preventivo** (por ejemplo, para reparar la bomba se cambió el tubo, que es justo la tarea preventiva de 150 h), se debe poder **dar por cumplida** esa tarea preventiva y reiniciar su contador.
> 4. **Reprogramación:** los preventivos que se desplazan por un correctivo de otro dron (porque el técnico estaba ocupado) se reprograman y el sistema debe recalcular el plan de la semana.
> 5. Todo correctivo debe registrar la **causa de la falla** con una categoría (motor, hélice, controlador de velocidad, bomba, boquilla, batería, GPS/RTK, radar, estructura, software/firmware, error de operación, causa externa). Sin eso no podemos calcular el tiempo medio entre fallas por tipo de componente.

- [V] ¿Estos son los escenarios de excepción más frecuentes o hay otros?

> **Respuesta:** Esos son los principales. Agregaría estos:
>
> - **Boletines o avisos del fabricante:** a veces DJI o XAG emiten un aviso (por ejemplo, "revisar el conector de tal lote de baterías" o "actualizar firmware antes de volar"). Eso genera una tarea **única y obligatoria** para los drones o componentes afectados (por modelo o por rango de números de serie), con una fecha límite.
> - **Componente en garantía:** si falla un componente dentro de la garantía, no se cambia con stock propio si se puede esperar; se gestiona con el distribuidor. Necesitamos saber qué componentes están en garantía y hasta cuándo.
> - **Batería sospechosa:** batería en cuarentena, ya mencionada.
> - **Dron que regresa de taller externo:** debe entrar con su informe y pasar por inspección de recibo antes de liberarse.
> - **Errores de registro:** un piloto registra horas al dron equivocado. Hoy se tacha en el papel. En el sistema no se debería borrar, sino hacer una **corrección con motivo** y que se recalculen los contadores.

### 5. Indicadores y desempeño

- [A] ¿Qué métricas usan para saber si el proceso funciona bien?

> **Respuesta:** Las que queremos usar (y que hoy calculamos mal o no calculamos) son:
>
> | Indicador | Cómo lo entendemos | Meta |
> |---|---|---|
> | **Disponibilidad de la flota** | Días-dron disponibles (incluye "disponible con restricción") / días-dron totales del periodo, excluyendo drones dados de baja. | ≥ 90 % |
> | **Cumplimiento del plan preventivo** | Tareas preventivas ejecutadas antes de vencer / tareas preventivas que vencían en el periodo. | ≥ 95 % |
> | **Tiempo medio entre fallas (MTBF)** | Horas de vuelo / número de fallas no planeadas, por modelo y por tipo de componente. | Seguimiento; queremos que suba. |
> | **Tiempo medio de reparación (MTTR)** | Promedio de horas desde que el dron queda en tierra por falla hasta que se libera. | ≤ 24 h para fallas menores |
> | **Costo de mantenimiento por hora de vuelo** | (Repuestos + consumibles + mano de obra + servicios externos) / horas de vuelo, por dron, modelo, base y mes. | ≤ $80.000 COP/h |
> | **Vuelos con mantenimiento vencido sin diferimiento** | Número de ciclos realizados por drones con tareas vencidas no diferidas. | 0 (cero absoluto) |
> | **Fallas en campo por cada 100 horas** | Novedades que interrumpieron una jornada / horas de vuelo × 100. | ≤ 1,5 |
> | **Backlog de mantenimiento** | Tareas pendientes vencidas o próximas a vencer. | Lo más bajo posible |

- [P] ¿Cómo se miden hoy (fuente, frecuencia, responsable)? Por ejemplo, disponibilidad de la flota, cumplimiento del plan preventivo, tiempo fuera de servicio, costo de mantenimiento o fallas por vuelo.

> **Respuesta:** Mal y tarde:
>
> - **Disponibilidad:** la estimo yo una vez al mes revisando los grupos de WhatsApp y la programación. Es aproximada.
> - **Cumplimiento del plan:** no se mide, porque no hay un plan formal; hay una matriz de intervalos.
> - **MTBF:** no se mide. Tenemos las fallas regadas en WhatsApp y en órdenes de trabajo en papel sin categoría.
> - **Costo por hora:** administración saca el total de compras de repuestos del mes en Siigo y lo divide por las horas de la bitácora. No separa por dron, no incluye mano de obra y mezcla compras con consumos (si compramos 20 hélices en un mes, ese mes "sale carísimo").
> - **Fallas por vuelo:** no se mide.
>
> Responsable: en teoría yo, con apoyo de administración para costos. Frecuencia: mensual para la reunión con gerencia.

- [P] ¿Cuáles son las metas actuales y cuáles son las más difíciles de cumplir?

> **Respuesta:** Las metas son las de la tabla anterior. Las más difíciles:
>
> 1. **Disponibilidad del 90 % en temporada alta** (octubre–diciembre y marzo–mayo en banano). Estimamos que hoy estamos alrededor del 82 % en esas temporadas.
> 2. **Cero vuelos con mantenimiento vencido.** Sabemos que ocurre, pero no podemos medir cuánto. Esa es la que más me preocupa por seguridad y por la aseguradora.
> 3. **Costo por hora de vuelo:** creemos que estamos entre $70.000 y $95.000 COP, pero sin datos confiables no sabemos dónde se nos va la plata. Sospechamos que las baterías y los motores de los T40 de Urabá son los más costosos.

- [V] ¿Qué indicador le gustaría poder ver y hoy no puede?

> **Respuesta:** Tres cosas concretas:
>
> 1. **Un tablero de estado de la flota en tiempo casi real:** cada dron con su estado (disponible, disponible con restricción, en mantenimiento, en tierra por falla, fuera de servicio, dado de baja), su base actual y su próximo mantenimiento con cuántas horas o días le faltan.
> 2. **Una proyección a 30 días:** qué mantenimientos vienen, en qué fechas aproximadas según el ritmo de vuelo de cada dron, y **qué repuestos van a hacer falta por base**. Esto para mí es el indicador más valioso.
> 3. **Vida útil real de los componentes:** cuántas horas duran realmente los motores, bombas y baterías antes de fallar o de retirarse, por modelo y por base. Eso nos permitiría ajustar los intervalos con datos y no solo con lo que dice el fabricante.

### 6. Normatividad y gobernanza

- [A] ¿Qué normatividad externa debe cumplir el proceso (aeronáutica civil, agrícola/sanitaria, ambiental, seguridad y salud, protección de datos)?

> **Respuesta:** Les doy el panorama como lo manejamos nosotros; los detalles legales los lleva nuestro asesor jurídico:
>
> - **Aeronáutica civil:** los drones están regulados por la **Aerocivil**, mediante el **RAC 100** (reglamento de sistemas de aeronaves no tripuladas). Para nosotros eso implica: los drones registrados ante la Aerocivil, pilotos con la formación y certificación exigida, un manual de operaciones, seguro de responsabilidad civil, reporte de incidentes y accidentes, y **mantener los equipos según las instrucciones del fabricante con registros que lo demuestren**.
> - **Agrícola / sanitaria:** el **ICA** regula la aplicación de plaguicidas; estamos registrados como empresa aplicadora, aplicamos solo productos con registro ICA y bajo receta de un agrónomo. Esto toca al mantenimiento por la **calibración de los equipos de aplicación**: una boquilla descalibrada significa una dosis incorrecta.
> - **Ambiental:** respetar distancias a fuentes de agua, viviendas y zonas protegidas; manejo de aguas de lavado y disposición de envases. Lo relevante para mantenimiento es el registro de las limpiezas del sistema de aspersión y la disposición de residuos (por ejemplo, filtros contaminados).
> - **Seguridad y salud en el trabajo:** el SG-SST (Decreto 1072 de 2015 y los estándares mínimos). En el taller manejamos baterías de litio de alta capacidad y residuos con agroquímicos; hay procedimientos de manejo seguro y disposición de baterías.
> - **Protección de datos:** Ley 1581 de 2012. Manejamos datos personales de pilotos y técnicos y datos de ubicación de las fincas de los clientes, que para ellos son confidenciales.

- [P] ¿Qué evidencias o registros deben conservar para auditorías o inspecciones?

> **Respuesta:** Por cada dron necesitamos poder mostrar su **"libro de mantenimiento"**:
>
> 1. **Hoja de vida del dron:** modelo, número de serie, registro ante Aerocivil, fecha de adquisición, estado, base.
> 2. **Historial de horas y ciclos**, con su origen (registro de vuelo del fabricante o reporte del piloto).
> 3. **Configuración instalada:** qué componentes controlados tiene montados hoy (con número de serie) y el historial de instalaciones y desmontajes.
> 4. **Todas las órdenes de trabajo** cerradas: qué se hizo, quién lo hizo, quién lo inspeccionó, fecha, horas del dron en ese momento, repuestos usados (con número de serie cuando aplica), hallazgos, fotos.
> 5. **Diferimientos** con su aprobación y justificación.
> 6. **Liberaciones a servicio** con firma.
> 7. **Fallas e incidentes** con su análisis.
> 8. **Calibraciones** del sistema de aspersión.
> 9. **Cumplimiento de avisos del fabricante.**
>
> Para cada **batería**, su historial de ciclos, inspecciones, cuarentenas y retiro.
>
> **Conservación:** nuestra política es guardar los registros **mientras el dron esté activo y al menos 5 años después de su baja**. Y algo importante: **los registros firmados no se pueden modificar ni borrar**; si hay un error se hace una corrección que deja rastro del original.
>
> Necesitamos poder **exportar ese libro en PDF** para enviarlo a la aseguradora, a la Aerocivil o a un cliente cuando lo pidan.

- [A] ¿Qué políticas, procedimientos o certificaciones internas aplican (calidad, seguridad, mantenimiento)?

> **Respuesta:**
>
> - **Manual de mantenimiento interno (MM-01):** basado en los manuales de DJI y XAG, con nuestras adaptaciones (como los intervalos de Urabá). Define las tareas, intervalos, cuáles son críticas, y el procedimiento de liberación.
> - **Procedimiento de gestión de baterías (PR-04):** almacenamiento, carga, cuarentena, retiro y disposición.
> - **Manual de operaciones:** el que exige la Aerocivil; incluye prevuelo y reporte de novedades.
> - **Formatos:** FM-01 bitácora de vuelo, FM-02 inspección prevuelo, FM-03 orden de trabajo, FM-05 checklist de servicio de 100 h, FM-06 registro de calibración.
> - **Certificaciones:** no estamos certificados aún, pero estamos preparando **ISO 9001 para 2027**, y el auditor de pre-evaluación nos dijo que el proceso de mantenimiento era nuestro punto más débil en trazabilidad. Nuestros clientes bananeros están certificados en GlobalG.A.P. y nos auditan como proveedores una vez al año.

- [P] ¿Qué gobernanza esperan para el proceso digitalizado (responsables, aprobaciones, trazabilidad)?

> **Respuesta:**
>
> 1. **Dueño del proceso:** el jefe de mantenimiento. Es quien aprueba cambios en el plan maestro de tareas e intervalos.
> 2. **Cambios a la configuración del plan** (crear una tarea, cambiar un intervalo, marcar una tarea como crítica) deben quedar registrados con quién, cuándo y por qué, y aplicar desde ese momento sin reescribir el pasado.
> 3. **Roles y permisos claros:** un piloto no puede cerrar una orden de trabajo; un técnico no puede aprobar un diferimiento; solo el jefe de mantenimiento da de baja un componente; solo gerencia da de baja un dron completo.
> 4. **Trazabilidad completa:** toda acción importante (registro de vuelo, cambio de componente, firma, diferimiento, corrección) debe quedar con usuario, fecha y hora, y base.
> 5. **Revisión mensual:** reunión con gerencia sobre indicadores.

- [V] ¿Hay inspecciones o auditorías periódicas? ¿Quién las realiza?

> **Respuesta:** Sí:
>
> - **Aerocivil:** puede hacer inspecciones a nuestra operación; no son con fecha fija. La última fue en 2025 y pidieron ver registros de mantenimiento de 5 drones escogidos al azar; nos tomó dos días reunirlos.
> - **ICA:** visitas de verificación como empresa aplicadora, más enfocadas en productos y calibración.
> - **Clientes (bananeras):** auditoría anual de proveedor por sus certificaciones.
> - **Aseguradora:** en la renovación anual de la póliza piden un resumen del estado de la flota, y en caso de siniestro piden el historial completo del dron.
> - **Interna:** yo hago una revisión trimestral de una muestra de órdenes de trabajo; desde 2027 se sumará la auditoría interna de ISO 9001.

### 7. Tecnología (TI y sistemas)

- [A] ¿Cuentan con un área de TI? ¿Es interna o tercerizada?

> **Respuesta:** No tenemos área de TI como tal. Tenemos:
>
> - Una **auxiliar administrativa** que administra las cuentas de Google Workspace, Siigo y los equipos.
> - Un **proveedor externo** que nos da soporte de redes y equipos por horas.
> - Los pilotos y técnicos manejan las apps de los fabricantes por su cuenta.
>
> Por eso necesitamos que el sistema sea **fácil de operar y mantener**, idealmente en la nube, sin servidores en nuestras instalaciones.

- [P] ¿Tienen un marco de gobernanza o gestión de TI (políticas de seguridad, gestión de cambios, estándares)?

> **Respuesta:** Formal, no. Tenemos unas reglas básicas: cada persona con su usuario, contraseñas de Google Workspace con doble factor obligatorio, copias de seguridad automáticas de Drive y una política de tratamiento de datos personales por la Ley 1581. No tenemos gestión de cambios formal.
>
> Lo que sí pedimos del sistema nuevo: **usuarios individuales con roles** (nada de usuarios compartidos por base), ojalá **inicio de sesión con nuestras cuentas de Google**, copias de seguridad, y que los datos de ubicación de los clientes estén protegidos.

- [A] ¿Qué sistemas de información usan hoy y a qué proceso apoya cada uno (ERP, inventarios, software del fabricante, hojas de cálculo)?

> **Respuesta:**
>
> | Sistema | Proceso que apoya |
> |---|---|
> | **Siigo Nube** | Contabilidad, facturación electrónica, compras, proveedores e inventario de repuestos por bodega (una bodega por base). |
> | **Plataforma de DJI Agras** (app en el control remoto + plataforma web) | Planeación de misiones y registros de vuelo de los T40 y T50: fecha, hora, duración, área, piloto, número de serie del dron. Las baterías DJI reportan su número de serie y ciclos en la app. |
> | **Plataforma de XAG** (app + nube) | Lo mismo para los 4 XAG P100. Formato distinto al de DJI. |
> | **Google Workspace** (Sheets, Drive, Calendar, Forms, Gmail) | Programación de servicios, bitácoras, matriz de mantenimiento, archivo de documentos escaneados. |
> | **WhatsApp** | Comunicación operativa, reporte de fallas. |
> | **Excel de talento humano** | Certificaciones del personal y vencimientos. |

- [P] ¿Dónde reside hoy la información del mantenimiento y quién la mantiene?

> **Respuesta:** Repartida:
>
> - **Matriz de tareas e intervalos:** mi Excel maestro, lo mantengo yo.
> - **Órdenes de trabajo:** papel en cada base; los coordinadores escanean y suben a Drive (cuando se acuerdan).
> - **Horas y ciclos:** bitácoras de los pilotos y plataformas de los fabricantes.
> - **Baterías:** un Excel por base que mantiene cada coordinador.
> - **Repuestos:** Siigo, que mantiene el almacenista; en las bases, las salidas las registra el técnico en un cuaderno y el almacenista las pasa a Siigo cada semana.
> - **Historial de fallas:** WhatsApp y la memoria de los técnicos.
>
> Queremos que la información de mantenimiento **quede en un solo lugar**, que sea el sistema nuevo, y que este se comunique con los otros sistemas donde haga falta.

- [P] ¿Qué conectividad tienen en campo y en las bases (internet, dispositivos, offline)?

> **Respuesta:** Este punto es muy importante:
>
> - **Rionegro:** fibra óptica estable.
> - **El Espinal:** 4G estable en la base y en buena parte de los lotes.
> - **Apartadó:** fibra en la base, pero se cae varias veces por semana, a veces por horas. **En las fincas casi no hay señal.**
> - **En campo en general:** hay que asumir que **no hay conexión** durante la jornada. Los pilotos sincronizan cuando vuelven a la base o cuando encuentran señal.
>
> **Dispositivos:** pilotos con celular Android de la empresa; técnicos con una tablet Android por base en el taller (resistente, con funda) y un computador de escritorio por base; jefe de mantenimiento, almacén y gerencia con portátil.
>
> Por eso necesitamos que **al menos el prevuelo, el reporte de novedades del piloto y el registro de tareas del técnico funcionen sin conexión** y se sincronicen cuando vuelva la señal. El resto (planeación, indicadores, aprobaciones) puede requerir conexión.

- [V] ¿Hay restricciones tecnológicas (nube, proveedores, presupuesto, seguridad)?

> **Respuesta:**
>
> - **Nube:** no tenemos preferencia de proveedor; nos parece bien la nube siempre que sea confiable y que los datos estén respaldados. Preferimos pago por uso a licencias costosas.
> - **Presupuesto de operación:** queremos que el costo mensual de infraestructura sea moderado (pensamos en algo del orden de lo que pagamos por Siigo y Google Workspace juntos).
> - **No queremos reemplazar Siigo:** la contabilidad, las compras y el inventario contable siguen allá.
> - **No queremos depender de un solo fabricante:** hoy tenemos DJI y XAG y mañana podríamos tener otra marca. El sistema no debe estar amarrado al formato de un fabricante.
> - **Seguridad:** acceso con usuario individual, datos de clientes protegidos, comunicación cifrada.
> - **Dispositivos:** debe funcionar en Android (celular y tablet) y en navegador web en computador.

### 8. El proceso en cuestión: mantenimiento preventivo de la flota

- [A] Describa paso a paso cómo se hace hoy el mantenimiento preventivo, desde la planeación hasta el cierre y registro.

> **Respuesta:** Hoy es así:
>
> 1. **Cada lunes** reviso las bitácoras de las tres bases (Excel y fotos del papel de Urabá) y las comparo con mi matriz de intervalos para ver qué drones están cerca de algún servicio.
> 2. En la **reunión de operaciones** negocio con los coordinadores qué días puede entrar cada dron a taller sin afectar la programación.
> 3. Le escribo al técnico de la base por WhatsApp qué le toca a cada dron. Le pido al almacenista que envíe lo que haga falta.
> 4. El técnico **imprime el formato de orden de trabajo** (FM-03) y el checklist del servicio (por ejemplo FM-05 de 100 h).
> 5. Ejecuta las tareas. Anota a mano los hallazgos, los repuestos usados y, a veces, toma fotos con su celular.
> 6. Si es tarea crítica, busca al inspector para la segunda firma (o le manda fotos).
> 7. **Libera el dron** firmando la orden y avisa por WhatsApp al coordinador.
> 8. El coordinador escanea la orden y la sube a Drive.
> 9. El técnico anota las salidas de repuestos en el cuaderno; el almacenista las pasa a Siigo.
> 10. Yo actualizo en mi matriz la fecha y las horas del último servicio (cuando me llega la información).
>
> Los problemas: el paso 1 depende de bitácoras incompletas, el paso 3 se pierde en WhatsApp, el paso 10 casi siempre se atrasa, y la información de componentes y baterías no la actualiza nadie.

- [P] ¿Cómo se define el plan (por horas de vuelo, ciclos, calendario, recomendaciones del fabricante)?

> **Respuesta:** Partimos de los **manuales de los fabricantes** y los ajustamos con nuestra experiencia. Para que tengan una referencia concreta, esta es una muestra simplificada de nuestra matriz para los T40 (los T50 y XAG son parecidos con algunas diferencias):
>
> | Componente / subsistema | Tarea | Condición | ¿Crítica? |
> |---|---|---|---|
> | Sistema de aspersión completo | Limpieza (tanque, bomba, filtros, boquillas) | Al final de cada jornada | No |
> | Filtros de tanque y de línea | Reemplazo | 30 h o 7 días | No |
> | Boquillas centrífugas | Calibración de caudal y tamaño de gota | 50 h o 15 días | No (pero obligatoria para aplicar) |
> | Discos atomizadores de boquilla | Reemplazo | 300 h o por desgaste | No |
> | Bomba | Reemplazo de tubo y sellos | 150 h | No |
> | Bomba | Reemplazo de la bomba | 600 h o por condición (caudal fuera de rango) | No |
> | Hélices | Inspección (fisuras, balance) | 50 h | Sí |
> | Hélices | Reemplazo del juego | 200 h o por daño | Sí |
> | Motores | Inspección (juego, ruido, temperatura) | 100 h | Sí |
> | Motores | Cambio de rodamientos | 500 h | Sí |
> | Motores | Reemplazo | 1.200 h o por condición | Sí |
> | Controladores de velocidad (ESC) | Inspección de conectores y temperatura | 100 h | Sí |
> | Estructura, brazos y tren | Inspección de fisuras y tornillería | 100 h o 3.000 ciclos | No |
> | Radar y sensores de obstáculos | Limpieza y prueba | 100 h | No |
> | GPS / RTK | Calibración y verificación | 3 meses | No |
> | Controlador de vuelo | Revisión de firmware y registro de errores | Mensual | Sí |
> | Control remoto | Inspección y batería | 6 meses | No |
> | Dron completo | **Servicio mayor** (incluye todas las de 100 h + desarme parcial) | 500 h o 12 meses | Sí |
> | Baterías | Inspección | 100 ciclos | Sí |
> | Baterías | Retiro | 1.000 ciclos o salud < 80 % | Sí |
> | Baterías | Ciclo de mantenimiento de carga | 30 días sin uso | No |
>
> Las tareas se agrupan en **paquetes** (servicio de 50 h, de 100 h, servicio mayor) para que el técnico no tenga que abrir el dron por cada tarea suelta; cuando se ejecuta un paquete se cumplen todas las tareas que lo componen. Y, como les dije, algunas tareas tienen el intervalo **ajustado por base** (Urabá al 80 % en filtros, bombas y boquillas).
>
> Los **componentes controlados individualmente** (con número de serie) son: motores, controladores de velocidad, bomba, controlador de vuelo, módulo RTK, radar y baterías. Las hélices se controlan **por juego y por posición** (no tienen número de serie, pero las marcamos). Filtros, tornillería, sellos y discos son **consumibles**: no se les sigue la vida individual, solo se registra que se cambiaron y cuántos se usaron.

- [P] ¿Qué se registra en cada intervención (checklists, repuestos, firmas, fotos, hallazgos)?

> **Respuesta:** En cada orden de trabajo debería quedar:
>
> 1. **Dron**, base, fecha de apertura y cierre, horas y ciclos del dron al momento de la intervención.
> 2. **Tipo:** preventiva (y qué paquete o tareas), correctiva (asociada a la falla reportada), aviso del fabricante, o inspección especial (post-caída, recibo de taller externo).
> 3. **Checklist** de cada tarea con resultado: conforme / no conforme / no aplica, y para algunas tareas un **valor medido** (por ejemplo, caudal de la boquilla en L/min, salud de la batería en %, temperatura del motor). Si un valor medido está fuera de rango, la tarea queda no conforme y debe generar una acción.
> 4. **Hallazgos** en texto libre y **fotos** (sobre todo de daños y de tareas críticas).
> 5. **Componentes desmontados e instalados**, con número de serie y motivo (vencimiento, falla, canibalización).
> 6. **Repuestos y consumibles** usados con cantidades.
> 7. **Horas-hombre** por técnico.
> 8. **Firma del técnico** que ejecuta y, en tareas críticas, **firma del inspector**.
> 9. **Liberación a servicio**: dron disponible, disponible con restricción, o continúa en tierra (por ejemplo, si falta un repuesto).
>
> Las órdenes pasan por estos momentos: **programada → en ejecución → pendiente de inspección (si tiene críticas) → cerrada**. También puede quedar **suspendida por falta de repuesto**. Una vez cerrada no se modifica.

- [P] ¿En qué punto específico entraría la digitalización y qué esperan lograr con ella?

> **Respuesta:** Esperamos que el sistema cubra estos puntos, en este orden de importancia:
>
> 1. **Captura automática o casi automática del uso:** que las horas y ciclos lleguen de los registros de vuelo de los fabricantes y que el piloto solo **confirme o complete** (por ejemplo, qué baterías usó si la plataforma no lo trae). Que se acumulen al dron y a sus componentes instalados.
> 2. **Configuración de cada dron:** saber qué componentes tiene instalados y mover componentes entre drones o al almacén sin perder su historia.
> 3. **Cálculo continuo de vencimientos** con las reglas de "lo que ocurra primero", tolerancias, ajustes por base y diferimientos.
> 4. **Bloqueo automático** de drones con tareas vencidas o fallas abiertas, y que esa disponibilidad la vea operaciones.
> 5. **Plan y proyección:** generar la propuesta de plan semanal y la proyección a 30 días con repuestos requeridos. Yo ajusto y apruebo el plan.
> 6. **Órdenes de trabajo digitales** en la tablet, con checklist, fotos, firmas y funcionamiento sin conexión.
> 7. **Integración con inventario y compras** para reservar repuestos y avisar faltantes.
> 8. **Indicadores y libro de mantenimiento exportable.**
>
> **Lo que no esperamos:** no necesitamos telemetría en tiempo real del dron en vuelo, ni mantenimiento predictivo con inteligencia artificial, ni que el sistema planee los vuelos o haga la facturación. Queremos lo básico muy bien hecho.

- [A] ¿Quiénes usarán el sistema? Describa su perfil, sus dispositivos y las condiciones físicas en que trabajan (campo, taller, sin conexión).

> **Respuesta:**
>
> | Usuario | Cantidad | Perfil | Dispositivo | Condiciones |
> |---|---|---|---|---|
> | Pilotos | 14 | Jóvenes (22–35 años), técnicos o tecnólogos, muy hábiles con el celular. Poca paciencia para formularios. | Celular Android | A pleno sol, con guantes y protección por el químico, sin señal, entre salida y salida tienen 2–3 minutos. **Necesitan pantallas grandes, pocos toques y modo sin conexión.** |
> | Técnicos | 6 | Técnicos electrónicos o aeronáuticos, 25–45 años, conocen bien los equipos. | Tablet Android en taller; a veces el celular. | Taller con manos sucias de grasa o producto, ruido; en Urabá con conexión intermitente. **Checklists rápidos, fotos fáciles, sin conexión.** |
> | Coordinadores de base | 3 | Administran la base, manejan bien Excel. | Computador y celular. | Oficina de la base. |
> | Jefe de mantenimiento | 1 | Yo: ingeniero, uso intensivo, quiero tableros y filtros. | Portátil y celular. | Rionegro y viajes a las bases. |
> | Almacenista y compras | 2 | Manejan Siigo. | Computador. | Oficina en Rionegro. |
> | Agrónomos | 4 | Solo consultan calibraciones. | Celular y computador. | Campo y oficina. |
> | Talento humano | 1 | Consulta y registra certificaciones (o las sincroniza). | Computador. | Oficina. |
> | Gerencia | 1–2 | Solo indicadores. | Computador y celular. | Oficina. |
>
> En total unos **30 usuarios**, que podrían llegar a 45 con la base del Meta.

### 9. Interoperabilidad (bloque específico)

#### Procesos y áreas internas

46. [A] ¿Con qué procesos de negocio se relaciona el mantenimiento preventivo? Por ejemplo, planeación de vuelos, programación de operaciones, compras e inventario de repuestos, gestión de pilotos, calidad, costos o facturación.

> **Respuesta:** Se relaciona con:
>
> 1. **Programación de servicios (operaciones):** el más importante.
> 2. **Ejecución de vuelos / registro de operaciones:** de ahí salen horas y ciclos.
> 3. **Inventario y compras de repuestos.**
> 4. **Gestión de personal certificado** (pilotos y técnicos).
> 5. **Calidad agronómica** (calibraciones).
> 6. **Costos** (administración y finanzas).
> 7. **Gestión con entidades externas:** Aerocivil, aseguradora, fabricantes.
>
> Con **facturación** la relación es indirecta: no necesitamos integrar nada.

47. [P] Para cada uno: ¿qué información recibe el mantenimiento y cuál entrega? ¿En qué momento y con qué frecuencia?

> **Respuesta:**
>
> | Proceso | Mantenimiento **recibe** | Mantenimiento **entrega** | Momento / frecuencia |
> |---|---|---|---|
> | **Programación de servicios** | Asignación planeada de drones a servicios por día (para no programar mantenimiento cuando el dron está comprometido y para proyectar las horas futuras). | Estado y disponibilidad de cada dron por día; ventanas de mantenimiento programadas; drones con restricción. | Recibe al programar o cambiar la programación (varias veces al día). Entrega cada vez que cambia el estado de un dron, y la vista de disponibilidad de los próximos 14 días se consulta a diario. |
> | **Ejecución de vuelos** | Registros de vuelo: dron, fecha, hora de despegue y aterrizaje, duración, piloto, baterías usadas, área aplicada. Novedades y prevuelos de los pilotos. | Alertas al piloto (tarea próxima a vencer, restricciones, batería que no debe usar). | Al final de cada jornada (o cuando haya conexión); las novedades en el momento en que ocurren. |
> | **Inventario y compras** | Existencias por bodega, confirmación de reservas, llegada de compras. | Necesidades proyectadas por base, reservas para órdenes de trabajo, consumos reales, solicitudes de compra o de traslado, devoluciones de componentes reparables. | Reservas al programar una orden; consumos al cerrarla; proyección semanal. |
> | **Personal certificado** | Lista de técnicos y pilotos con sus certificaciones, modelos habilitados y fecha de vencimiento. | Nada formal; a lo sumo alertas de que un técnico con certificado por vencer tiene órdenes asignadas. | Cuando hay cambios (pocas veces al mes); el sistema debe validar al asignar o firmar. |
> | **Calidad agronómica** | — | Estado y resultado de la calibración de cada dron. | Cada vez que se calibra; el agrónomo consulta antes de autorizar una aplicación. |
> | **Costos / finanzas** | Costo unitario de repuestos (desde Siigo); tarifa estándar de hora-hombre de técnico (la define finanzas cada año). | Costo de mantenimiento por dron, base y mes, y horas de vuelo para el cálculo por hora. | Mensual, al cierre contable. |
> | **Entidades externas** | Avisos del fabricante, informes de taller externo, requerimientos de la aseguradora o Aerocivil. | Libro de mantenimiento, reportes de incidentes, resumen de estado de la flota. | Por demanda; renovación de póliza anual. |

48. [P] ¿Cómo se intercambia esa información hoy (correo, formatos, llamada, sistema)?

> **Respuesta:**
>
> - Programación ↔ mantenimiento: **WhatsApp y la reunión de los lunes**; la hoja de programación no muestra nada de mantenimiento.
> - Vuelos → mantenimiento: **bitácora en Excel o papel**; las plataformas de los fabricantes nadie las consulta para mantenimiento.
> - Mantenimiento ↔ inventario: **WhatsApp y cuaderno** en las bases; el almacenista digita en Siigo.
> - Talento humano → mantenimiento: **nada**; preguntamos cuando hay duda.
> - Mantenimiento → agronomía: **llamada o WhatsApp** ("¿el 14 está calibrado?").
> - Mantenimiento → finanzas: **Excel** mensual armado a mano.
> - Externos: **correo con PDF** escaneados.

#### Sistemas

- [A] ¿Qué sistemas existentes deberían enviar datos al sistema a construir o recibir datos de él (ERP, inventario, software de gestión de vuelo, telemetría del dron, contabilidad)?

> **Respuesta:**
>
> 1. **Plataformas de los fabricantes (DJI y XAG)** → envían registros de vuelo al sistema nuevo.
> 2. **Siigo Nube** (inventario y compras) ↔ intercambio en ambos sentidos.
> 3. **Programación de servicios** ↔ intercambio en ambos sentidos. Ojo aquí: hoy es una hoja de Google Sheets, pero **el próximo año queremos reemplazarla por una herramienta propia**. Por eso pedimos que el sistema de mantenimiento **ofrezca la disponibilidad de la flota de una forma estándar** que cualquier herramienta de programación pueda consultar, y que pueda recibir las asignaciones de drones. En el corto plazo nos sirve que lea la hoja de Google o que se carguen las asignaciones.
> 4. **Registro de personal (Excel de talento humano)** → envía certificaciones. A corto plazo podría ser una carga de archivo o una pantalla para que talento humano las registre directamente en el sistema nuevo; no queremos duplicar.
> 5. **Google Workspace** → inicio de sesión de los usuarios y, opcionalmente, almacenamiento de las fotos y PDF exportados.
>
> No necesitamos integración con contabilidad directamente; el costo de los repuestos lo tomamos de Siigo vía inventario.

- [P] ¿Qué datos específicos se intercambiarían, en qué formato y con qué periodicidad? ¿Esos sistemas tienen API, exportación o integración posible?

> **Respuesta:** Les cuento lo que sabemos; los detalles técnicos los tendrán que confirmar ustedes:
>
> **Plataformas de los fabricantes (registros de vuelo)**
>
> - Datos: número de serie del dron, fecha, hora de despegue y aterrizaje, duración, piloto (usuario de la app), área aplicada, volumen aplicado; en DJI, además, los números de serie de las baterías usadas y sus ciclos.
> - Formato: **ambas plataformas permiten exportar los registros a archivo (CSV o Excel) desde la web**, pero **cada una con columnas, nombres y formatos de fecha distintos**. XAG, por ejemplo, no trae la batería en la exportación que conocemos.
> - API: hasta donde sabemos, no tenemos acceso a una API abierta para nuestra cuenta; si existe, no la hemos explorado.
> - Periodicidad deseada: **diaria**. La propuesta realista es que el coordinador de cada base suba el archivo exportado del día (o de varios días) y el sistema lo procese, **sin duplicar registros que ya se cargaron** y señalando inconsistencias (dron que no existe, vuelo que se cruza en hora con otro del mismo dron, vuelo con duración absurda).
> - Muy importante: **que mañana se pueda agregar un tercer fabricante** sin rehacer el sistema.
> - Reconciliación: si el piloto reportó horas manualmente (porque la exportación no llegó) y luego llega la exportación, debe primar el dato del fabricante y quedar marcado el ajuste.
>
> **Siigo Nube (inventario y compras)**
>
> - Datos: catálogo de repuestos (código, nombre, unidad, costo promedio), existencias por bodega/base, documentos de salida de inventario, solicitudes u órdenes de compra.
> - Nuestro proveedor de Siigo nos dice que **tiene API REST** con la que se pueden consultar productos y existencias y crear documentos. No sabemos exactamente qué documentos de inventario se pueden crear por API; eso lo tienen que revisar.
> - Lo que queremos: consultar existencias al planear; registrar la salida de repuestos cuando se cierra una orden de trabajo (o al menos dejar lista la información para que el almacenista la confirme); y generar **solicitudes de compra o de traslado** cuando la proyección muestra faltantes.
> - **Siigo es el dueño de las existencias y del costo**; el sistema de mantenimiento es el dueño de qué repuesto requiere cada tarea y de qué se consumió en cada orden.
> - Una aclaración: Siigo no maneja números de serie de componentes. **El seguimiento por número de serie de motores, baterías, etc. es responsabilidad del sistema de mantenimiento.**
> - Periodicidad: consulta de existencias bajo demanda o cada pocas horas; salidas al cierre de cada orden.
> - Si Siigo no está disponible, el sistema de mantenimiento **no debe detenerse**: la orden se cierra y la salida se envía después.
>
> **Programación de servicios**
>
> - Recibe: por cada dron y día, su estado y disponibilidad; las ventanas de mantenimiento programadas.
> - Envía: por cada día, qué dron está asignado a qué servicio y base, y las horas estimadas de vuelo (para que la proyección de mantenimientos sea más precisa).
> - Formato: hoy, la hoja de Google; a futuro, la herramienta nueva. Les pedimos **una interfaz pensada para que otro sistema la consuma**.
> - Además, **cuando un dron pase a estar en tierra**, programación debería enterarse de inmediato (para buscar reemplazo).
>
> **Personal certificado**
>
> - Datos: persona, rol, tipo de certificación, modelos habilitados, fecha de expedición y vencimiento.
> - Formato: hoy Excel; un archivo o registro directo en el sistema. Frecuencia: bajo demanda.

- [P] ¿Hay datos que hoy se capturan dos veces en sistemas distintos?

> **Respuesta:** Sí, y es parte de lo que queremos eliminar:
>
> 1. **Horas y ciclos de vuelo:** quedan en la plataforma del fabricante y el piloto los vuelve a escribir en la bitácora.
> 2. **Repuestos usados:** el técnico los escribe en la orden de trabajo, luego en el cuaderno, y el almacenista los digita en Siigo. Tres veces.
> 3. **Estado de los drones:** lo sabe mantenimiento, pero el coordinador lo vuelve a anotar en la hoja de programación.
> 4. **Certificaciones:** las tiene talento humano y yo tengo mi propia lista de qué técnico está habilitado en qué modelo.
> 5. **Ciclos de baterías:** los muestra la app y los coordinadores los copian en el Excel de baterías.

#### Entidades externas

- [A] ¿Con qué entidades externas interactúa el proceso (autoridad aeronáutica, entidades agrícolas o ambientales, fabricantes, proveedores de repuestos, talleres, aseguradoras, clientes)?

> **Respuesta:**
>
> 1. **Aerocivil** (autoridad aeronáutica).
> 2. **ICA** (por la calibración de equipos de aplicación).
> 3. **Fabricantes y distribuidores autorizados** de DJI (distribuidor en Bogotá) y XAG (distribuidor en Bogotá con soporte desde China), que además funcionan como **taller externo** para garantías y reparaciones mayores.
> 4. **Proveedores de repuestos** (unos 5 habituales, incluyendo una importadora en Medellín).
> 5. **Aseguradora** de la flota (póliza todo riesgo y responsabilidad civil).
> 6. **Clientes**, sobre todo las bananeras certificadas.
> 7. **Gestor de residuos peligrosos**, que recoge baterías dadas de baja y filtros contaminados.

- [P] ¿Qué información se envía o recibe de cada una y en qué canal (portal, correo, físico)?

> **Respuesta:**
>
> | Entidad | Enviamos | Recibimos | Canal actual |
> |---|---|---|---|
> | Aerocivil | Registro de drones (altas y bajas), reportes de incidentes y accidentes, registros de mantenimiento cuando hay inspección. | Requerimientos, resultados de inspección. | Correo y trámites en línea de la entidad; documentos en PDF. |
> | ICA | Registros de calibración cuando hay visita. | Requerimientos. | Físico y correo. |
> | Fabricantes / distribuidores | Drones o componentes para garantía o reparación, con el reporte de la falla; solicitudes de garantía. | Avisos técnicos y actualizaciones de firmware, informes de reparación, componentes reparados o reemplazados. | Correo, WhatsApp, envío físico por transportadora. |
> | Proveedores de repuestos | Solicitudes de cotización y órdenes de compra (desde Siigo). | Cotizaciones, facturas, repuestos. | Correo. |
> | Aseguradora | Resumen anual del estado de la flota; en siniestro, el historial completo del dron. | Condiciones de la póliza, requerimientos. | Correo con PDF. |
> | Clientes | Constancia de mantenimiento y calibración vigente de los drones que les aplican. | Solicitudes de constancia en auditorías. | Correo. |
> | Gestor de residuos | Relación de baterías y residuos entregados. | Certificado de disposición. | Físico y correo. |

- [P] ¿Es necesario o deseable establecer comunicación digital directa con alguna? ¿Cuáles?

> **Respuesta:** Siendo realistas, **ninguna de estas entidades nos va a dar una API** para conectarnos. Lo que sí necesitamos es que el sistema **produzca los documentos de salida listos para enviar**:
>
> 1. **Libro de mantenimiento por dron** en PDF (para Aerocivil y aseguradora). **Necesario.**
> 2. **Constancia de mantenimiento y calibración vigente** por dron o por grupo de drones, para clientes. **Necesario.**
> 3. **Resumen del estado de la flota** para la renovación de la póliza. **Deseable.**
> 4. **Reporte de incidente** con los datos del dron, la falla y la intervención. **Deseable.**
> 5. **Seguimiento de envíos a taller externo:** registrar qué salió, cuándo, con qué reporte de falla y cuándo regresó, con el informe del taller adjunto. **Necesario** (no como integración, sino como registro).
> 6. **Registro de avisos del fabricante:** que yo pueda cargar el aviso y el sistema genere las tareas sobre los drones o componentes afectados. **Necesario.**
>
> Lo ideal sería que esos documentos se pudieran **enviar por correo desde el sistema** con un clic, pero no es indispensable.

- [V] ¿Falta algún proceso, área, sistema o entidad con la que se intercambie información, aunque sea de forma ocasional?

> **Respuesta:** Recordé dos cosas:
>
> - **Notificaciones a las personas:** hoy todo llega por WhatsApp. Nos gustaría que el sistema avise (por correo o notificación en el celular; WhatsApp sería un plus pero no indispensable) al técnico cuando se le asigna una orden, al jefe de mantenimiento cuando hay una falla o un diferimiento por aprobar, al coordinador cuando un dron queda en tierra, y al almacenista cuando hay faltantes proyectados.
> - **SST:** cuando se retira una batería por daño (hinchazón, golpe), SST necesita saberlo por el riesgo de incendio y para gestionar la disposición con el gestor de residuos. Es ocasional, pero importante.
>
> Y con **la futura base del Meta**: el sistema tiene que permitir crear una base nueva con sus bodegas, drones y personal sin desarrollo adicional.

### 10. Cierre

- [A] ¿Hay algo importante que no le hayamos preguntado?

> **Respuesta:** Algunas cosas que quiero dejar claras para que no se pierdan:
>
> 1. **El estado del dron es la pieza central.** Todo el mundo en la empresa pregunta lo mismo: "¿este dron puede volar hoy?". Si el sistema responde eso de forma confiable, con el motivo (por qué no puede, o con qué restricción), ya nos cambió la vida.
> 2. **Los componentes y las baterías tienen vida propia**, independiente del dron en el que estén. Si el sistema solo lleva horas por dron, no nos sirve.
> 3. **Nada se borra.** Las correcciones dejan rastro. Esto es por auditoría y por la aseguradora.
> 4. **Debe ser rápido para el piloto y el técnico.** Un piloto debería poder hacer el prevuelo en menos de un minuto y reportar una novedad en menos de dos. Si no, no lo van a usar, como pasó con el software de 2023.
> 5. **Que no dependa de un fabricante ni de Siigo para funcionar.** Si una integración falla, el mantenimiento debe seguir operando y ponerse al día después.
> 6. **Crecimiento:** en 2027 vamos a 35–40 drones y una cuarta base. No es una escala enorme, pero el sistema no debería "quedarse pequeño".
> 7. **Prioridad si hay que entregar por fases:** primero el registro de uso, la configuración de componentes, el cálculo de vencimientos y el estado del dron; después las órdenes de trabajo digitales; después la integración con inventario y la proyección; y por último los indicadores y documentos de salida.

- [A] ¿Quién más podría complementar esta información o tiene documentos (formatos, manuales, procedimientos) que podamos revisar?

> **Respuesta:**
>
> **Personas:**
>
> - **Yesid Palacios**, coordinador de la base de Apartadó: conoce muy bien la operación en condiciones difíciles y la realidad de la conectividad en Urabá.
> - **Laura Henao**, técnica inspectora en Rionegro: la que más sabe de baterías y de la doble firma.
> - **Diego Arango**, almacenista: les puede explicar cómo funciona el inventario en Siigo y qué limitaciones tiene.
> - **Andrea Correa**, auxiliar administrativa: maneja Siigo y Google Workspace; puede ayudarles con los accesos de prueba y con lo de la API de Siigo.
> - **Natalia Ospina**, una de las pilotos de El Espinal: la más crítica con los formularios; si el sistema le sirve a ella, le sirve a todos.
>
> **Documentos que les podemos compartir:**
>
> - Manual de mantenimiento interno **MM-01** y procedimiento de baterías **PR-04**.
> - Matriz maestra de tareas e intervalos (Excel), con los ajustes por base.
> - Formatos **FM-01** (bitácora), **FM-02** (prevuelo), **FM-03** (orden de trabajo), **FM-05** (checklist 100 h) y **FM-06** (calibración).
> - Ejemplos de exportaciones de registros de vuelo de **DJI** y de **XAG** (archivos reales de una semana, con los datos de clientes anonimizados).
> - El Excel de control de baterías de las tres bases.
> - Un par de órdenes de trabajo escaneadas, incluidas las de las dos caídas de 2025, para que vean el nivel de detalle que necesitamos.
> - Los manuales de mantenimiento de los fabricantes para T40, T50 y P100.
>
> Muchas gracias por el interés. Quedo atento a lo que necesiten.