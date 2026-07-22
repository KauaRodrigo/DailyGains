# 🔥 DailyGains

Mobile application for daily workout tracking, featuring streak-based gamification, custom workout plans, and physical progress monitoring.

> ⚠️ Project currently in early development.

---

## 📋 About the project

This app allows gym students/members to log their daily workout sessions, either by using a pre-registered workout plan or by building a custom session on the fly, selecting the exercises performed.

Every day a workout is logged counts toward a **streak** — similar to Duolingo's streak or Snapchat/TikTok's flame — as a gamification mechanism to encourage training consistency.

### Key features

- ✅ User authentication (JWT) with role-based access control (RBAC)
- ✅ Creation and management of custom workout plans
- ✅ Daily workout session logging (using a saved plan or a freeform session)
- ✅ Streak system based on consecutive training days
- ✅ Progress tracking: loads used, body weight, and muscle mass
- ✅ Workout history, highlighting the most trained muscle groups

### Roadmap / Future plans

- 🔜 Automatic random workout generation based on:
  - Selected muscle groups
  - Desired intensity level
  - Total number of exercises

---

## 🚀 Tech stack

### Backend
- [NestJS](https://nestjs.com/)
- [Prisma ORM](https://www.prisma.io/)
- [Swagger](https://swagger.io/) — API documentation
- JWT authentication
- Role-Based Access Control (RBAC)

### Frontend (Mobile)
- [React Native](https://reactnative.dev/) (with Expo)

> The initial focus is the mobile app. Other platforms (web, admin dashboard) may be considered in the future.

---

## 📁 Repository structure

```
/
├── backend/          # NestJS API
│   ├── src/
│   ├── prisma/
│   └── ...
├── mobile/           # React Native (Expo) app
│   ├── app/
│   └── ...
└── README.md
```

> Simple monorepo structure. May evolve into workspaces (e.g. Turborepo/PNPM workspaces) as the project grows.

---

## ⚙️ Getting started

### Prerequisites
- Node.js 18+
- NPM or Yarn
- Database (PostgreSQL recommended)
- Expo Go (for testing on a physical device)

### Backend

```bash
cd backend
npm install
cp .env.example .env   # configure environment variables
npx prisma migrate dev
npm run start:dev
```

Swagger documentation available at: `http://localhost:3000/api` (adjust according to your configuration)

### Mobile

```bash
cd mobile
npm install
npx expo start
```

> Remember to point the API URL to your machine's local network IP (not `localhost`) when testing on a physical device via Expo Go.

---

## 🗄️ Data modeling

The database currently includes the following core entities:

- `users` — app users/students
- `workout_plans` — workout plans/routines created by the user
- `exercises` — available exercises
- `workout_plan_exercises` — join table between workout plans and exercises (with sets, reps, and order)
- `muscle_groups` — muscle groups

*(Full schema available in `schema.prisma`)*

---

## 🔐 Authentication & Authorization

- Authentication via **JWT**
- **Role-based** access control (e.g. `student`, `admin`)

---

## 📄 License

---

MIT.
