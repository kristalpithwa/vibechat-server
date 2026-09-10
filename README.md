# 💬 VibeChat Server

The backend API and real-time messaging engine for **VibeChat**, built with Node.js, Express, Socket.io, TypeScript, and Prisma ORM with PostgreSQL.

---

## 🚀 Features

- **Real-Time Communication**: Instant messaging powered by Socket.io.
- **Robust Database ORM**: Powered by Prisma 7 and PostgreSQL.
- **Relational Data Model**:
  - **Users**: Authentication, profiles, online status, and avatars.
  - **Conversations**: Direct 1-on-1 chats and group channels.
  - **Memberships**: Role-based access control (`ADMIN`, `MEMBER`).
  - **Messages**: Support for text, media (image/video/audio), attachments, and reply threading.
- **Modern TypeScript Stack**: Pure ECMAScript Modules (ESM) with `tsx` fast dev runner.

---

## 🛠️ Tech Stack

- **Runtime & Language**: Node.js (v20+ recommended) & TypeScript
- **Web Framework**: Express 5
- **WebSockets**: Socket.io
- **ORM**: Prisma 7
- **Database**: PostgreSQL (Prisma Postgres / Neon / Supabase / Local)
- **Security**: JWT (`jsonwebtoken`) & `bcrypt`

---

## 📁 Project Structure

```
vibechat-server/
├── prisma/
│   ├── migrations/        # SQL database migrations
│   └── schema.prisma      # Prisma schema (models, relations, enums)
├── src/
│   ├── generated/prisma/  # Generated Prisma client (git-ignored)
│   └── server.ts          # Express & Socket.io server entrypoint
├── .env.example           # Template for environment variables
├── package.json           # Dependencies and scripts
├── prisma7.config.ts      # Prisma 7 CLI configuration
└── tsconfig.json          # TypeScript compiler options
```

---

## 🏁 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/vibechat-server.git
cd vibechat-server
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Copy the example environment file:

```bash
cp .env.example .env
```

> **Note**: Never commit `.env` to Git. It is excluded in `.gitignore`.

---

## 🗄️ Database Setup & Migrations

### Apply Migrations

Run database migrations to create or update tables:

```bash
npx prisma migrate dev
```

### Generate Prisma Client

Generate TypeScript types and Prisma Client:

```bash
npx prisma generate
```

### Open Prisma Studio

To inspect and manage database records visually in your browser:

```bash
npx prisma studio
```

---

## 💻 Running the Server

### Development Mode (with hot-reload)

```bash
npm run dev
```

The server will start on `http://localhost:5000`.

### Health Check

Verify the server is running by opening:

```bash
curl http://localhost:5000/health
```

Expected response:

```json
{
  "success": true,
  "message": "Chat backend is running 🚀"
}
```

---

## 📜 Available Scripts

| Script                   | Command                   | Description                        |
| :----------------------- | :------------------------ | :--------------------------------- |
| `npm run dev`            | `tsx watch src/server.ts` | Starts the server with live reload |
| `npx prisma migrate dev` | `prisma migrate dev`      | Applies migrations in development  |
| `npx prisma studio`      | `prisma studio`           | Launches Prisma database GUI       |
| `npx prisma generate`    | `prisma generate`         | Regenerates Prisma Client          |
| `npx tsc --noEmit`       | `tsc --noEmit`            | Performs TypeScript type checking  |

---

## 🔒 Security & Best Practices

- Ensure `.env` is never checked into Git.
- Passwords should always be hashed using `bcrypt` before database storage.
- Validate all incoming WebSocket payloads and HTTP requests.

---

## 📄 License

This project is licensed under the [ISC License](LICENSE).
