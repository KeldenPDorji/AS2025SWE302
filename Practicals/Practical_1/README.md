## Interactive Quiz Application

This repository contains a modern interactive quiz application built with React and TypeScript.

**🔗 Source Code:** [View on GitHub](https://github.com/KeldenPDorji/reactquiz)

**📋 [View Testing Documentation](TESTING.md)**

### Project Overview

This project is a real-time, interactive quiz application designed to test programming knowledge. The application features a modern, responsive interface with comprehensive testing and demonstrates advanced software design principles and full-stack development skills.

### Key Features

- **Interactive Quiz Flow**: 10 programming questions with immediate feedback
- **Timer System**: 30-second countdown with automatic termination
- **Responsive Design**: Mobile-first approach, adapts to all screen sizes
- **Real-time Scoring**: Live score tracking with percentage calculation
- **Modern UI/UX**: Clean design with smooth animations and visual feedback
- **Comprehensive Testing**: 177 automated tests covering all functionality

---

## Setup Instructions

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or newer recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)

### Installation

1. **Install dependencies:**

```bash
npm install
```

2. **Start the development server:**

```bash
npm run dev
```

The app will be available at [http://localhost:5173](http://localhost:5173) by default.

3. **Build for production:**

```bash
npm run build
```

4. **Preview the production build:**

```bash
npm run preview
```

5. **Lint the codebase:**

```bash
npm run lint
```

## Testing

This project includes comprehensive end-to-end tests using Playwright with **177 automated tests** covering all functionality.

**📋 [View Complete Testing Documentation](TESTING.md)**

### Quick Test Commands

1. **Start the development server:**
```bash
npm run dev
```

2. **Run all tests (in a separate terminal):**
```bash
npm run test
```

3. **Run tests with UI mode:**
```bash
npm run test:ui
```

4. **View test reports:**
```bash
npm run test:report
```

### Docker Setup (Alternative)

If you prefer to use Docker, you can run the application in a container:

1. **Build the Docker image:**

```bash
docker build -t quiz-app .
```

2. **Run the container:**

```bash
docker run -p 3000:3000 quiz-app
```

The app will be available at [http://localhost:3000](http://localhost:3000).

### Slack Integration

This project is integrated with Slack for continuous integration notifications:

- **GitHub App Integration**: GitHub app has been added to Slack workspace
- **Repository Subscription**: This repository is subscribed for notifications
- **Push Notifications**: Successful git pushes trigger "success" notifications in Slack
- **Real-time Updates**: Team members receive instant updates on code changes and deployments

The integration ensures seamless collaboration and keeps the team informed about project progress.

---

## Architecture & Technical Details

### Tech Stack

- **Frontend**: React 19, TypeScript
- **Styling**: Tailwind CSS 4.0
- **Icons**: Lucide React
- **Build Tool**: Vite 6.1
- **Testing**: Playwright
- **Linting**: ESLint 9.19

### Key Features Implemented

1. **Interactive Quiz Flow**
   - 10 React/programming questions
   - Multiple choice answers (4 options each)
   - Immediate feedback on selection
   - Automatic question progression

2. **Timer System**
   - 30-second countdown per quiz session
   - Visual timer display
   - Automatic quiz termination when time expires

3. **Scoring System**
   - Real-time score tracking
   - Final score calculation and display
   - Percentage accuracy calculation

4. **Responsive Design**
   - Mobile-first approach
   - Adapts to different screen sizes
   - Touch-friendly interface

5. **Modern UI/UX**
   - Clean, modern design with Tailwind CSS
   - Smooth transitions and animations
   - Intuitive user interactions
   - Visual feedback for all actions

---

**📋 [View Complete Testing Documentation](TESTING.md)**
