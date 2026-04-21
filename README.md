# Web Application with CI/CD Pipeline

A modern Node.js web application with a complete CI/CD pipeline using GitHub Actions.

## Project Structure

```
.
├── app.js                    # Express application
├── package.json              # Dependencies and scripts
├── jest.config.js            # Jest testing configuration
├── .eslintrc.json            # ESLint configuration
├── .github/
│   └── workflows/
│       └── ci-cd.yml        # GitHub Actions CI/CD workflow
├── Dockerfile                # Docker container configuration
├── docker-compose.yml        # Docker Compose for local development
├── test/
│   └── app.test.js          # Unit tests
└── README.md                 # This file
```

## Features

- ✅ **Express.js Server** - Lightweight web framework
- ✅ **Automated Testing** - Jest unit tests with coverage
- ✅ **Code Quality** - ESLint for code consistency
- ✅ **CI/CD Pipeline** - GitHub Actions for automation
- ✅ **Docker Support** - Containerized application
- ✅ **Security Checks** - Dependency vulnerability scanning
- ✅ **Health Checks** - Application monitoring endpoints

## Installation

### Prerequisites
- Node.js 16.x or higher
- npm or yarn
- Docker (optional)

### Setup

```bash
# Install dependencies
npm install

# Install development dependencies
npm install --save-dev
```

## Running the Application

### Local Development

```bash
# Start development server with auto-reload
npm run dev
```

### Production

```bash
# Start production server
npm start
```

The application will be available at `http://localhost:3000`

## Running Tests

```bash
# Run tests with coverage
npm test

# Run linter
npm run lint

# Fix linting issues automatically
npm run lint:fix
```

## Docker

### Build Docker Image

```bash
docker build -t web-app:latest .
```

### Run with Docker

```bash
docker run -p 3000:3000 web-app:latest
```

### Run with Docker Compose

```bash
docker-compose up -d
```

## API Endpoints

- `GET /` - Welcome message
- `GET /health` - Health check endpoint
- `GET /api/data` - Sample data endpoint

## CI/CD Pipeline

The GitHub Actions workflow automatically:

1. **Tests** - Runs unit tests across multiple Node.js versions (16.x, 18.x)
2. **Linting** - Checks code quality with ESLint
3. **Build** - Creates production build artifacts
4. **Security** - Audits dependencies for vulnerabilities
5. **Deploy** - Deploys to production (when pushing to main branch)

### Pipeline Triggers

- Push to `main` or `develop` branches
- Pull requests to `main` or `develop` branches

### Pipeline Jobs

#### Test Job
- Runs on Ubuntu latest
- Tests on Node.js 16.x and 18.x
- Uploads coverage to Codecov

#### Build Job
- Creates build artifacts
- Stores artifacts for 30 days

#### Security Job
- Performs npm audit
- Checks for vulnerabilities

#### Deploy Job
- Runs only on `main` branch push
- After test and build jobs pass
- Placeholder for production deployment

## Environment Variables

Create a `.env` file for local development:

```
PORT=3000
NODE_ENV=development
```

## Deployment

### Vercel

```bash
npm install -g vercel
vercel
```

### Heroku

```bash
heroku login
git push heroku main
```

### AWS Lambda

Configure AWS credentials and deploy using Serverless Framework

### DigitalOcean App Platform

Connect your GitHub repository and configure deployment

## Testing Coverage

Run tests with coverage:

```bash
npm test
```

Coverage thresholds:
- Branches: 50%
- Functions: 50%
- Lines: 50%
- Statements: 50%

## Troubleshooting

### Port already in use
```bash
# Change PORT environment variable
PORT=3001 npm start
```

### Dependencies not installing
```bash
# Clear npm cache
npm cache clean --force
npm install
```

### Docker build fails
```bash
# Use no-cache flag
docker build --no-cache -t web-app:latest .
```

## Contributing

1. Create a feature branch
2. Commit your changes
3. Push to your branch
4. Create a Pull Request

The CI/CD pipeline will automatically test and validate your changes!

## License

ISC

## Support

For issues or questions, please open an issue on GitHub.
