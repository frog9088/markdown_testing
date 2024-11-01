# Moheng

## 🖼 Preview
![Preview Image](./generated_image.png)
 
##  Table of Contents

- [ Overview](#-overview)
- [ Features](#-features)
- [ Project Structure](#-project-structure)
  - [ Project Index](#-project-index)
- [ Getting Started](#-getting-started)
  - [ Prerequisites](#-prerequisites)
  - [ Installation](#-installation)
  - [ Usage](#-usage)
  - [ Testing](#-testing)
- [ Project Roadmap](#-project-roadmap)
- [ Contributing](#-contributing)
- [ License](#-license)
- [ Acknowledgments](#-acknowledgments)


## 📝 Overview
Moheng is a comprehensive travel planning application that allows users to discover and plan trips based on their preferences and interests. The application integrates various features such as keyword-based recommendations, live information about destinations, and user-specific trip schedules.

### Main Purpose
- To provide a platform for users to plan their travel itineraries effectively.
- To solve the problem of finding relevant travel information and recommendations based on user preferences.
- Target users include travelers, travel enthusiasts, and anyone looking to explore new destinations.

### Key Features
- **Personalized Recommendations**: Users receive trip suggestions based on their interests and previous interactions.
- **Live Information**: Access to real-time data about destinations, including live events and activities.
- **Trip Scheduling**: Users can create and manage their trip schedules, including adding and removing trips as needed.

### Core Technology Stack 
- Frontend: React, Vite
- Backend: Spring Boot, Java
- Database: MySQL
- Other Tools: Docker, Prometheus, Grafana

## 📊 Analysis
The application leverages data analysis to provide personalized recommendations and insights into user preferences. Performance metrics are tracked to ensure a smooth user experience and to optimize the recommendation algorithms.

## 📁 Project Structure
```
moheng
├── 📁 backend
│   ├── 📁 application
│   ├── 📁 domain
│   ├── 📁 dto
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
└── docker-compose.yaml
```

## 🚀 Getting Started
To get started with the Moheng project, follow the instructions below.

### Prerequisites
- Docker and Docker Compose installed on your machine.
- Java 11 or higher for the backend.
- Node.js and npm installed for the frontend.

### Installation
```bash
# Clone the repository
git clone https://github.com/kakaotech-25/moheng.git

# Navigate to the project directory
cd moheng

# Start the application using Docker Compose
docker-compose up -d
```

### Usage
- Access the frontend application at `http://localhost:3000`.
- The backend API can be accessed at `http://localhost:8080/api`.

### Testing
- Unit tests can be run using the following command in the backend directory:
```bash
# Navigate to the backend directory
cd backend

# Run tests
./mvnw test
```

## Project Roadmap
- Implement additional features for user preferences.
- Enhance the recommendation algorithms for better accuracy.
- Improve the UI/UX of the frontend application.

## Contributing
Contributions are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Thanks to all contributors and the open-source community for their support and resources.
- Special thanks to the developers of the libraries and frameworks used in this project.
