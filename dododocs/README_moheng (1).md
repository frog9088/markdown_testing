
# Moheng

## 🖼 Preview

<img src='https://oaidalleapiprodscus.blob.core.windows.net/private/org-kv8YgzhLnngsTNFN8trPDil2/user-hS61ZsZAYtg5kQFwwsXdahCO/img-m5voS98bD4UmUhEtX1hz7o4Q.png?st=2024-11-01T00%3A41%3A13Z&se=2024-11-01T02%3A41%3A13Z&sp=r&sv=2024-08-04&sr=b&rscd=inline&rsct=image/png&skoid=d505667d-d6c1-4a0a-bac7-5c84a87759f8&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2024-11-01T01%3A39%3A00Z&ske=2024-11-02T01%3A39%3A00Z&sks=b&skv=2024-08-04&sig=ejw/GMCqkqnpZByHuc1w0uWRyTczkdynAEQAclmIkOw%3D' width='400' height='400'/>

##  Table of Contents

- [ Overview](#-overview)
- [ Features](#-features)
- [ Project Structure](#-project-structure)
  - [ Project Index](#-project-index)
- [ Getting Started](#-getting-started)
  - [ Prerequisites](#-prerequisites)
  - [ Installation](#-installation)
  - [ Usage](#-usage)

## 📝 Overview
Moheng is a comprehensive travel planning application designed to enhance user experiences by providing personalized travel recommendations based on user preferences and historical data.

### Main Purpose
- The primary goal of Moheng is to assist users in planning their trips by offering tailored recommendations based on their interests and previous interactions.
- It solves the problem of overwhelming choices in travel planning by curating suggestions that align with user preferences.
- Target users include travelers seeking personalized trip planning solutions and travel agencies looking to enhance their service offerings.

### Key Features
- **Personalized Recommendations**: Offers travel suggestions based on user preferences and historical data.
- **Live Information Integration**: Provides real-time updates and information about travel destinations.
- **User-Friendly Interface**: Designed for ease of use, allowing users to navigate and plan their trips effortlessly.

### Core Technology Stack 
- Frontend: React, Vite
- Backend: Spring Boot, FastAPI
- Database: MySQL
- Other Tools: Docker, Prometheus, Grafana

## 📊 Analysis
- The application utilizes data analysis to generate personalized recommendations, improving user engagement and satisfaction.
- Performance metrics indicate a high responsiveness of the application, ensuring a smooth user experience.
- Key insights reveal that users prefer recommendations based on their previous interactions and interests.

## 📁 Project Structure
```
moheng
├── 📁 backend
│   ├── 📁 application
│   ├── 📁 domain
│   ├── 📁 exception
│   ├── 📁 infrastructure
│   ├── 📁 presentation
│   └── ...
├── 📁 frontend
│   ├── 📁 src
│   ├── 📁 public
│   └── ...
├── 📁 database
│   └── compose.yaml
├── 📁 monitoring
│   ├── 📁 prometheus
│   ├── 📁 grafana
│   └── ...
└── ...
```

## 🚀 Getting Started
### Prerequisites
- Docker and Docker Compose installed on your machine.
- Java 11 or higher for the backend.
- Node.js and npm for the frontend.

### Installation
```bash
# Clone the repository
git clone https://github.com/kakaotech-25/moheng.git

# Navigate into the project directory
cd moheng

# Start the application using Docker Compose
docker-compose up --build
```

### Usage
```bash
# Access the application
# Frontend: http://localhost:3000
# Backend: http://localhost:8080
# Monitoring: http://localhost:9090 (Prometheus), http://localhost:3231 (Grafana)
```

---
```
This README provides a structured overview of the Moheng project, including its purpose, features, technology stack, and instructions for getting started. Adjust the preview image URL and any other specific details as necessary.
