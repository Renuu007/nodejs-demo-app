# Node.js Demo App with CI/CD Pipeline

A simple Node.js web application with automated CI/CD pipeline using GitHub Actions and DockerHub.

## 🚀 Overview

This project demonstrates a complete CI/CD (Continuous Integration/Continuous Deployment) pipeline for a Node.js application. The pipeline automatically builds, tests, and deploys the application using GitHub Actions and DockerHub.

## 📋 Features

- **Simple HTTP Server**: Basic Node.js web server that responds with "Hello, World!"
- **Docker Containerization**: Application packaged as a Docker container
- **Automated CI/CD Pipeline**: GitHub Actions workflow for automated build and deployment
- **DockerHub Integration**: Automatic pushing of Docker images to DockerHub registry

## 🏗️ Architecture

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   GitHub Repo   │───▶│  GitHub Actions  │───▶│   DockerHub     │
│                 │    │   CI/CD Pipeline │    │   Registry      │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

## 📁 Project Structure

```
nodejs-demo-app/
├── .github/
│   └── workflows/
│       └── main.yml          # GitHub Actions CI/CD workflow
├── index.js                  # Main Node.js application
├── package.json              # Node.js dependencies and scripts
├── Dockerfile               # Docker container configuration
├── task 1.txt              # Project requirements
└── README.md               # This file
```

## 🛠️ Technologies Used

- **Node.js**: JavaScript runtime environment
- **Docker**: Containerization platform
- **GitHub Actions**: CI/CD automation
- **DockerHub**: Container registry

## 🚀 Getting Started

### Prerequisites

- Node.js (v18 or higher)
- Docker (optional, for local testing)
- GitHub account
- DockerHub account

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/Renuu007/nodejs-demo-app.git
   cd nodejs-demo-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Run the application locally**
   ```bash
   npm start
   ```

4. **Access the application**
   Open your browser and navigate to `http://localhost:3000`

### Docker (Optional)

1. **Build the Docker image**
   ```bash
   docker build -t nodejs-demo-app .
   ```

2. **Run the Docker container**
   ```bash
   docker run -p 3000:3000 nodejs-demo-app
   ```

## 🔄 CI/CD Pipeline

### Workflow Overview

The CI/CD pipeline is defined in `.github/workflows/main.yml` and includes the following steps:

1. **Code Checkout**: Clones the repository
2. **Node.js Setup**: Sets up Node.js environment
3. **Dependency Installation**: Installs npm dependencies
4. **Testing**: Runs application tests
5. **DockerHub Login**: Authenticates with DockerHub
6. **Docker Build**: Builds the Docker image
7. **Docker Push**: Pushes the image to DockerHub

### Trigger Conditions

The pipeline automatically runs when:
- Code is pushed to the `main` branch
- Pull requests are created or updated

### Required Secrets

The following GitHub secrets must be configured in your repository:

- `DOCKERHUB_USERNAME`: Your DockerHub username
- `DOCKERHUB_TOKEN`: Your DockerHub access token

### Setting Up Secrets

1. Go to your GitHub repository
2. Navigate to **Settings** → **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. Add the required secrets as mentioned above

## 📦 Docker Image

The application is containerized using Docker with the following configuration:

- **Base Image**: `node:18` (Node.js LTS)
- **Working Directory**: `/app`
- **Exposed Port**: `3000`
- **Start Command**: `npm start`

## 🔧 Configuration

### Environment Variables

- `PORT`: Server port (defaults to 3000)

### Package Scripts

- `npm start`: Starts the application
- `npm test`: Runs tests (currently placeholder)

## 📊 Monitoring

### GitHub Actions

- Monitor pipeline runs in the **Actions** tab of your GitHub repository
- View detailed logs for each step
- Re-run failed jobs if needed

### DockerHub

- Track image builds and pushes in your DockerHub repository
- Monitor image tags and versions

## 🚀 Deployment

### Manual Deployment

1. Pull the latest image from DockerHub:
   ```bash
   docker pull renuu007/nodejs-demo-app:latest
   ```

2. Run the container:
   ```bash
   docker run -p 3000:3000 renuu007/nodejs-demo-app:latest
   ```

### Cloud Deployment

The Docker image can be deployed to various cloud platforms:

- **Azure Container Instances**
- **AWS ECS/Fargate**
- **Google Cloud Run**
- **DigitalOcean App Platform**
- **Heroku Container Registry**

## 🧪 Testing

Currently, the project includes a placeholder test script. To add real tests:

1. Install a testing framework (e.g., Jest):
   ```bash
   npm install --save-dev jest
   ```

2. Create test files in a `tests/` directory
3. Update the test script in `package.json`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License.

## 👨‍💻 Author

**Renuu007**

- GitHub: [@Renuu007](https://github.com/Renuu007)
- Repository: [nodejs-demo-app](https://github.com/Renuu007/nodejs-demo-app)

## 🙏 Acknowledgments

- GitHub Actions for CI/CD automation
- Docker for containerization
- Node.js community for the excellent runtime environment

## 📈 Future Enhancements

- [ ] Add comprehensive test suite
- [ ] Implement health check endpoints
- [ ] Add environment-specific configurations
- [ ] Implement blue-green deployment strategy
- [ ] Add monitoring and logging
- [ ] Implement security scanning in CI/CD pipeline

---

**⭐ Star this repository if you found it helpful!** 