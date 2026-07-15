# Data Science Fundamentals with Python and SQL Specialization
## Module 3 — Libraries, APIs, Datasets & Machine Learning Models

---

## Libraries for Data Science

> A **library** is a collection of functions and methods that let you perform actions without writing the code yourself.

### Scientific Computing Libraries (Python)

| Library | What It Does |
|---------|-------------|
| **Pandas** | Data cleaning, manipulation, and analysis. Works with DataFrames (2D tables of rows and columns) |
| **NumPy** | Based on arrays and matrices. Allows mathematical functions on arrays. Pandas is built on top of NumPy |

### Data Visualization Libraries (Python)

| Library | What It Does |
|---------|-------------|
| **Matplotlib** | Most well-known. Creates graphs and plots. Easily customizable |
| **Seaborn** | Built on top of Matplotlib. Creates heat maps, time series, and violin plots |

### Machine Learning Libraries (Python)

| Library | What It Does |
|---------|-------------|
| **Scikit-learn** | Statistical modeling — regression, classification, clustering. Built on NumPy, SciPy, Matplotlib |
| **Keras** | High-level. Build deep learning models quickly and simply. Runs on GPU |
| **TensorFlow** | Low-level. Used for large-scale production of deep learning models |
| **PyTorch** | Used for experimentation — easy for researchers to test ideas |

### Cluster Computing

| Library | What It Does |
|---------|-------------|
| **Apache Spark** | General-purpose cluster computing. Processes data in parallel across multiple computers. Has similar functionality to Pandas, NumPy, and Scikit-learn. Supports Python, R, Scala, and SQL |

### Scala Libraries

| Library | What It Does |
|---------|-------------|
| **Vegas** | Statistical data visualization. Works with data files and Spark DataFrames |
| **BigDL** | Deep learning for Spark |

### R Libraries

| Library | What It Does |
|---------|-------------|
| **ggplot2** | Popular data visualization library for R |

> R was the de-facto standard for open-source data science, but Python is now superseding it.

---

## Application Programming Interfaces (APIs)

### What is an API?
- An **API** allows communication between two pieces of software
- You use the API to send inputs and receive outputs — without knowing what happens at the back end
- The API is the **interface** — it is the part of the library you see

### How APIs Work (Example — Pandas)
- Pandas has software components, not all written in Python
- You use the Pandas API to process data by communicating with those components
- TensorFlow is written in C++ but has APIs for Python, JavaScript, Java, Go, and more

### REST APIs
- **REST** = Representational State Transfer
- Allow communication **over the internet**
- Give access to resources like storage, data, and AI algorithms

### Key REST API Terms

| Term | Meaning |
|------|---------|
| **Client** | You or your code |
| **Resource** | The web service being accessed |
| **Endpoint** | The URL where the client finds the service |
| **Request** | What the client sends to the resource |
| **Response** | What the resource sends back |

### How REST API Communication Works
1. Client sends an **HTTP request** containing a **JSON file** with instructions
2. The web service performs the operation
3. The web service returns an **HTTP response** with a **JSON file** containing the result

### REST API Examples

| API | What It Does |
|-----|-------------|
| **Watson Speech-to-Text** | Send audio file (POST request) → receive text transcription (GET request) |
| **Watson Language Translator** | Send text → receive translated text (e.g. English to Spanish) |

---

## Data Sets — Powering Data Science

### What is a Dataset?
- A **structured collection of data**
- Data can be text, numbers, images, audio, or video

### Types of Data Formats

| Format | Description |
|--------|-------------|
| **Tabular (CSV)** | Rows and columns. Each row = one record. Most common format |
| **Hierarchical** | Organized in a tree-like structure |
| **Network** | Stored as a graph (e.g. social network connections) |
| **Raw files** | Images, audio (e.g. MNIST — handwritten digit images) |

### Types of Data Ownership

| Type | Description |
|------|-------------|
| **Private data** | Contains confidential or proprietary information. Not shared publicly |
| **Open data** | Made available to the public for free by governments, institutions, and companies |

### Where to Find Open Datasets
- **datacatalogs.org** — comprehensive list of data portals worldwide
- **Kaggle** — popular data science community with many datasets
- **United Nations, European Union** — government data repositories
- **Google Dataset Search** — search engine for finding datasets

### Community Data License Agreement (CDLA)
Created by the **Linux Foundation** to handle open data licensing properly.

| License | What It Allows |
|---------|---------------|
| **CDLA-Sharing** | Use and modify data. If you publish your modified version, you must use the same license |
| **CDLA-Permissive** | Use and modify data. You are NOT required to share your changes |

> Neither license restricts the results or models you build using the data.

### Dataset License Types (Summary)

| License | Key Rule |
|---------|----------|
| **Public Domain** | No restrictions — fully open |
| **CC-BY** | Must give credit to creator |
| **CC-BY-SA** | Must give credit + share changes under same license |
| **CC-BY-NC** | Must give credit + no commercial use |
| **CC-BY-ND** | Must give credit + no modifications allowed |
| **CDLA-Permissive** | Use and modify freely, include disclaimer |
| **CDLA-Sharing** | Use and modify, but share changes under same license |

---

## Machine Learning Models

### What is Machine Learning?
- ML uses **algorithms (models)** to identify patterns in data
- **Model training** = the process by which the model learns patterns from data
- Once trained, the model makes **predictions** on new data

### Three Types of Machine Learning

| Type | How It Works | Examples |
|------|-------------|---------|
| **Supervised Learning** | Human provides input data AND correct outputs. Model learns the relationship | Regression, Classification |
| **Unsupervised Learning** | Data has no labels. Model finds patterns on its own | Clustering, Anomaly detection |
| **Reinforcement Learning** | Model learns by trial and error to maximize rewards | Game playing (Go, Chess) |

### Supervised Learning — Two Model Types

| Model | Purpose | Example |
|-------|---------|---------|
| **Regression** | Predict a numeric value | Predicting house prices based on size and location |
| **Classification** | Predict which category data belongs to | Detecting spam emails |

### Unsupervised Learning — Examples
- **Clustering** — group records into similar categories (e.g. purchase recommendations)
- **Anomaly detection** — find outliers (e.g. fraudulent credit card transactions)

### Deep Learning
- A specialized subset of machine learning
- Loosely emulates how the **human brain** solves problems
- Used for: natural language, images, audio, video, time series forecasting
- Requires: **large labeled datasets**, significant compute power, **special hardware (GPU)**
- Frameworks: **TensorFlow, PyTorch, Keras**
- Pre-trained models available from **model zoos** (TensorFlow, PyTorch, Keras, ONNX)

### Steps to Build a Deep Learning Model
1. Collect and prepare data (label it — e.g. draw bounding boxes around objects)
2. Build or select an existing model
3. Train the model on your data
4. Analyze results and repeat until performance meets requirements
5. Deploy the model to make it available to applications

---

## The Model Asset eXchange (MAX)

### What is MAX?
- A **free, open-source repository** of ready-to-use deep learning models on IBM Developer platform
- Reduces **time to value** by providing pre-trained models
- All models available under **permissive open-source licenses** (safe for personal and commercial use)

### What MAX Offers
- Object detection, image/audio/video/text classification
- Named entity recognition, image-to-text translation, human pose detection, and more

### Components of a MAX Model-Serving Microservice
1. Pre-trained deep learning model
2. Code that **pre-processes** the input
3. Code that **post-processes** the model output
4. A **standardized public API** that exposes the service to applications

### How MAX Microservices Are Deployed
- Built and distributed as **open-source Docker images**
- Source published on **GitHub**
- Use **Kubernetes** to automate deployment, scaling, and management
- **Red Hat OpenShift** — popular enterprise Kubernetes platform
- Available on: IBM Cloud, Google Cloud, AWS, Microsoft Azure

---

## Quiz 1 — Libraries, APIs, Datasets & ML

**Q1: Which of the following libraries is NOT mentioned as a high-level visualization library?**
- Seaborn
- ✅ **TensorFlow**
- Matplotlib
- Plotly

**Q2: What does the acronym "API" stand for?**
- ✅ **Application Programming Interface**
- Algorithmic Processing Interface
- Algorithmic Program Interface
- Application Process Interface

**Q3: What is the best way to represent network data?**
- Tabular format
- ✅ **As a graph**
- Comma-separated values
- In a tree-like structure

**Q4: What is the primary role of an API in software?**
- Access to proprietary IBM data sets only
- ✅ **It allows communication between two pieces of software**
- Data sets exclusively for academic use
- It stores data in the cloud

**Q5: Which of the following are machine learning models? (Select all that apply)**
- Model training
- ✅ **Unsupervised Learning**
- ✅ **Supervised Learning**
- ✅ **Reinforcement Learning**

**Q6: Which of the following is an example of a tabular data format?**
- MP3
- JSON
- PNG
- ✅ **CSV**

---

## Quiz 2 — Deep Dive

**Q1: Which library is used for machine learning?**
- Matplotlib
- NumPy
- Pandas
- ✅ **Scikit-learn**

**Q2: What is the main purpose of an Application Programming Interface (API)?**
- Facilitate communication between hardware components
- ✅ **Allow communication between software components**
- Design user interfaces for applications
- Create graphical representations of data

**Q3: In a REST API architecture, what does the client typically receive from the web service after sending a request?**
- ✅ **JSON file**
- Binary data
- HTML file
- XML document

**Q4: What term is used to describe a structured collection of data?**
- ✅ **Data Set**
- Data Store
- Data Format
- Data Grid

**Q5: What type of resources are available for developers on the Data Asset eXchange (DAX) platform?**
- Only pre-trained machine learning models
- ✅ **Curated collections of open data sets along with tutorial notebooks**
- Only raw data files without any associated documentation
- Only proprietary data sets with restricted access

**Q6: What is the primary task of model training in machine learning?**
- ✅ **Identifying patterns in the data**
- Evaluating the model
- Preparing the data
- Making predictions

**Q7: Which type of machine learning model is primarily used to predict a numeric value?**
- Clustering
- Classification
- ✅ **Regression**
- Reinforcement

**Q8: Which of the following statements is true regarding deep learning models?**
- ✅ **Deep learning models emulate how the human brain solves problems**
- Deep learning models require small data sets for training
- Deep learning models are only used for natural language processing tasks
- Deep learning models do not require specialized hardware for training

**Q9: What is a key difference between CDLA-Sharing and CDLA-Permissive?**
- ✅ **CDLA-Permissive allows private use of modifications**
- CDLA-Permissive requires modifications to be shared
- CDLA-Sharing does not allow modification
- CDLA-Sharing restricts data to academic use only

**Q10: Which type of learning involves the model learning from rewards or penalties?**
- ✅ **Reinforcement Learning**
- Unsupervised Learning
- Regression Learning
- Supervised Learning
---
