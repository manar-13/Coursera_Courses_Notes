# Data Science Fundamentals with Python and SQL Specialization
## Module 1 — Data Science Tools

---

## Categories of Data Science Tools

### The Data Science Pipeline (in order)

1. **Data Management** – collect, store, and retrieve data (from sources like sensors, social media, etc.)
2. **Data Integration & Transformation (ETL)** – Extract data from multiple places → Transform it (clean/reformat) → Load it into a Data Warehouse
3. **Data Visualization** – Turn data into charts, maps, plots so decision-makers understand it
4. **Model Building** – Train machine learning algorithms on data so the system learns to make predictions
5. **Model Deployment** – Make the model available to other applications via APIs
6. **Model Monitoring & Assessment** – Continuously check the model's accuracy and fairness using metrics (like F1 score)

---

### The 4 Support Systems

| Tool Type | What It Does | Example |
|-----------|-------------|---------|
| Code Asset Management | Version control + team collaboration on code | GitHub |
| Data Asset Management (DAM) | Organize, store, and control access to your data | DAM platforms |
| Development Environments (IDEs) | Where you write, test, and deploy code | IBM Watson Studio |
| Execution Environments | Runs and compiles your code (cloud-based) | IBM Watson Studio |

---

## Open-Source Tools for Data Science

### Data Management Tools
- **Relational databases:** MySQL, PostgreSQL
- **NoSQL databases:** MongoDB, Apache CouchDB, Apache Cassandra
- **File-based:** Hadoop File System, Ceph
- **Search:** Elasticsearch – stores text and creates search indexes for fast retrieval

### Data Integration & Transformation Tools
- **ETL vs ELT** — ELT is the newer approach: dump the data first, transform later
- Tools: Apache AirFlow, KubeFlow, Apache Kafka, Apache Nifi, Apache SparkSQL, NodeRED

### Data Visualization Tools
- Pixie Dust, Hue, Kibana, Apache Superset

### Model Deployment Tools
- Apache PredictionIO, Seldon, MLeap
- **TensorFlow** can deploy to: servers, Raspberry Pi (TF Lite), web browsers (TF.js)

### Model Monitoring Tools
- **ModelDB** — stores info about your models
- **Prometheus** — general monitoring tool, used for ML too
- **IBM AI Fairness 360** — detects bias against groups (gender, race, etc.)
- **IBM Adversarial Robustness 360** — protects model from attackers
- **IBM AI Explainability 360** — explains why a model made a decision (removes the "black box" problem)

### Code Asset Management
- **Git** is the industry standard. GitHub, GitLab, Bitbucket are built on top of it.

### Data Asset Management
- Apache Atlas, ODPi Egeria, Kylo

---

## IBM Model Development Tools

| Tool | What It Does |
|------|-------------|
| Watson Studio | Full environment to build, train, and deploy models. Supports Python, R, TensorFlow |
| IBM AutoAI | Lives inside Watson Studio. Automatically tests different algorithms to find the best model for your data |
| Watson OpenScale | Monitors models in production — checks for bias, fairness, and performance over time |
| Watson Machine Learning | Cloud service to train and deploy models at scale. Works with TensorFlow, PyTorch, scikit-learn |

---

## Open-Source Tools — Part 2

### Development Environments (IDEs)

| Tool | Key Fact |
|------|----------|
| Jupyter Notebook | Most popular. Combines code, output, and documentation in one place |
| JupyterLab | The newer version of Jupyter. Will eventually replace it. More flexible layout |
| Apache Zeppelin | Similar to Jupyter but plotting requires no coding — built in |
| RStudio | Best for R language. Oldest (2011). Combines coding, debugging, and visualization |
| Spyder | Like RStudio but for Python. Less powerful but still useful |

### Cluster Execution Environments
*(For when your data is too big for one computer)*

| Tool | Key Fact |
|------|----------|
| Apache Spark | Most popular. Processes large data in batches. Doubles performance when you double servers |
| Apache Flink | Focuses on real-time streaming data (vs Spark's batch processing) |
| Ray | Newest. Built specifically for large-scale deep learning training |

### Visual Tools (No Coding Needed)
- **KNIME** — drag and drop, built-in visualization, can connect to Spark and use Python/R
- **Orange** — easier than KNIME but less flexible

---

## Commercial Tools for Data Science

### Data Management
- Oracle Database, Microsoft SQL Server, IBM Db2 — the 3 industry standards in enterprises

### Data Integration & Transformation (ETL)
- **Informatica PowerCenter** and **IBM InfoSphere DataStage** — the top 2 leaders
- Others: SAP, Oracle, SAS, Talend, Microsoft
- Watson Studio Desktop has a tool called **Data Refinery** — works like a spreadsheet for ETL

### Data Visualization (BI Tools)
- **Tableau, Microsoft Power BI, IBM Cognos Analytics** — the big 3 for business dashboards

### Model Building
- **SPSS Modeler** and **SAS Enterprise Miner** — main commercial tools for machine learning models

### Model Deployment
- Tightly built into the model-building tools (example: SPSS exports models as **PMML** format so other tools can read them)

### Model Monitoring & Code Asset Management
- No strong commercial tools yet — open source is still the better choice here

### Data Asset Management (Governance)
- **Informatica Enterprise Data Governance** and **IBM Information Governance Catalog**
- Covers: data dictionary, data ownership, data lineage, privacy rules

### Fully Integrated Tools
- **Watson Studio + Watson OpenScale** — covers the full data science lifecycle
- **H2O Driverless AI** — another fully integrated commercial option

---

## Cloud-Based Tools for Data Science

### Fully Integrated Cloud Platforms
- **Watson Studio + Watson OpenScale** — covers the complete data science lifecycle
- **Microsoft Azure Machine Learning** — same idea, Microsoft's version
- **H2O Driverless AI** — download and install, but deploys to any cloud with one click

### Data Management (Cloud/SaaS versions)
- **AWS DynamoDB** — NoSQL database, stores data as key-value or JSON format
- **Cloudant** — cloud database built on Apache CouchDB, cloud provider handles all maintenance
- **IBM Db2 as a service** — commercial database available as SaaS on cloud

### Data Integration & Transformation
- **Informatica Cloud Data Integration** — cloud ETL leader
- **IBM Data Refinery** — part of Watson Studio, transforms raw data in a spreadsheet-like interface

### Data Visualization
- **Datameer** — cloud-based visualization tool
- **IBM Cognos** — available as cloud solution too

### Model Building
- **Watson Machine Learning** — trains and builds models on IBM cloud
- **Google AI Platform Training** — Google's equivalent

### Model Monitoring
- **Amazon SageMaker Model Monitor** — monitors deployed models continuously on AWS
- **Watson OpenScale** — IBM's monitoring tool

---

## Quiz 1 — Categories & Open-Source Tools

**Q1: Which Data Science category involves extracting, transforming, and loading data?**
- Data Visualization
- Data Management
- Model Building
- ✅ **Data Integration and Transformation**

**Q2: Which task category uses charts, plots, and maps to help decision-makers?**
- Data Management
- Data Integration and Transformation
- ✅ **Data Visualization**
- Model Building

**Q3: Which tool is commonly used for code asset management?**
- ModelDB
- MySQL
- Apache PredictionIO
- ✅ **Git**

**Q4: Which open-source notebook tool supports multiple programming languages through kernels?**
- Spyder
- ✅ **Jupyter**
- RStudio
- Apache Spark

**Q5: Which tool tracks the performance of deployed models in production?**
- MySQL
- ModelDB
- ✅ **Fiddler**
- GitHub

**Q6: Which is an example of a cloud-based execution environment for model training and deployment?**
- ✅ **IBM Watson Studio**
- Db2
- Amazon S3
- Datameer

---

## Quiz 2 — Commercial & Cloud Tools

**Q1: Which of the following commercial tools is often used for data management in enterprises?**
- Apache Kafka
- Jupyter Notebook
- TensorFlow
- ✅ **Oracle Database**

**Q2: Which commercial data integration and transformation tools are identified as leaders?**
- ✅ **Informatica PowerCenter and IBM InfoSphere DataStage**
- Oracle Database and IBM Db2
- SPSS Modeler and SAS Enterprise Miner
- Watson Studio and Watson OpenScale

**Q3: Which tools support the complete development lifecycle for data science, ML, and AI tasks?**
- Apache Cassandra
- IBM SPSS Modeler
- ✅ **Watson Studio and Watson OpenScale**
- MySQL

**Q4: Which cloud-based tool offers a NoSQL database service called DynamoDB?**
- ✅ **Amazon Web Services (AWS)**
- Google BigQuery
- Microsoft Azure
- IBM Db2

**Q5: Which tools can be used for model deployment? (Select all that apply)**
- ✅ **Watson Machine Learning**
- MySQL
- Google Analytics
- Watson OpenScale
- ✅ **SPSS Collaboration and Deployment Services**

**Q6: Which statements are true about Watson Studio and Watson OpenScale? (Select all that apply)**
- ✅ **They can support both model development and model monitoring activities**
- ✅ **They can be deployed in local data centers and Kubernetes-based platforms**
- ✅ **They can be used together to support tasks across the data science lifecycle**

---

## Quiz 3 — Applied Scenarios

**Q1: A retail company extracts customer data into one central location for large-scale reporting. What is the central repository mainly used for?**
- Managing source code changes across a team
- Training machine learning models directly
- Monitoring fairness and robustness of deployed models
- ✅ **Collecting and storing large volumes of data for later analysis**

**Q2: A health team converts height/weight to metric units before loading into the warehouse. Which part of ETL is this?**
- Visualization
- Extraction
- ✅ **Transformation**
- Deployment

**Q3: Which are code asset management tool choices? (Select all that apply)**
- ModelDB
- ✅ **GitLab**
- ✅ **GitHub**
- ✅ **Bitbucket**
- Apache Atlas

**Q4: Which tools are open-source data integration and transformation tools? (Select all that apply)**
- Kibana
- ✅ **Apache Nifi**
- ✅ **NodeRED**
- ✅ **Apache Kafka**
- Prometheus

**Q5: A Python user wants a visualization tool with a UI, not just code. Which tool fits?**
- ✅ **Pixie Dust**
- Hue
- Apache Superset
- Kibana

**Q6: Which tools relate to model monitoring, fairness, robustness, and explainability? (Select all that apply)**
- ✅ **IBM AI Fairness 360**
- TensorFlow Lite
- Hue
- ✅ **IBM AI Explainability 360**
- ✅ **IBM Adversarial Robustness 360 Toolbox**

**Q7: Which statements about open-source development environments are correct? (Select all that apply)**
- ✅ **Apache Zeppelin provides integrated plotting capability**
- ✅ **Apache Spark has linear scalability**
- ✅ **JupyterLab allows users to open different file types and arrange them on a canvas**
- Spyder is described as the primary tool for code asset management
- RStudio is presented as a stream-processing engine for real-time data

**Q8: A company needs real-time stream processing, not batch. Which tool is better?**
- Ray
- ✅ **Apache Flink**
- RStudio
- Apache Spark

**Q9: A business team wants commercial tools for visual reports and live dashboards. Which type fits?**
- ✅ **Business intelligence and data visualization tool**
- Data asset management tool
- Model deployment service
- Code asset management platform

**Q10: Which cloud tool pairings are correct? (Select all that apply)**
- Cloudant — model deployment service
- ✅ **Watson Machine Learning — model building**
- ✅ **Watson Studio and Watson OpenScale — complete development lifecycle coverage**
- ✅ **Amazon SageMaker Model Monitor — continuous monitoring of deployed models**
- Datameer — code asset management
---
