# Moheng Travel Recommendation System
- A comprehensive travel recommendation system that utilizes user preferences and AI models to suggest travel destinations and activities.

## 📝 Description
This project is designed to provide personalized travel recommendations based on user preferences and historical data. It integrates various technologies to create a seamless experience for users looking to explore new travel destinations.

### Key features
- Personalized travel recommendations based on user preferences.
- Integration with AI models for enhanced suggestion accuracy.
- User-friendly API for easy access to travel data.
- Support for multiple social login providers.

### Core technology stack used
- **Frontend**: React, Vite
- **Backend**: Spring Boot, FastAPI
- **Database**: PostgreSQL
- **AI/ML**: Custom recommendation algorithms
- **Caching**: In-memory caching for performance optimization

## 🖼 Preview

![Generated Image](https://oaidalleapiprodscus.blob.core.windows.net/private/org-kv8YgzhLnngsTNFN8trPDil2/user-hS61ZsZAYtg5kQFwwsXdahCO/img-iCBQIru17mAFztw7ktnyHv9I.png?st=2024-10-31T11%3A00%3A16Z&se=2024-10-31T13%3A00%3A16Z&sp=r&sv=2024-08-04&sr=b&rscd=inline&rsct=image/png&skoid=d505667d-d6c1-4a0a-bac7-5c84a87759f8&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2024-10-31T01%3A19%3A25Z&ske=2024-11-01T01%3A19%3A25Z&sks=b&skv=2024-08-04&sig=aU7G517F8bUZt0gk72s7508SEIB/9oH9qK5w2GptP04%3D)


<img src="https://oaidalleapiprodscus.blob.core.windows.net/private/org-kv8YgzhLnngsTNFN8trPDil2/user-hS61ZsZAYtg5kQFwwsXdahCO/img-iCBQIru17mAFztw7ktnyHv9I.png?st=2024-10-31T11%3A00%3A16Z&se=2024-10-31T13%3A00%3A16Z&sp=r&sv=2024-08-04&sr=b&rscd=inline&rsct=image/png&skoid=d505667d-d6c1-4a0a-bac7-5c84a87759f8&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2024-10-31T01%3A19%3A25Z&ske=2024-11-01T01%3A19%3A25Z&sks=b&skv=2024-08-04&sig=aU7G517F8bUZt0gk72s7508SEIB/9oH9qK5w2GptP04%3D" width="200" height="400"/>


## 📊 Analysis
The analysis of the recommendation system reveals several key findings:
- The system effectively utilizes user click data to improve recommendation accuracy.
- Performance metrics indicate a response time of under 200ms for API calls.
- Insights from user interactions suggest a strong preference for personalized recommendations based on past travel history.

## 📁 Project Structure
```
[project root]
├── 📁 frontend
│   ├── vite.config.js
│   └── src
│       ├── api
│       │   └── Axios.js
│       └── ...
├── 📁 ai
│   ├── main.py
│   ├── containers.py
│   ├── model
│   │   └── Recommendation.py
│   └── ...
└── 📁 backend
    ├── src
    │   ├── main/java/moheng
    │   │   ├── auth
    │   │   ├── keyword
    │   │   ├── liveinformation
    │   │   ├── member
    │   │   ├── planner
    │   │   ├── recommendtrip
    │   │   └── trip
    │   └── ...
    └── ...
```

## 🚀 Getting Started

### Prerequisites
- Node.js and npm for the frontend
- Python and FastAPI for the AI model
- Java and Spring Boot for the backend
- PostgreSQL for the database

### Installation
```bash
# Clone the repository
git clone [repository URL]

# Navigate to the frontend directory and install required packages
cd frontend
npm install

# Navigate to the backend directory and install required packages
cd backend
./mvnw install

# Navigate to the AI directory and install required packages
cd ai
pip install -r requirements.txt

# Configure environment variables as needed
```

### Usage
```bash
# To run the frontend
cd frontend
npm run dev

# To run the backend
cd backend
./mvnw spring-boot:run

# To run the AI model
cd ai
uvicorn main:app --reload
```

---
This README provides a comprehensive overview of the Moheng Travel Recommendation System, detailing its purpose, features, technology stack, and instructions for setup and usage.
