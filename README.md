# Coffee Ordering API

A TypeScript-based REST API for managing coffee orders using Express, Prisma, and PostgreSQL.

## Tech Stack

- **Runtime:** Node.js 22
- **Language:** TypeScript 5
- **Framework:** Express 4
- **Database:** PostgreSQL 17
- **ORM:** Prisma 6
- **Testing:** Jest 29
- **Container:** Docker

## Getting Started

### Prerequisites

- Node.js 22 or higher
- Docker and Docker Compose
- npm

### Installation

1. Clone the repository and install dependencies:

```bash
npm install
```

2. Start the PostgreSQL database:

```bash
docker-compose up -d
```

3. Generate Prisma client:

```bash
npm run db:generate
```

4. Run database migrations:

```bash
npm run db:migrate
```

5. Start the development server:

```bash
npm run dev
```

The API will be available at `http://localhost:3000`.

### Available Scripts

- `npm run dev` - Start development server with hot reload
- `npm run build` - Build TypeScript to JavaScript
- `npm run start` - Start production server
- `npm test` - Run tests
- `npm run test:watch` - Run tests in watch mode
- `npm run db:generate` - Generate Prisma client
- `npm run db:migrate` - Run database migrations
- `npm run db:studio` - Open Prisma Studio

### API Endpoints

- `GET /health` - Health check endpoint

## Project Structure

```
├── src/
│   ├── controllers/     # HTTP request handlers
│   ├── services/        # Business logic
│   ├── middleware/      # Express middleware
│   ├── routes/          # Route definitions
│   ├── types/           # TypeScript type definitions
│   └── app.ts           # Main application entry point
├── tests/               # Test files
├── prisma/              # Database schema and migrations
├── docker-compose.yml   # PostgreSQL setup
└── dist/                # Built JavaScript files
```

## Development Status

- [x] Phase 1: Project Setup & Infrastructure
  - [x] Node.js/TypeScript project setup
  - [x] Express server configuration
  - [x] PostgreSQL Docker setup
  - [x] Prisma configuration
  - [x] Basic middleware setup
  - [x] Health check endpoint
- [ ] Phase 2: Database Schema & Models
- [ ] Phase 3: API Implementation
- [ ] Phase 4: Testing & Documentation

## License

ISC
