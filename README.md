# NestJS Basics

NestJS is a progressive Node.js framework for building efficient, reliable, and scalable server-side applications. It uses TypeScript by default and combines elements of OOP (Object Oriented Programming), FP (Functional Programming), and FRP (Functional Reactive Programming).

## Installation

To install NestJS, you need to have Node.js and npm installed. You can create a new NestJS project using the Nest CLI.

1. Install the Nest CLI globally:
    ```bash
    npm install -g @nestjs/cli
    ```

2. Create a new project:
    ```bash
    nest new project-name
    ```

3. Navigate to the project directory:
    ```bash
    cd project-name
    ```

4. Start the development server:
    ```bash
    npm run start
    ```

## Basic Concepts

### Modules

Modules are the basic building blocks of a NestJS application. They are used to organize the application into cohesive blocks of functionality.

```typescript
import { Module } from '@nestjs/common';
import { CatsController } from './cats.controller';
import { CatsService } from './cats.service';

@Module({
  controllers: [CatsController],
  providers: [CatsService],
})
export class CatsModule {}
```

### Controllers

Controllers handle incoming requests and return responses to the client. They are defined using the `@Controller` decorator.

```typescript
import { Controller, Get } from '@nestjs/common';
import { CatsService } from './cats.service';

@Controller('cats')
export class CatsController {
  constructor(private readonly catsService: CatsService) {}

  @Get()
  findAll(): string {
    return this.catsService.findAll();
  }
}
```

### Providers

Providers are used to encapsulate business logic and can be injected into controllers or other providers using dependency injection.

```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
export class CatsService {
  findAll(): string {
    return 'This action returns all cats';
  }
}
```

## Summary

NestJS is a powerful framework for building server-side applications. It provides a modular architecture, dependency injection, and a robust CLI to streamline development. By following the basic concepts of modules, controllers, and providers, you can create scalable and maintainable applications.

For more detailed information, refer to the [official NestJS documentation](https://docs.nestjs.com/).
