
# **Project Name:**

![Project Logo](https://img.icons8.com/fluency/48/000000/stock-share.png)  **StockFlow: Kafka Real-Time Stock Market Data Engineering**

---

## **Project Description**

📊 **StockFlow** is an advanced data engineering project designed to process and analyze real-time stock market data. Leveraging the power of **Apache Kafka** for data streaming, **Python** for processing, **Jupyter Notebooks** for analysis, and a suite of **AWS services**, StockFlow provides a robust and scalable solution for handling high-velocity financial data. This project not only demonstrates key data engineering principles but also showcases the seamless integration of various modern technologies to build an efficient real-time data processing pipeline, making it an ideal resource for anyone interested in real-time data processing and big data technologies.

---

## **Key Features**

- ![Kafka](https://www.vectorlogo.zone/logos/apache_kafka/apache_kafka-icon.svg) **Real-Time Data Streaming**: Implemented using **Apache Kafka** to handle high-throughput and low-latency data streams.
- ![Python](https://img.icons8.com/color/48/000000/python.png) **Data Producers & Consumers**: Custom **Python** scripts act as Kafka producers and consumers to process and manipulate real-time stock data.
- ![AWS](https://img.icons8.com/color/48/000000/amazon-web-services.png) **Scalable Architecture**: Utilizes **AWS services** including **Amazon S3**, **Athena**, and **Glue** for scalable data storage, querying, and cataloging.
- ![S3](https://img.icons8.com/color/48/000000/amazon-s3.png) **Data Storage & Management**: S3 buckets are used for storing raw and processed data, while AWS Glue crawlers automate data cataloging.
- ![Athena](https://d1.awsstatic.com/logos/aws/Athena.svg) **Analytical Querying**: **Amazon Athena** is employed for SQL-based querying of large datasets, enabling quick insights and data retrieval.
- ![Jupyter](https://jupyter.org/assets/homepage/main-logo.svg) **Visualization**: **Jupyter Notebooks** are used for exploratory data analysis and visualization, providing insights into stock market trends and patterns.

---

## **Project Architecture**

![Architecture Diagram](https://miro.medium.com/max/1400/1*5QInE2LeekRtbFLfFwYO8g.png)

1. ![Kafka](https://www.vectorlogo.zone/logos/apache_kafka/apache_kafka-icon.svg) **Data Ingestion (Kafka Producer)**:
   - A Python-based Kafka producer fetches real-time stock market data from external APIs and publishes it to Kafka topics.

2. ![Kafka](https://www.vectorlogo.zone/logos/apache_kafka/apache_kafka-icon.svg) **Data Processing (Kafka Consumer)**:
   - Kafka consumers read data from Kafka topics, process it (e.g., filtering, aggregation), and prepare it for storage.

3. ![S3](https://img.icons8.com/color/48/000000/amazon-s3.png) **Data Storage (Amazon S3 & AWS Glue)**:
   - Processed data is stored in Amazon S3 buckets.
   - AWS Glue crawlers automatically catalog the data, making it queryable through Athena.

4. ![Athena](https://d1.awsstatic.com/logos/aws/Athena.svg) **Data Analysis (Amazon Athena & Jupyter Notebooks)**:
   - Amazon Athena provides a serverless query service to analyze the data directly from S3 using SQL.
   - Jupyter Notebooks are used for further data exploration, visualization, and generating reports.

5. <img src="https://www.vectorlogo.zone/logos/apache_zookeeper/apache_zookeeper-icon.svg" alt="Zookeeper" height="48"/>**Monitoring & Alerts**:
   - Zookeeper manages the Kafka cluster, ensuring high availability and performance.

---

## **Setup & Installation**

### **1. Create an AWS EC2 Instance**

- **Step 1**: Launch an EC2 instance from the AWS Management Console.
- **Step 2**: Connect to your EC2 instance using SSH.

```bash
ssh -i "kafka-stock-market-keypair.pem" ec2-user@ec2-3-68-158-206.eu-central-1.compute.amazonaws.com
```

### **2. Download and Install Apache Kafka**

- **Step 1**: Download Apache Kafka.

```bash
wget https://dlcdn.apache.org/kafka/3.8.0/kafka_2.13-3.8.0.tgz
```

- **Step 2**: Extract the downloaded Kafka tar file.

```bash
tar -xzf kafka_2.13-3.8.0.tgz
```

### **3. Download and Install Java**

- **Step 1**: Install OpenJDK using `yum`.

```bash
sudo yum install java-22-amazon-corretto-devel
```

### **4. Start Zookeeper Server**

- **Step 1**: Navigate to the Kafka directory and start the Zookeeper server.

```bash
bin/zookeeper-server-start.sh config/zookeeper.properties
```

### **5. Start Kafka Server**

- **Step 1**: Start the Kafka server.

```bash
bin/kafka-server-start.sh config/server.properties
```

### **6. Create Kafka Topics**

- **Step 1**: Create a new Kafka topic.

```bash
bin/kafka-topics.sh --create --topic demo_testing --bootstrap-server 3.68.158.206:9092 --replication-factor 1 --partitions 1
```

### **7. Create Kafka Producer & Consumer**

- **Step 1**: Start the Kafka producer.

```bash
bin/kafka-console-producer.sh --topic demo_testing --bootstrap-server 3.68.158.206:9092
```

- **Step 2**: Start the Kafka consumer.

```bash
bin/kafka-console-consumer.sh --topic demo_testing --bootstrap-server 3.68.158.206:9092
```

### **8. AWS Integration**

- ![S3](https://img.icons8.com/color/48/000000/amazon-s3.png) **Amazon S3**: Store raw and processed data.
- ![Glue](https://img.icons8.com/color/48/000000/glue.png) **AWS Glue**: Use crawlers for automated data cataloging.
- ![Athena](https://d1.awsstatic.com/logos/aws/Athena.svg) **Amazon Athena**: Query data stored in S3 using SQL for quick insights.

---

## **Project Structure**

```
StockFlow/
│
├── kafka/
│   ├── producer.py          # Kafka producer script
│   ├── consumer.py          # Kafka consumer script
│   ├── zookeeper.properties # Zookeeper configuration
│   └── server.properties    # Kafka server configuration
│
├── aws/
│   ├── s3_setup             # S3 bucket setup script
│   ├── glue_crawler         # AWS Glue crawler setup script
│   └── athena_queries       # Sample Athena queries
│
├── notebooks/
│   ├── data_analysis        # Jupyter notebook for data analysis
│   └── visualization        # Jupyter notebook for data visualization
│
├── requirements.txt         # Project dependencies
├── README.md                # Project documentation
└── LICENSE                  # License information
```

---

## **Contributing**

I welcome contributions to **StockFlow**! Feel free to submit issues, fork the repository, and create pull requests.
---

## **Contact**

For any inquiries or support, please contact:

- **Name**: Farhan Shahriyar
- **GitHub**: [Shahriyar31](https://github.com/Shahriyar31)

---

## **Technologies Used**

<p align="center">
  <img src="https://www.vectorlogo.zone/logos/apache_kafka/apache_kafka-icon.svg" alt="Kafka" height="48"/>
  <img src="https://img.icons8.com/color/48/000000/python.png" alt="Python"/>
  <img src="https://jupyter.org/assets/homepage/main-logo.svg" alt="Jupyter" height="48"/>
  <img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg" alt="AWS" height="48"/>
  <img src="https://img.icons8.com/color/48/000000/amazon-s3.png" alt="Amazon S3"/>
  <img src="https://img.icons8.com/color/48/000000/glue.png" alt="AWS Glue"/>
  
  <img src="https://www.vectorlogo.zone/logos/apache_zookeeper/apache_zookeeper-icon.svg" alt="Zookeeper" height="48"/>
  <img src="https://img.icons8.com/color/48/000000/linux.png" alt="Linux"/>
</p>

---
