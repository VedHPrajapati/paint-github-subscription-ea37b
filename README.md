
# 🎓 LearnX - GCSE Learning Platform

<div align="center">
  <img src="./attached_assets/image_1753213776891.png" alt="LearnX Dashboard" width="800"/>
  
  [![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
  [![React](https://img.shields.io/badge/React-20232A?logo=react&logoColor=61DAFB)](https://reactjs.org/)
  [![Node.js](https://img.shields.io/badge/Node.js-43853D?logo=node.js&logoColor=white)](https://nodejs.org/)
  [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
</div>

## 🚀 Overview

**LearnX** is a cutting-edge GCSE revision platform powered by AI, delivering personalized and adaptive learning experiences for students preparing for their examinations. Built with modern web technologies and integrated with Google Gemini AI, LearnX provides comprehensive study tools, progress tracking, and intelligent tutoring systems.

### ✨ Key Features

- 🧠 **AI-Powered Learning** - Intelligent tutoring system powered by Google Gemini
- 📚 **7 GCSE Subjects** - Science, Math, Computer Science, Economics, English, Geography, Spanish
- 🎯 **Personalized Study Plans** - Adaptive learning paths based on individual progress
- 📊 **Progress Analytics** - Comprehensive tracking and performance insights  
- 🎮 **Gamification** - Achievement system with streaks and rewards
- 💳 **Tiered Subscriptions** - Flexible pricing plans with Stripe integration
- 🎥 **Video Learning** - Curated educational content from trusted sources
- 📱 **Modern UI/UX** - Clean, responsive design with dark mode

## 🏗️ Architecture

### Frontend Stack
- **React 18** with TypeScript for type-safe component development
- **Tailwind CSS** + **shadcn/ui** for modern, responsive styling
- **TanStack Query** for efficient server state management
- **Wouter** for lightweight client-side routing
- **Vite** for fast development and optimized builds

### Backend Stack
- **Node.js** + **Express** for robust server-side architecture
- **TypeScript** with ES modules for type safety
- **Drizzle ORM** with PostgreSQL for database operations
- **bcryptjs** for secure password hashing
- **express-session** with PostgreSQL-backed session storage

### AI Integration
- **Google Gemini API** for AI-powered features
- **Real-time chat interface** for interactive tutoring
- **Intelligent flashcard generation** and analysis
- **Personalized study recommendations**

### Payment Processing
- **Stripe** integration for secure subscription management
- **Webhook handling** for subscription lifecycle events
- **Multi-tier pricing** with feature access control

## 📦 Installation

### Prerequisites
- Node.js 18+ 
- PostgreSQL database
- Google Gemini API key
- Stripe account (for payments)

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/learnx.git
   cd learnx
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   
   Configure your `.env` file:
   ```env
   DATABASE_URL=your_postgresql_connection_string
   GEMINI_API_KEY=your_google_gemini_api_key
   STRIPE_SECRET_KEY=your_stripe_secret_key
   STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
   SESSION_SECRET=your_session_secret
   ```

4. **Set up the database**
   ```bash
   npm run db:push
   ```

5. **Start the development server**
   ```bash
   npm run dev
   ```

6. **Open your browser**
   Navigate to `http://localhost:5000`

## 💰 Subscription Tiers

<div align="center">
  <img src="./attached_assets/image_1753213688024.png" alt="Subscription Tiers" width="800"/>
</div>

### 🆓 Free Tier
- Basic flashcards (limited)
- 5 quiz attempts per day
- Basic progress tracking
- Community support

### 🚀 Starter - £3/month
- Access to basic flashcards
- Limited quiz attempts (5/day)
- Basic progress tracking
- Email support

### 🎯 Scholar - £5/month
- Unlimited flashcards
- Unlimited quiz attempts
- Advanced progress analytics
- Video lessons
- Priority email support

### 👑 Elite Revisionist - £10/month
- Everything in Scholar
- AI-powered study recommendations
- Personal study assistant
- Past paper analysis
- Priority chat support
- Early access to new features

## 🎯 Core Features

### 🧠 AI Tutoring System
- **Multiple Session Modes**: General Chat, Concept Explanation, Practice Quiz, Study Strategy
- **Subject-Specific Guidance**: Tailored tutoring for all 7 GCSE subjects
- **Conversation History**: Contextual awareness across sessions
- **Quick Actions**: Instant study plans, exam tips, and practice questions

### 📚 Smart Flashcards
- **AI-Generated Content**: 10 unique flashcards per subject
- **Automatic Regeneration**: Fresh content each session
- **Audio Learning**: Text-to-speech for auditory learners
- **Difficulty Categorization**: AI-based complexity assessment
- **Performance Tracking**: Progress analytics and insights

### 📊 Progress Analytics
- **Subject Mastery Tracking**: Visual progress indicators
- **Study Session History**: Time tracking and learning patterns
- **Achievement System**: Gamified rewards and milestones
- **Streak Tracking**: Daily study motivation
- **Performance Insights**: AI-powered study recommendations

### 🎥 Video Learning
- **Curated Content**: Educational videos from Khan Academy, Crash Course
- **Interactive Player**: Embedded YouTube with custom controls
- **Subject Organization**: Videos organized by GCSE subject
- **Thumbnail Previews**: Professional video previews with play overlays

## 🗄️ Database Schema

### Core Entities
- **Users**: Authentication, profiles, subscription data, streak tracking
- **Subjects**: GCSE subjects with progress tracking
- **Topics**: Individual learning units within subjects
- **Quizzes**: Assessment tools with scoring and time limits
- **Quiz Questions**: Multiple choice questions with correct answers
- **Quiz Attempts**: Student performance and history tracking
- **Past Papers**: Examination resources by subject and year
- **Achievements**: Gamification system for motivation
- **Study Sessions**: Time tracking for learning activities
- **Subscriptions**: Stripe integration for payment management

## 🔧 API Documentation

### Authentication Endpoints
```
POST /api/auth/login     - User login
POST /api/auth/register  - User registration
GET  /api/auth/me        - Get current user
POST /api/auth/logout    - User logout
```

### AI-Powered Features
```
POST /api/ai/tutor-chat           - AI tutoring chat (Starter+)
POST /api/ai/analyze-flashcard    - Flashcard analysis (Starter+)
POST /api/ai/study-insights       - Study recommendations (Scholar+)
POST /api/ai/generate-flashcards  - AI flashcard generation
POST /api/ai/upload-file          - File analysis (Scholar+)
```

### Subscription Management
```
GET  /api/subscription/status     - Current subscription status
POST /api/subscription/create     - Create Stripe checkout session
POST /api/subscription/webhook    - Stripe webhook handler
```

### Learning Data
```
GET  /api/subjects               - User subjects and progress
GET  /api/quizzes/:subjectId     - Subject quizzes
POST /api/quiz-attempts          - Submit quiz attempt
GET  /api/user/achievements      - User achievements
POST /api/study-sessions         - Track study time
```

## 🎨 UI/UX Design

### Design System
- **Monochromatic Theme**: Pure black and white aesthetic
- **Glass Morphism**: Subtle transparency effects
- **Responsive Design**: Mobile-first approach
- **Accessibility**: WCAG 2.1 compliant
- **Dark Mode Only**: Consistent dark theme throughout

### Component Library
- **shadcn/ui**: Production-ready components
- **Lucide React**: Consistent iconography
- **Framer Motion**: Smooth animations and transitions
- **Tailwind CSS**: Utility-first styling approach

## 🔒 Security Features

- **bcrypt Password Hashing**: Secure password storage
- **Session Management**: PostgreSQL-backed sessions
- **Input Validation**: Zod schema validation
- **SQL Injection Protection**: Parameterized queries with Drizzle ORM
- **Rate Limiting**: API endpoint protection
- **CSRF Protection**: Cross-site request forgery prevention

## 🚀 Deployment

### Development
```bash
npm run dev          # Start development server
npm run db:push      # Push schema changes
npm run db:studio    # Open database studio
```

### Production Build
```bash
npm run build        # Build for production
npm start           # Start production server
```

### Environment Configuration
- **DATABASE_URL**: PostgreSQL connection string
- **GEMINI_API_KEY**: Google Gemini API access
- **STRIPE_SECRET_KEY**: Stripe payment processing
- **SESSION_SECRET**: Session encryption key

## 📈 Performance

- **Optimized Bundle**: Code splitting and tree shaking
- **Image Optimization**: WebP format with fallbacks
- **Caching Strategy**: Browser and CDN caching
- **Database Indexing**: Optimized queries and indexes
- **API Rate Limiting**: Efficient resource utilization

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Workflow
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

### Code Style
- TypeScript strict mode
- ESLint + Prettier configuration
- Conventional commit messages
- Component-based architecture

## 📄 Legal

- [Privacy Policy](./client/src/pages/privacy.tsx)
- [Terms of Service](./client/src/pages/terms.tsx)
- GDPR Compliant data handling
- Educational use focus

## 📞 Support

- **Elite Tier**: Priority chat support
- **Scholar/Starter**: Email support
- **Community**: GitHub issues and discussions
- **Documentation**: Comprehensive guides and API docs

## 👨‍💻 Created By

**Ved Prajapati**  
Certified Cloud Architect (AWS, Aviatrix, Oracle)  
Cybersecurity & DevOps Enthusiast  
Founder of LearnX

---

<div align="center">
  <p>Made with ❤️ for GCSE students worldwide</p>
  <p>© 2025 LearnX. All rights reserved.</p>
</div>
