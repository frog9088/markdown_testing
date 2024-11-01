# Moheng
- A comprehensive travel planning application that integrates various services for trip recommendations, live information, and user management.

## 📝 Description
Moheng is designed to provide users with personalized travel recommendations based on their preferences and interactions. The application leverages AI to suggest trips and activities, while also allowing users to manage their travel itineraries and live information.

### Key features
- Personalized trip recommendations based on user preferences.
- Integration with live information services for real-time updates.
- User management including sign-up, profile updates, and trip planning.
- Support for multiple social login providers.

### Core technology stack used
- **Backend**: Java, Spring Boot
- **Frontend**: React, Vite
- **Database**: MySQL
- **Containerization**: Docker
- **Monitoring**: Prometheus, Grafana

## 🖼 Preview

<img src='https://oaidalleapiprodscus.blob.core.windows.net/private/org-kv8YgzhLnngsTNFN8trPDil2/user-hS61ZsZAYtg5kQFwwsXdahCO/img-tQpbg1PV1aRCsgHNGKwIUzKX.png?st=2024-11-01T00%3A11%3A57Z&se=2024-11-01T02%3A11%3A57Z&sp=r&sv=2024-08-04&sr=b&rscd=inline&rsct=image/png&skoid=d505667d-d6c1-4a0a-bac7-5c84a87759f8&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2024-11-01T01%3A11%3A57Z&ske=2024-11-02T01%3A11%3A57Z&sks=b&skv=2024-08-04&sig=%2BKZtdPj4AD55UHkSvikInbF0b9WYf5fGV3N1mm3UfO8%3D' width='400' height='400'/>

## 📊 Analysis
- The application effectively utilizes AI algorithms to enhance user experience by providing tailored recommendations.
- Performance metrics indicate a responsive UI with minimal latency during data retrieval.
- Key insights reveal user engagement increases with personalized content delivery.

## 📁 Project Structure
[moheng root] ├── 📁 backend │ ├── 📁 application │ ├── 📁 domain │ ├── 📁 infrastructure │ └── ... ├── 📁 frontend │ ├── 📁 src │ ├── 📁 public │ └── ... ├── 📁 database │ └── compose.yaml ├── 📁 monitoring │ ├── 📁 prometheus │ └── 📁 grafana └── ...


## 🚀 Getting Started

### Prerequisites
- Java 11 or higher
- Node.js and npm
- Docker and Docker Compose
- MySQL database

### Installation
```bash
# Clone the repository
git clone https://github.com/kakaotech-25/moheng.git

# Navigate to the backend directory
cd moheng/backend

# Install required packages
./mvnw install

# Navigate to the frontend directory
cd ../frontend

# Install required packages
npm install

# Configure environment
# Create a .env file in the backend and frontend directories with necessary configurations
Usage
# Start the backend server
cd backend
./mvnw spring-boot:run

# Start the frontend server
cd ../frontend
npm run dev

# Start the database and monitoring services using Docker Compose
cd ../database
docker-compose up -d
``` This README.md provides a structured overview of the Moheng project, including its purpose, features, technology stack, project structure, and instructions for getting started. Adjust the preview image link and any other specific details as necessary.
