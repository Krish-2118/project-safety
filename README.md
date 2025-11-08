# Smart Analytics Dashboard for Police Good Work Recognition

A real-time, AI-assisted dashboard that analyzes CCTNS “Good Work Done” reports, visualizes district-wise performance, and generates recognition insights for police leadership.

---

## Architecture Overview

**Architecture Pattern:** Client-centric, serverless, with AI-assisted server actions.

### Frontend (Client-Side)
- **Framework:** Next.js 15 (App Router) + React 18
- **UI:** ShadCN components + Tailwind CSS
- **Charts & Data Handling:** Recharts for visualization, `useMemo` for client-side aggregation and filtering
- **Responsiveness:** All analysis and charts render instantly on the client for smooth interaction

### Data Layer (Firebase)
- **Database:** Cloud Firestore (NoSQL) as the single source of truth
- **Collections:** `records` storing Good Work entries
- **Real-Time Updates:** `onSnapshot` (via `useCollection`) enables live UI updates whenever data changes

### Backend AI Layer (Server-Side)
- **Server Execution:** Next.js **Server Actions** for secure, server-only logic
- **AI Runtime:** **Genkit** to orchestrate server-side AI workflows ("flows")
- **Model Used:** Google **Gemini** for:
  - Extracting structured data from PDFs
  - Generating narrative summaries and insights

---

## Key Features
- Upload & process CCTNS Good Work records (CSV/PDF)
- Live district and event-wise performance dashboard
- Trends, charts, and comparative analytics
- AI-generated monthly performance summaries
- One-click report export for recognition

---

## Getting Started
```bash
git clone https://github.com/your-username/smart-police-dashboard.git
cd smart-police-dashboard

npm install
npm run dev
