

# Node.js CI/CD Pipeline Using GitHub Actions and Docker

## 📌 Project Overview

This project demonstrates the implementation of a Continuous Integration and Continuous Deployment (CI/CD) pipeline for a Node.js web application using **GitHub Actions, Docker, and Docker Hub**.

The pipeline automatically runs application tests whenever code is pushed to the `main` branch or a pull request targets `main`. After a successful push to `main`, GitHub Actions builds the Docker image and publishes it to Docker Hub.

## 🎯 Objectives

- Develop a simple Node.js web application using Express.js.
- Implement automated testing using Node.js's built-in test runner and Supertest.
- Create a Docker image to containerize the application.
- Configure GitHub Actions to automate testing, building, and publishing.
- Publish the Docker image to Docker Hub.
- Verify the application using its home and health-check endpoints.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Node.js | JavaScript runtime |
| Express.js | Web application framework |
| Supertest | HTTP endpoint testing |
| Node.js Test Runner | Automated testing |
| Docker | Application containerization |
| GitHub Actions | CI/CD workflow automation |
| Docker Hub | Docker image registry |
| Git and GitHub | Version control and source code hosting |

## 📁 Project Structure

```text
nodejs-demo-app/
├── .github/
│   └── workflows/
│       └── main.yml
├── .dockerignore
├── Dockerfile
├── package.json
├── package-lock.json
├── server.js
├── server.test.js
└── README.md
```

## 🌐 Application Endpoints

The application runs on port `3000`.

### Home Endpoint

**URL:** `http://localhost:3000`

**Response:**

```text
Hello! My GitHub Actions CI/CD pipeline is working!
```

### Health Check Endpoint

**URL:** `http://localhost:3000/health`

**Response:**

```json
{
  "status": "healthy"
}
```

The health endpoint can be used to verify that the application is responding correctly.

## 🧪 Automated Testing

The project uses Node.js's built-in test runner and Supertest to test the application endpoints.

Run the tests locally using:

```bash
npm test
```

The following tests are implemented:

1. Home page returns the expected welcome message.
2. Health endpoint returns a healthy status.

**Test result:** 2 tests passed, 0 failed.

## 🐳 Docker Setup

The application is containerized using the `Dockerfile`.

Build the Docker image:

```bash
docker build -t nodejs-demo-app:local .
```

Run the container:

```bash
docker run -d --name nodejs-demo -p 3000:3000 nodejs-demo-app:local
```

Open the application in your browser:

- Home: http://localhost:3000
- Health: http://localhost:3000/health

To check the running container:

```bash
docker ps
```

To stop the container:

```bash
docker stop nodejs-demo
```

To remove the container after stopping it:

```bash
docker rm nodejs-demo
```

## ⚙️ CI/CD Pipeline

The workflow is defined in `.github/workflows/main.yml`.

### Pipeline Workflow

1. **Code Checkout:** Retrieves the source code from GitHub.
2. **Node.js Setup:** Configures the required Node.js version.
3. **Dependency Installation:** Installs dependencies using `npm ci`.
4. **Automated Testing:** Executes `npm test`.
5. **Docker Buildx Setup:** Prepares the Docker build environment.
6. **Docker Hub Authentication:** Authenticates using a GitHub Actions secret.
7. **Docker Image Build:** Builds the application image.
8. **Image Publishing:** Pushes the image to Docker Hub with the `latest` tag.

### Workflow Triggers

- Pushes to the `main` branch.
- Pull requests targeting the `main` branch.

The Docker image publishing job runs only for pushes to `main` and only after the test job succeeds.

## 📦 Docker Hub Image

**Docker Hub repository:**  
https://hub.docker.com/r/puneet74350/nodejs-demo-app

Pull the published image:

```bash
docker pull puneet74350/nodejs-demo-app:latest
```

Run the published image:

```bash
docker run -d --name nodejs-demo-published -p 3000:3000 puneet74350/nodejs-demo-app:latest
```

If port `3000` is already occupied by another container, stop that container first or map a different host port.

## 🔐 Secrets and Security

The workflow uses a GitHub Actions repository secret named `DOCKERHUB_TOKEN` for Docker Hub authentication.

To configure it, open the GitHub repository and navigate to:

**Settings → Secrets and variables → Actions → New repository secret**

Add the Docker Hub access token as `DOCKERHUB_TOKEN`.

Never commit access tokens, passwords, or other credentials to the repository.

## ✅ Results

The project was tested locally and the GitHub Actions workflow completed successfully.

- Node.js application runs locally.
- Home endpoint returns the expected welcome message.
- Health endpoint returns a healthy status.
- Both automated tests pass.
- Docker image builds successfully.
- GitHub Actions completes the test and build-and-push jobs.
- Docker image is published to Docker Hub.

## 📸 Project Screenshots

Add the screenshots collected during implementation to a folder named `screenshots/` and use the following references.

### 1. Application Home Page

![Application home page](screenshots/home-page.png)

### 2. Health Check Endpoint

![Health check endpoint](screenshots/health-check.png)

### 3. Automated Test Results

![Automated test results](screenshots/test-results.png)

### 4. Successful GitHub Actions Pipeline

![GitHub Actions pipeline success](screenshots/github-actions-success.png)

## 🚀 Future Improvements

- Deploy the Docker container to a cloud server or container platform.
- Add image versioning using Git tags or commit SHA values.
- Add code quality checks and security scanning.
- Configure automated deployment to a staging or production environment.

## 👨‍💻 Author

**Puneet Rathore**

GitHub: https://github.com/Puneetrathore

---

*This project was completed as a practical demonstration of CI/CD automation, automated testing, Docker containerization, and Docker image publishing.*
