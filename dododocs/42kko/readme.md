# Cloud Discord Bot

## 🖼 Preview

<img src='./generated_image.png' width='400' height='400'/>

##  Table of Contents

- [ Overview](#-overview)
- [ Analysis](#-analysis)
- [ Project Structure](#-project-structure)
- [ Getting Started](#-getting-started)
  - [ Prerequisites](#prerequisites)
  - [ Installation](#installation)
  - [ Usage](#usage)

## 📝 Overview
The Cloud Discord Bot is a C++ application designed to interact with Discord's API, providing various functionalities such as automated responses, notifications, and integrations with other services.

### Main Purpose
- The primary goal of the project is to create a versatile Discord bot that can automate tasks and enhance user interaction within Discord servers.
- It solves the problem of manual task management and provides a seamless way to integrate external services with Discord.
- The target audience includes Discord server administrators and users looking to enhance their server's functionality.

### Key Features
- Automated responses to user commands.
- Integration with external services like Jenkins for notifications.
- Configuration management for easy setup and customization.

### Core Technology Stack
- Frontend: N/A
- Backend: C++
- Database: N/A
- Other Tools: CMake, Makefile

## 📊 Analysis
The bot utilizes various performance metrics to ensure efficient operation. Key insights include:
- The bot can handle multiple commands simultaneously without significant latency.
- Integration with external services is seamless, providing real-time notifications.

## 📁 Project Structure
```
Cloud-discord_bot
├── 📁 srcs
│   ├── bot.cpp
│   ├── jenkins_utils.cpp
│   ├── dpp_utils.cpp
│   ├── config.cpp
│   └── main.cpp
├── 📁 include
│   ├── bot.h
│   ├── jenkins_utils.h
│   ├── dpp_utils.h
│   └── config.h
├── 📁 libs
│   ├── 📁 json
│   │   ├── CMakeLists.txt
│   │   ├── include
│   │   ├── single_include
│   │   └── ...
│   └── ...
├── 📁 build
├── 📁 bin
└── Makefile
```

## 🚀 Getting Started

### Prerequisites
- C++17 compatible compiler (e.g., clang++)
- CMake (version 3.1 or higher)
- Required libraries: dpp, curl
- Python 3 (for documentation generation)

### Installation
```bash
# Clone the repository
git clone https://github.com/42kko/42.git

# Navigate to the project directory
cd 42/Cloud-discord_bot

# Install required packages
make

# Configure environment (if necessary)
# This step may vary based on your setup and dependencies
```

### Usage
```bash
# How to run the bot
./bin/mybot
```
