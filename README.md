# MindStream — Chatbot with Real-time Response Analysis

MindStream is an elegant, full-stack chatbot web application that integrates Gemini AI conversational answers with instant, real-time response telemetry. 

Every time a message is sent, the Node.js Express backend triggers parallel AI tasks. One stream generates a conversational reply, and a dependent promise immediately utilizes structural JSON parameters (using Gemini's response schema validation) to extract sentiment badges, dialogue tones, and confidence indicators.

---

## Unified Full-Stack Architecture

To ensure the highest quality of service, security of API keys, and compatibility with Cloud Run runtime environments, this application employs a **Unified TypeScript Full-Stack Structure**:
- **Unified package.json**: Dependencies are managed collectively to eliminate version mismatching.
- **Express Server (`server.ts`)**: Serves as the single API hosting server on port `3000`.
- **Integrated Vite Middleware**: Express mounts the Vite development server globally in dev mode and serves statically compiled client assets in production. This allows both the API endpoints and the frontend to run simultaneously on a single host.

---

## Core Features

1. **Intelligent Dialogue Partner**: Driven by **Gemini 3.5 Flash** (the official, up-to-date replacement for unsupported 2.0-flash models) to provide helpful, conversational assistance.
2. **Real-time Telemetry Dashboard**:
   - **Sentiment Indicator**: Green (positive), amber (neutral), or red (negative).
   - **Intent Analysis**: Classifies conversational objectives (informational, emotional, transactional).
   - **Tone Profiling**: Evaluates conversation style (formal, casual, empathetic).
   - **Confidence Meter**: Animated indicator representing schema reliability.
3. **Historical Trend Distribution**: Monitors average dialogue confidence and aggregates pie/bar metrics across the entire chat duration.
4. **Local State Persistence**: Automatic `localStorage` synchronisation keeps dialogues intact through page refreshes.

---

## Quick Setup and Run

Ensure you have [Node.js](https://nodejs.org) installed on your system.

### 1. Install Dependencies
Run a single command in the project root to install all required dependencies (both client and server packages are managed unified):
```bash
npm install
```

### 2. Configure Environment Variables
Create a file named `.env` in the root of the project with your private Gemini API key:
```env
GEMINI_API_KEY="your_actual_gemini_api_key_here"
```

### 3. Run Development Server
Start the unified Express + Vite server locally on port 3000:
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) in your web browser.

---

## Production Build and Hosting

To compile the application for deployment or high-performance hosting:

```bash
# Clean previous build artifacts
npm run clean

# Build static frontend assets and bundle the Express server into dist/server.cjs
npm run build

# Start the optimized Node.js production server
npm run start
```
