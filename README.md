# **Redis Streams Data Processing with Consumer Groups and Grafana Visualization**

## **Project Overview**  
This project demonstrates the use of **Redis Streams** for real-time data streaming and management, leveraging consumer groups for efficient data processing. The setup includes integration with **Grafana** for dynamic visualization of the data streams.

---

## **Features**  
- **Data Streaming:** Real-time data ingestion using Redis Streams.  
- **Consumer Groups:**  
  - Group 1: Processes historical data from the beginning of the stream.  
  - Group 2: Handles only new data generated after group creation.  
- **Dynamic Dashboards:** Visualize data in Grafana with updates from Redis Streams.

---

## **Setup Instructions**

### **1. Prerequisites**  
Ensure you have the following installed:  
- Docker  
- Redis  
- Grafana  

### **2. Pull Redis Docker Image**  
Start by pulling the Redis image and accessing the Redis CLI:  
```bash
docker pull redis
docker run -d -p 6379:6379 redis
redis-cli
```

### **3. Add Data to the Stream**  
Use the following command to add data to a Redis stream:  
```bash
XADD mystream * Source "web" Amount 250
```

### **4. Create Consumer Groups**  
- **Group 1:** Consumes all existing data in the stream.  
- **Group 2:** Consumes only new data generated after group creation.  

Create and configure groups via Redis CLI or a client.  

### **5. Read and Process Data**  
- Group 1 reads historical data from the beginning.  
- Group 2 processes real-time, newly added data.  

### **6. Visualize Data in Grafana**  
1. Configure Grafana to connect to the Redis instance using its IP and port.  
2. Add panels to visualize metrics from the Redis stream.  
3. Apply updates to reflect changes dynamically.  

---

## **Commands Reference**

### Add Data to Redis Stream  
```bash
XADD mystream * Source "mobile" Amount 100
```

### Read Data from Stream  
```bash
XRANGE mystream - +
```

### Inspect Consumer Groups  
```bash
XINFO GROUPS mystream
```

---

## **Technology Stack**  
- **Redis Streams:** Real-time data streaming.  
- **Consumer Groups:** Efficient parallel data consumption.  
- **Grafana:** Data visualization and monitoring.  
- **Docker:** Environment setup and management.  

---

## **Future Enhancements**  
- Automate consumer creation and data ingestion.  
- Expand visualizations to include additional metrics.  
- Integrate alerting mechanisms within Grafana.

---

## **Author**  
Aya Yahia  
[LinkedIn](https://linkedin.com/in/aya-yahia-37522a217) | [GitHub](https://github.com/aya-yahia-1november)  

---  

Feel free to explore, contribute, or reach out with suggestions!
