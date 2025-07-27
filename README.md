# SahayakAI: AI-Powered Teaching & Learning Assistant

SahayakAI is a modern web application built to serve as an intelligent assistant for both teachers and students. It leverages Generative AI to provide tools for content creation, administrative assistance, and interactive learning, all within a unified platform.

## Core Features

### For Teachers:
-   **Differentiated Worksheet Generation**: Automatically create worksheets tailored for multiple grade levels from a single topic prompt.
-   **Localized Content Generation**: Generate culturally relevant stories and poems in various Indian languages, complete with text-to-speech audio.
-   **AI Lesson Plan Generation**: Instantly create structured weekly lesson plans for any topic, subject, and grade level.
-   **Blackboard Art Generation**: Create simple, clean line drawings from a text description for use in the classroom.
-   **Attendance Tracking**: Mark daily attendance and automatically notify parents of absent students via a simulated SMS service.
-   **My School Feed**: View questions and content shared by students in a central feed.

### For Students:
-   **Instant Q&A**: Get simple, analogy-based answers to complex questions.
-   **Problem Solver**: Upload an image of a problem (e.g., math, physics) and receive a step-by-step solution.
-   **Gamified Quizzes**: Test knowledge on any topic with fun, interactive quizzes that award points, badges, and streaks.
-   **My School Feed**: Participate in a learning community by viewing questions from other students.
-   **Leaderboard**: See how you rank against classmates based on quiz scores.

## Tech Stack

-   **Framework**: [Next.js](https://nextjs.org/) (App Router)
-   **UI**: [React](https://react.dev/), [TypeScript](https://www.typescriptlang.org/)
-   **Styling**: [Tailwind CSS](https://tailwindcss.com/)
-   **UI Components**: [ShadCN UI](https://ui.shadcn.com/)
-   **Generative AI**: [Genkit](https://firebase.google.com/docs/genkit) with Google Gemini models.
-   **Backend & Database**: [Firebase](https://firebase.google.com/) (Authentication, Firestore, Storage)

## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

-   Node.js (v18 or later)
-   npm or yarn

### Installation

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd <repository-directory>
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Set up environment variables:**
    Create a file named `.env` in the root of your project and add your Firebase project configuration keys. You can get these from the Firebase console.

    ```env
    NEXT_PUBLIC_FIREBASE_API_KEY=...
    NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=...
    NEXT_PUBLIC_FIREBASE_PROJECT_ID=...
    NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=...
    NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=...
    NEXT_PUBLIC_FIREBASE_APP_ID=...
    ```

    You will also need a Gemini API key for the Genkit flows to work:
    ```env
    GEMINI_API_KEY=...
    ```

4.  **Run the Genkit developer UI (optional):**
    To inspect your Genkit flows, you can run the Genkit developer UI in a separate terminal:
    ```bash
    npm run genkit:watch
    ```
    This will start the UI, typically at `http://localhost:4000`.

5.  **Run the development server:**
    ```bash
    npm run dev
    ```
    Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Project Structure

-   `src/app/`: Contains all the pages and layouts for the Next.js App Router.
-   `src/ai/`: Houses all the Genkit-related code.
    -   `src/ai/flows/`: Contains all the individual Genkit flows that power the AI features.
    -   `src/ai/genkit.ts`: Global Genkit configuration.
-   `src/components/`: Shared React components used throughout the application.
    -   `src/components/ui/`: Auto-generated ShadCN UI components.
-   `src/lib/`: Core libraries, constants, and utility functions.
-   `src/contexts/`: React context providers, such as for authentication.
-   `src/hooks/`: Custom React hooks.

## Available Scripts

In the project directory, you can run:

-   `npm run dev`: Runs the app in development mode.
-   `npm run build`: Builds the app for production.
-   `npm run start`: Starts a production server.
-   `npm run lint`: Lints the code using Next.js's built-in ESLint configuration.
-   `npm run genkit:dev`: Starts the Genkit development server.
-   `npm run genkit:watch`: Starts the Genkit server in watch mode.
