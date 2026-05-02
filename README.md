Real-Time Crypto Dashboard using Kafka + Spring Boot + React

This project is a real-time data streaming system that demonstrates how to build a full-stack application using Apache Kafka (event streaming), Spring Boot (Producer & Consumer services), and React (Vite) for the frontend dashboard.
The system simulates real-time cryptocurrency price updates (generated data) and displays them in a live dashboard with charts.

Architecture Overview
Producer (Spring Boot) → Apache Kafka (Topic: test) → Consumer (Spring Boot) → WebSocket → Frontend (React Vite Dashboard)

Components 

Kafka Producer

Generates real-time crypto price data (BTC, ETH, SOL) and sends data to a Kafka topic. 

Runs automatically without needing an API trigger.

Tech: Spring Boot, KafkaTemplate

Kafka Consumer
Listens to the Kafka topic, processes incoming messages, and exposes data to the frontend via WebSocket.
Tech: Spring Boot, @KafkaListener

Frontend Dashboard
Built with React and Vite. 
Displays live prices, price changes, and charts (line, bar, dot). 
Updates every few seconds.
Features include tab-based UI (BTC, ETH, SOL) and real-time updates.


GitHub Repositories
This project is split into three independent services:

Producer Service
https://github.com/SurajMadhushan/kafka-producer-service.git

Consumer Service
https://github.com/SurajMadhushan/kafka-consumer-service.git

Frontend Dashboard (React Vite)
https://github.com/SurajMadhushan/kafka-react-frontend.git

Sample Data Format
{
"symbol": "BTC",
"price": 67234.12,
"timestamp": 1714459200000
}

Kafka Setup (KRaft Mode)
Generate Cluster ID
bin/windows/kafka-storage.bat random-uuid

Format storage
bin/windows/kafka-storage.bat format -t <CLUSTER_ID> -c config/kraft/server.properties

Start Kafka
bin/windows/kafka-server-start.bat config/kraft/server.properties

Features
Real-time data streaming using Kafka
Decoupled microservice architecture
Scalable event-driven design
Live updating dashboard
Custom chart rendering (Canvas-based)

What You Learn From This Project
Kafka fundamentals (Producer, Consumer, Topics)
Event-driven architecture
Real-time data pipelines
Spring Boot Kafka integration
React real-time UI updates
WebSocket streaming

Future Improvements
Add real crypto APIs (e.g., Binance)
Add authentication (JWT)
Deploy using Docker and AWS
Add persistent storage (MySQL)

Author
Suraj Madhushan
Software Engineering Student
University of Moratuwa

If you like this project, give it a star on GitHub and share