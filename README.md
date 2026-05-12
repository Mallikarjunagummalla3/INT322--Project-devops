# INT332 – DevOps Pipeline Implementation
**Student:** Gummalla Mallikarjuna | **Reg. No.:** 12311643 | **Section:** 2OM46

---

## Project Overview
Microservices containerization with Docker, build automation with Maven, and CI/CD using GitHub Actions.

## Project Structure
```
INT332-project/
├── src/
│   ├── main/java/com/int332/app/App.java   # Spring Boot app
│   └── test/java/com/int332/app/AppTest.java
├── .github/
│   └── workflows/ci.yml                    # GitHub Actions pipeline
├── Dockerfile                              # Multi-stage Docker build
├── docker-compose.yml
├── pom.xml                                 # Maven build config
└── README.md
```

## How to Run Locally

### Using Docker Compose
```bash
docker-compose up --build
```
Open → http://localhost:8080

### Using Maven directly
```bash
mvn clean package
java -jar target/int332-app-1.0.0.jar
```

## CI/CD Pipeline (GitHub Actions)
Push to `main` triggers 3 jobs automatically:
1. **Build & Test** – Maven compiles and runs unit tests
2. **Containerize & Push** – Docker image built and pushed to Docker Hub
3. **Deploy** – Container pulled and started from published image

## GitHub Secrets Required
Go to → Settings → Secrets → Actions → New repository secret:
- `DOCKER_USERNAME` – your Docker Hub username
- `DOCKER_PASSWORD` – your Docker Hub password/token
