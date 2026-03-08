# 📊 Playbook: Herramientas del Ecosistema Data

El sector de los datos incluye docenas de herramientas y evoluciona rápido. En lugar de conocerlas todas a medias, la clave del éxito profesional es saber **qué es**, **para qué sirve**, **sus ventajas/desventajas** y **cuándo utilizarlas según tu perfil** (Data Analyst, Scientist o Engineer).

> **Insight importante del mercado:**
> El stack más común hoy y el "must-have" para roles analíticos es:
> **SQL • Python • Pandas • Power BI / Tableau • Git • Cloud (BigQuery / AWS)**
> El resto configuran especializaciones.

---

## 1️⃣ Editores de Código e IDEs

| Herramienta | Tipo | Ventajas | Desventajas | Perfiles que más la usan |
| :--- | :--- | :--- | :--- | :--- |
| **Visual Studio Code** | Editor | Ligero, extensible, enorme ecosistema | Puede volverse pesado con muchas extensiones | Todos: Analysts, Scientists, Backend |
| **PyCharm** | IDE | Excelente para Python, debugging ultrapotente | Pesado, la versión Pro es de pago | Data Scientists, Backend Devs |
| **Jupyter Notebook** | Notebook | Perfecto para análisis rápido interactivo | Código muy difícil de versionar con Git | Data Analysts, Exploración |
| **JupyterLab** | Notebook IDE | Más orden y ventanas que Notebook clásico | Más recargado | Data Scientists |
| **Google Colab** | Cloud Nb | GPU gratis, facilidad mágica de compartir | Necesita obligatoria conexión a internet | ML Engineers, Estudiantes |
| **RStudio** | IDE | El referente absoluto mundial para R | Limita su uso si trabajas en Python | Data Analysts estadísticos |
| **Spyder** | IDE | Interfaz pensada al dedillo para ciencia, parecido a RStudio | Menos flexible | Científicos, Investigadores |
| **Vim** | Editor Terminal | Extremadamente rápido, ya en todas las terminales | Curva de aprendizaje extrema | Seniors, Data Engineers puros |
| **Emacs** | Editor Terminal | Hiper configurable y modificable | Muy complejo | Advanced Engineers |

---

## 2️⃣ Notebooks y Entornos de Análisis Colaborativos

| Herramienta | Tipo | Ventajas | Desventajas | Uso Típico |
| :--- | :--- | :--- | :--- | :--- |
| **Jupyter Notebook** | Local Notebook | Facilísima exploración rápida | Difícil para proyectos grandes y Git | Análisis exploratorio (EDA) |
| **Deepnote** | Cloud Collab | Colaboración "Google Docs", en tiempo real | Ecosistema menor | Equipos de Data |
| **Databricks** | Plataforma Total | Potencia absoluta escalable de procesado paralelo | Licencias corporativas costosas | Data Engineers, Big Data Analysts |
| **Kaggle Notebooks** | Cloud Notebook | Integración directa con las competiciones y datasets | Poco serio para producción empresarial | Estudiar, Portfolio, Concursos |

---

## 3️⃣ Librerías Core de Análisis de Datos

| Librería | Lenguaje | Ventajas | Desventajas | Perfil Que la Exprime |
| :--- | :--- | :--- | :--- | :--- |
| **Pandas** | Python | El estándar mundial para leer tablas y explorar | Lentísimo si sobrepasas los límites de memoria RAM (Big Data) | Data Analysts |
| **NumPy** | Python | Rapidez extrema en cálculo matricial, es el motor | No se usa casi a nivel negocio, es pura matemática | Data Scientists |
| **Polars** | Python/Rust | Velocidad abrumadora frente a Pandas, multi-núcleo | Aún es reciente, cuesta encontrar algunas respuestas | Data Engineers / Analysts con gran volumen |
| **Dask** | Python | Sintaxis similar a pandas, pero procesa repartido | Su configuración es compleja | Big Data |
| **PySpark** | Python/Scala | El rey del procesado industrial distribuido | Requiere saber levantar contenedores/clúster, curva alta | Data Engineers |

---

## 4️⃣ Librerías de Visualización (Python)

| Librería | Ventajas | Desventajas | Típico caso de uso |
| :--- | :--- | :--- | :--- |
| **Matplotlib** | Base del resto. Te deja dibujar literal cualquier cosa | La base teórica es tosca y es feo visualmente por defecto | Gráficos estáticos para papers |
| **Seaborn** | Capa sobre matplotlib que lo embellece brutalmente y tiene métodos estadísticos directos | Personalización a fondo pierde flexibilidad | Análisis exploratorio presentable |
| **Plotly** | Gráficos 100% interactivos (tooltips, zooms, clicks) | Carga pesada para navegadores móviles a veces | Creación de Dashboards o Apps (Streamlit) |
| **Bokeh** | Ideal para visualizaciones directas sobre navegadores web rápidos | Su comunidad es pequeña respecto a Plotly | Web-Apps Data |
| **Altair** | Basado en Vega-Lite, código muy elegante y conciso y resultados bonitos | Menos flexible para salirte del estándar | Exploración moderna |

---

## 5️⃣ Business Intelligence (Los Cuadros de Mando)

| Herramienta | Ventajas | Desventajas | Mercado Target |
| :--- | :--- | :--- | :--- |
| **Power BI** | Total integración con ecosistema Microsoft. Altísima demanda. DAX potente | Atado al entorno Windows/Azure. Poco flexible si lo extiendes | Empresas tradicionales, pymes, corporativo |
| **Tableau** | Las mejores y más precisas visualizaciones del sector. Creado de cero para eso | Licencias extremadamente costosas a gran escala | Consultoras, Bancos, Tech |
| **Looker (Google)** | Tienen su propio lenguaje analítico y modelado seguro (LookML) | Complejo de arrancar al principio | Big Tech, Scale-Ups que ya usan Google |
| **Metabase** | Conectas DB gratis, es instantáneo. Open source genial | Se queda algo corto en gráficas ultra avanzadas | Startups |
| **Superset** | Open-source muy muy potente respaldado por Airbnb | Difícil de configurar infraestructura en local | Ingeniería madura |

---

## 6️⃣ Bases de Datos (El hogar del Dato)

| Tecnologías | Tipo / Paradigma | Ventajas | Desventajas | Casos de Uso |
| :--- | :--- | :--- | :--- | :--- |
| **MySQL** | RDBMS (SQL) | Super popular, omnipresente, documentación infinita | Un paso por detrás a nivel funcionalidades analíticas | Tiendas Web, Foros |
| **PostgreSQL** | RDBMS (SQL) | Robusta, soporta objetos JSON espaciales, hiper madura, es el estándar dorado | Algo más dura de asimilar de inicio | Analítica robusta, SaaS, producto tech |
| **SQLite** | RDBMS (SQL) | El DB en un solo archivo, perfecto en local | No escala bien si varios usuarios editan a la vez | Tu portfolio de Data Analyst |
| **MongoDB** | NoSQL (Documentos) | Sin esquemas SQL rígidos, guardas dicts gigantes directo y escala | Mala para cruzar tablas entre sí (JOINS) | Redes sociales, apps en tiempo real |
| **Snowflake** | DW (Data Warehouse) Cloud | Lo hace todo solo y escala a velocidad de la luz, el estándar | El coste por cómputo puede dispararse a millones | Big Corporates |
| **Google BigQuery**| DW Serverless | Puedes procesar Terabytes en 3 segundos puros usando peticiones tipo API, integrado | Recluido en Google Cloud | Análisis de Big Data puro |

---

## 7️⃣ Herramientas de Data Engineering (Pipeline Builders)

| Herramienta | Tipo | Ventajas | Desventajas |
| :--- | :--- | :--- | :--- |
| **Apache Airflow** | Orquestación / Cronométro | Definición de DAGs super complejos por código Python (creado Airbnb) | Su infraestructura y despliegue cuesta |
| **AWS Glue** | ETL Cloud | Magia integrada con recursos de Amazon S3 sin servidores pesados | El Vendor lock-in total (no lo sacas de Amazon) |
| **dbt (data build tool)** | Tansformación SQL | Ha revolucionado la industria: tratas consultas SQL como código puro. Best practices, tests y Git a Queries | Tienes que dominar bases de SQL profundamente |

---

## 8️⃣ Control de Versiones 

| Herramienta | Ventajas | Desventajas |
| :--- | :--- | :--- |
| **Git** | Máquina del tiempo atómica, el estándar global. Sin él, no hay IT moderno. | La curva inicial en consola siempre es dura. |
| **GitHub** | Plataforma social de repositorios. Pull requests muy visuales. | Fomenta repositorios y exposición en exceso. |
| **GitLab** | Integra todo en uno potente para CI/CD corporativo y DevOps directo. | Más duro y feo visualmente para principiantes. |
| **Bitbucket** | Mágico si en la empresa usáis también Jira y Confluence para tickets (están en familia). | Comunidad open-source reducida. |

---

## 9️⃣ Gestión de Proyectos / Ticketing

| Herramienta | Ventajas | Desventajas | Perfil |
| :--- | :--- | :--- | :--- |
| **Trello** | Un Kanban muy visual. Arrastras columnas, pones listas y está listo. | Si escalas un equipo de 30 pidiendo tareas cruje por todos lados. | Startups, uso personal. |
| **Jira** | Puede controlar a 1.000 ingenieros en flujos super ágiles corporativos. | Su configuración requiere días, interfaz recargada. | Equipos de multinacionales. |
| **Notion** | El Word/Excel con esteroides súper maleable, bases de datos combinadas. | Al principio puede carecer de reglas firmes de equipo. | Freelancers, Data Analysts. |
| **Asana** | Asignación de plazos muy clara e interfaces agradables. | Requiere pagar en estadios medio altos. | Agencias y pymes. |

---

## 🔟 Despliegue de Apps y Nubes (Infra y Cloud)

| Tecnología | Categoría | Qué resuelve |
| :--- | :--- | :--- |
| **Amazon Web Services (AWS)** | Proveedor Cloud | Domina un % global absurdo, se valora infinito. Servicios como S3 y EC2 son míticos. |
| **Microsoft Azure** | Proveedor Cloud | Rey de la adopción corporativa (siempre meten Azure en un pack ofimático O365, gran cuota). |
| **Google Cloud (GCP)** | Proveedor Cloud | Destaca mucho en interfaces de Datos e IA con VertexAI o BigQuery. |
| **Streamlit** | Librería Deploy Python | Montas una interfaz web/Dashboard analítico completo programado EXCLUSIVAMENTE todo en Python. Ideal tu portfolio! |
| **Dash** | Librería Front/Back | Su hermano gemelo potenciado por Plotly. |
| **Docker** | Contenedores | "En mi máquina sí funciona". Para que en todo el mundo se ejecute igual, empaquetas la máquina entera en él. |

---

## 🧠 Herramientas Avanzadas & Misceláneas
| Herramienta | Foco General |
| :--- | :--- |
| **Beautiful Soup & Selenium** | El ABC para el Web Scraping y la automatización (con la 2ª navegas el click de botones en Webs reales). |
| **Apache Kafka** | El estándar si el dato hay que enviarlo en stream de mensajerías sin guardarlo. |
| **MLflow & Weights & Biases** | Data Science Avanzado: Llevar control de resultados de IA (Qué datos usaste para qué "Accuracy" consigues cada día iterando el cerebro del modelo). |

---

## 🧭 ¿Qué dominan tus Colegas? (Stack y Rutas)

Para que entiendas el flujo donde entras al integrarte con colegas de TI:

- 📊 **Si eres Data Analyst:** Pide un problema -> Te bajas los datos con `SQL` y `Pandas` -> Modelizas e Indagas -> Pintas un Cuadro de mando de métricas en `Power BI / Tableau`. 
- 🔬 **Si eres Data Scientist:** Pides problema a DA -> Preparas la ingesta a `Python` masivo-> Preparas y curas variables para el Modelado (Scikit, XGBoost) -> Comruebas su % real.
- ⚙️ **Si eres Data Engineer:** Miras donde hace agua la infraestructura -> Levantas clústeres de cálculo (`Spark, Airflow`) y limpias ingestas en `dbt/BigQuery` diariamente de noche -> Te abrazas al DevOps y a los contenedores.
- 🤖 **Si eres ML Engineer:** Tomas el modelo científico del DS, lo "limpias" para que vuele milisegundos en backend en tu lenguaje (C o PyTorch a fondo) -> Monitorizas drift en `MLFlow` montado en un endpoint vivo de la web.

> 💡 **Buenas Prácticas para Herramientas**
> 1. No te obsesiones con "aprender 5 herramientas cloud diferentes". Entiende los conceptos de CI/CD, escalabilidad y DW. Si conoces AWS (S3), migrar a GCP (GCS) es intuitivo.
> 2. Documenta tus dependencias en `requirements.txt`.
> 3. En la fase junior/mid, prioriza volverte fuerte en SQL puro y Pandas antes de querer volar en Deep Learning.
