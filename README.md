# Auth WebApp

A modern, full-stack web application with user authentication built using Next.js 14, TypeScript, and Prisma.

## 🚀 Features

- **Modern Tech Stack**: Next.js 14 with App Router, TypeScript, and Tailwind CSS
- **Secure Authentication**: NextAuth.js with credentials provider
- **Database Integration**: Prisma ORM with SQLite (development) and Vercel Postgres (production)
- **User Management**: Registration, login, and protected routes
- **Type Safety**: Full TypeScript support throughout the application
- **Responsive Design**: Mobile-friendly UI with Tailwind CSS

## 📁 Project Structure

```
auth-webapp/
├── app/                    # Next.js 14 App Router
│   ├── api/               # API routes
│   │   ├── auth/          # NextAuth.js endpoints
│   │   └── register/      # User registration API
│   ├── dashboard/         # Protected dashboard page
│   ├── login/             # Login page
│   ├── register/          # Registration page
│   ├── layout.tsx         # Root layout with SessionProvider
│   └── page.tsx           # Home page
├── lib/                   # Utility libraries
│   ├── auth.ts           # NextAuth.js configuration
│   └── prisma.ts         # Prisma client setup
├── prisma/               # Database schema and migrations
│   └── schema.prisma     # Database schema definition
├── types/                # TypeScript type definitions
│   └── next-auth.d.ts    # NextAuth.js type extensions
└── public/               # Static assets
```

## 🛠️ Setup & Installation

### Prerequisites

- Node.js 18+ 
- npm or yarn
- Git

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd auth-webapp
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Setup

Copy the environment variables template:

```bash
cp .env.example .env.local
```

Update `.env.local` with your values:

```env
# Database
DATABASE_URL="file:./dev.db"

# NextAuth.js
NEXTAUTH_SECRET="your-secret-key-here-generate-a-strong-one"
NEXTAUTH_URL="http://localhost:3000"
```

### 4. Database Setup

```bash
# Generate Prisma client
npx prisma generate

# Run database migrations
npx prisma migrate dev --name init

# (Optional) Open Prisma Studio to view your database
npx prisma studio
```

### 5. Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 🔧 Configuration

### Database Configuration

**Development (SQLite):**
```env
DATABASE_URL="file:./dev.db"
```

**Production (Vercel Postgres):**
```env
DATABASE_URL="postgresql://username:password@host:port/database"
```

### NextAuth.js Configuration

Update the following in your environment:

- `NEXTAUTH_SECRET`: Generate with `openssl rand -base64 32`
- `NEXTAUTH_URL`: Your domain URL

## 🚀 Deployment

### Vercel (Recommended)

1. **Connect Repository to Vercel:**
   - Import your GitHub repository to Vercel
   - Vercel will automatically detect it's a Next.js app

2. **Environment Variables:**
   Set these in your Vercel dashboard:
   ```
   NEXTAUTH_SECRET=your-secret-key-here
   NEXTAUTH_URL=https://your-app.vercel.app
   DATABASE_URL=your-vercel-postgres-url
   ```

3. **Database Migration:**
   ```bash
   npx prisma migrate deploy
   ```

### Other Platforms

The app can be deployed to any platform that supports Next.js:
- Netlify
- Railway
- DigitalOcean App Platform
- AWS Amplify

## 📚 Usage

### User Registration

1. Navigate to `/register`
2. Fill in the registration form
3. Submit to create a new account
4. You'll be automatically signed in

### User Login

1. Navigate to `/login`
2. Enter your credentials
3. You'll be redirected to the dashboard

### Protected Routes

The dashboard at `/dashboard` is protected and requires authentication. Unauthorized users will be redirected to the login page.

## 🔐 Security Features

- **Password Hashing**: Uses bcrypt with 12 salt rounds
- **Session Management**: Secure JWT-based sessions
- **Input Validation**: Zod schema validation for API endpoints
- **CSRF Protection**: Built-in NextAuth.js protection
- **Environment Variables**: Sensitive data stored securely

## 🧪 Testing

Run linting:
```bash
npm run lint
```

Type checking:
```bash
npm run build
```

## 📝 API Endpoints

### Authentication
- `GET/POST /api/auth/[...nextauth]` - NextAuth.js endpoints

### User Management
- `POST /api/register` - Create new user account

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

If you encounter any issues:

1. Check the [GitHub Issues](https://github.com/your-repo/issues) page
2. Create a new issue with detailed information
3. Include error messages and steps to reproduce

## 🎯 Next Steps

To extend this application, consider adding:

- Email verification
- Password reset functionality
- Social authentication (Google, GitHub, etc.)
- User profile management
- Role-based access control
- API rate limiting
- Email notifications
- Two-factor authentication

---

Built with ❤️ using Next.js, TypeScript, and modern web technologies.

deploy fix
