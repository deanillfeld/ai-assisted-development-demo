# Coffee Ordering API Development Plan

**Date:** 16 July 2025
**Issue:** https://github.com/deanillfeld/ai-assisted-development-demo/issues/1
**Status:** Approved - Ready for Implementation

## Overview

Implement a Coffee Ordering API endpoint that allows users to create coffee orders with validation, persistence, and proper error handling.

## Requirements Summary

### API Endpoint
- **Method:** POST
- **Path:** `/api/orders/coffee`
- **Status Codes:** 201 (success), 400 (validation error), 500 (server error)

### Request Body Schema
```json
{
  "coffeeType": "Latte",         // Required: Latte, Cappuccino, Espresso, Americano
  "size": "Medium",              // Required: Small, Medium, Large
  "milk": "Full Cream",          // Optional: Full Cream, Skim
  "sugar": 1,                    // Optional: number (no maximum limit)
  "customerNotes": "Extra hot"   // Optional: string
}
```

### Response Schema
```json
{
  "orderId": "COF-20250716-001",
  "coffeeType": "Latte",
  "size": "Medium",
  "milk": "Full Cream",
  "sugar": 1,
  "customerNotes": "Extra hot",
  "status": "Pending",
  "orderTime": "2025-07-16T18:30:00Z"
}
```

### Order ID Format
- Pattern: `COF-YYYYMMDD-XXX`
- Example: `COF-20250716-001`
- Auto-generated with current date and sequential number

## Tech Stack

- **Runtime:** Node.js 22
- **Language:** TypeScript 5
- **Framework:** Express 4
- **Database:** PostgreSQL 17
- **ORM:** Prisma 6
- **Container:** Docker

## Project Structure

```
├── controllers/        # HTTP request handlers
├── services/          # Business logic
├── middleware/        # Express middleware
├── routes/            # Route definitions
├── types/             # TypeScript type definitions
├── tests/             # Test files
├── prisma/            # Database schema and migrations
├── docker-compose.yml # PostgreSQL setup
├── package.json       # Dependencies
├── tsconfig.json      # TypeScript configuration
└── app.ts            # Main application entry point
```

## Implementation Phases

### Phase 1: Project Setup & Infrastructure
1. Initialize Node.js/TypeScript project with required dependencies
2. Configure TypeScript with `tsconfig.json`
3. Create `docker-compose.yml` for PostgreSQL 17
4. Set up Prisma configuration
5. Create basic Express server with middleware

### Phase 2: Database Schema & Models
1. Design Prisma schema for `CoffeeOrder` model
2. Create enums for validation:
   - `CoffeeType`: Latte, Cappuccino, Espresso, Americano
   - `Size`: Small, Medium, Large
   - `MilkType`: Full Cream, Skim
3. Generate and run Prisma migration

### Phase 3: API Implementation
1. Create coffee order service with business logic
2. Implement order ID generation
3. Build POST `/api/orders/coffee` endpoint
4. Add request validation middleware
5. Implement proper error handling

### Phase 4: Testing & Documentation
1. Write unit tests for service layer
2. Write integration tests for API endpoint
3. Create basic API documentation
4. Verify all requirements are met

## Database Schema

```prisma
model CoffeeOrder {
  id            String   @id @default(cuid())
  orderId       String   @unique
  coffeeType    CoffeeType
  size          Size
  milk          MilkType?
  sugar         Int?
  customerNotes String?
  status        String   @default("Pending")
  orderTime     DateTime @default(now())
  createdAt     DateTime @default(now())
  updatedAt     DateTime @updatedAt
}

enum CoffeeType {
  LATTE
  CAPPUCCINO
  ESPRESSO
  AMERICANO
}

enum Size {
  SMALL
  MEDIUM
  LARGE
}

enum MilkType {
  FULL_CREAM
  SKIM
}
```

## Validation Rules

- **coffeeType**: Required, must be one of the valid coffee types
- **size**: Required, must be one of the valid sizes
- **milk**: Optional, must be one of the valid milk types if provided
- **sugar**: Optional, must be a number (no maximum limit)
- **customerNotes**: Optional, string

## Key Dependencies

```json
{
  "dependencies": {
    "express": "^4.x",
    "@prisma/client": "^6.x",
    "cors": "^2.x",
    "helmet": "^7.x"
  },
  "devDependencies": {
    "typescript": "^5.x",
    "@types/node": "^22.x",
    "@types/express": "^4.x",
    "prisma": "^6.x",
    "jest": "^29.x",
    "@types/jest": "^29.x",
    "ts-jest": "^29.x",
    "supertest": "^6.x",
    "@types/supertest": "^6.x",
    "ts-node": "^10.x"
  }
}
```

## Development Notes

- Use Australian/British English spelling
- Implement complete solutions without placeholders
- Write tests for all functionality
- Avoid over-engineering - keep solutions simple and concise
- Only add comments for complex logic that isn't immediately obvious
- Use new branch for implementation (not main)
- Use docker-compose for local development
- Prefer Prisma ORM over raw SQL queries

## Definition of Done

- [ ] All acceptance criteria met
- [ ] Unit and integration tests written and passing
- [ ] API documentation created
- [ ] Database schema implemented and migrated
- [ ] Order ID generation working correctly
- [ ] Validation working for all fields
- [ ] Error handling implemented (400, 500 responses)
- [ ] Success response format matches specification
- [ ] Docker setup complete and working
- [ ] Code follows TypeScript best practices
- [ ] All tests pass

## Next Steps

1. Create new branch for feature implementation
2. Begin Phase 1: Project Setup & Infrastructure
3. Follow implementation phases in order
4. Test thoroughly before marking as complete
