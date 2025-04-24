# DotNetCoreInDocker

A simple sample project demonstrating how to run an ASP.NET Core Web API application inside a Docker container.

## 📝 Overview

This project is a minimalistic RESTful API built with **ASP.NET Core 3.1**, intended to demonstrate how to containerize a .NET Core application using **Docker**. The application exposes a sample weather forecast API endpoint and is fully dockerized using a multi-stage Docker build process.

## 📁 Project Structure
```bash
/DotNetCoreInDocker
│
├── Controllers/
│   └── WeatherForecastController.cs
│
├── Models/
│   └── WeatherForecast.cs
│
├── Dockerfile
├── docker-compose.yml
├── DotNetCoreInDocker.csproj
├── Program.cs
└── Startup.cs

## 🚀 How to Run

### Prerequisites

- [.NET Core SDK 3.1](https://dotnet.microsoft.com/en-us/download/dotnet/3.1)
- [Docker](https://www.docker.com/)
- (Optional) [Visual Studio Code](https://code.visualstudio.com/) with Docker extension

### 🐳 Run with Docker

Build and run the container:


docker build -t dotnetcoreindocker .
docker run -d -p 5000:5000 dotnetcoreindocker
🔁 Or with Docker Compose

docker-compose up --build
Then open your browser and navigate to:


http://localhost:5000/weatherforecast
You should see a list of random weather forecast data in JSON format.

🔧 Configuration
Application runs on port 5000 (configured in Dockerfile and docker-compose.yml)

Environment variable ASPNETCORE_ENVIRONMENT=Development is set

ASPNETCORE_URLS is set to http://+:5000 for compatibility with Docker networking

📦 Dockerfile Highlights
Uses multi-stage builds to separate build and runtime environments

Based on official .NET Core 3.1 SDK and ASP.NET Core Runtime images

Publishes a self-contained app in /app/publish

📜 Sample Output
[
  {
    "date": "2025-04-24T00:00:00",
    "temperatureC": 25,
    "temperatureF": 77,
    "summary": "Warm"
  },
  ...
]

🔗 Resources

ASP.NET Core Docker Docs
Docker Compose Docs
Visual Studio Code - Containers


