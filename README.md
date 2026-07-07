# Project Setup Guide

This document contains the setup commands for both **Mongoose (MongoDB)** and **Prisma (PostgreSQL/MySQL)** projects using **Node.js + TypeScript**.

---

# Mongoose (MongoDB) Project Setup

## 1. Create Project

```bash
mkdir mongoose-project
cd mongoose_project
npm init -y
```

## 2. Install Dependencies

```bash
npm install express mongoose dotenv cors
```

## 3. Install Development Dependencies

```bash
npm install -D typescript ts-node-dev @types/node @types/express @types/cors
```

## 4. Initialize TypeScript

```bash
npx tsc --init
```

## 5. Create Environment File

Create a `.env` file.

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/my_database
```

## 6. Folder Structure

```
src/
│── app.ts
│── server.ts
│── config/
│── modules/
│── routes/
│── middleware/
│── utils/
│── interfaces/
```

## 7. Add Scripts

```json
"scripts": {
  "dev": "ts-node-dev --respawn --transpile-only src/server.ts",
  "build": "tsc",
  "start": "node dist/server.js"
}
```

---

# Prisma (PostgreSQL/MySQL) Project Setup

## 1. Create Project

```bash
mkdir prisma-project
cd prisma_project
npm init -y
```

## 2. Install TypeScript

```bash
npm install -D typescript ts-node @types/node
npx tsc --init
```

## 3. Install Prisma

```bash
npm install prisma --save-dev
npm install @prisma/client
```

## 4. Initialize Prisma

```bash
npx prisma init --datasource-provider postgresql
```

This will create:

```
prisma/
    schema.prisma

.env
```

## 5. Configure Database URL

Example for PostgreSQL:

```env
DATABASE_URL="postgresql://postgres:password@localhost:5432/mydb?schema=public"
```

Example for MySQL:

```env
DATABASE_URL="mysql://root:password@localhost:3306/mydb"
```

## 6. Create First Migration

```bash
npx prisma migrate dev --name init
```

## 7. Generate Prisma Client

```bash
npx prisma generate
```

## 8. Open Prisma Studio

```bash
npx prisma studio
```

## 9. Useful Prisma Commands

Create Migration

```bash
npx prisma migrate dev --name migration_name
```

Reset Database

```bash
npx prisma migrate reset
```

Generate Client

```bash
npx prisma generate
```

View Database

```bash
npx prisma studio
```

Deploy Migrations

```bash
npx prisma migrate deploy
```

---

# Recommended Scripts

```json
"scripts": {
  "dev": "ts-node-dev --respawn --transpile-only src/server.ts",
  "build": "tsc",
  "start": "node dist/server.js"
}
```

---

# Tech Stack

## Mongoose

- Node.js
- Express.js
- TypeScript
- MongoDB
- Mongoose

## Prisma

- Node.js
- Express.js
- TypeScript
- PostgreSQL / MySQL
- Prisma ORM

---

# Quick Comparison

| Feature     | Mongoose              | Prisma             |
| ----------- | --------------------- | ------------------ |
| Database    | MongoDB               | PostgreSQL / MySQL |
| Type        | ODM                   | ORM                |
| Schema      | JavaScript/TypeScript | schema.prisma      |
| Migrations  | Manual                | Built-in           |
| Type Safety | Good                  | Excellent          |
