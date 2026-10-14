# Setu AI (सेतु)
> **AI-Powered Personal Health Copilot • Bridging Medical Records to Human Understanding & ABDM Interoperability**

[![Live Demo](https://img.shields.io/badge/Live%20Demo-team--bread.vercel.app-0D9488?style=for-the-badge&logo=vercel)](https://team-bread.vercel.app)
[![GitHub Repository](https://img.shields.io/badge/GitHub-team-%2Fbread-181717?style=for-the-badge&logo=github)](https://github.com/dat1aryan/team_bread)
[![Next.js 14](https://img.shields.io/badge/Next.js-14.2-black?style=for-the-badge&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.6-3178C6?style=for-the-badge&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.4-38B2AC?style=for-the-badge&logo=tailwind-css)](https://tailwindcss.com/)
[![Supabase](https://img.shields.io/badge/Supabase-PostgreSQL%20%2B%20RLS-3ECF8E?style=for-the-badge&logo=supabase)](https://supabase.com/)
[![ABDM FHIR R4](https://img.shields.io/badge/ABDM-HL7%20FHIR%20R4%20Compliant-FF6F00?style=for-the-badge)](https://abdm.gov.in/)

---

## Executive Summary

Over **78% of chronic patients in India** manage their healthcare journey using fragmented paper envelopes: handwritten physician prescriptions, multi-page pathology lab reports, and hospital discharge summaries. Patients frequently struggle with medical jargon, miss borderline biomarker trajectories (such as creeping HbA1c or blood pressure fluctuations), and face linguistic isolation when documents are in English.

**Setu AI (सेतु)** bridges this gap by transforming physical health records into structured, empathetic, plain-language health intelligence. Designed to align with the **Ayushman Bharat Digital Mission (ABDM)**, Setu combines multi-modal clinical OCR, 7 regional Indian languages with voice synthesis, longitudinal biomarker charting, drug-interaction safety watchdogs, and HL7 FHIR R4 exports into a unified, accessible digital platform.

---

## Key Features & Capabilities

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                          Setu AI Copilot Engine                          │
└──────┬───────────────────────┬───────────────────────┬──────────────────────┘
       │                       │                       │
       ▼                       ▼                       ▼
┌──────────────┐       ┌──────────────┐       ┌─────────────────┐
│ Multi-Modal  │       │ Multilingual │       │ ABDM & FHIR R4  │
│ Vision OCR   │       │ AI & Voice   │       │ Digital Card    │
└──────┬───────┘       └──────┬───────┘       └────────┬────────┘
       │                      │                        │
       ▼                      ▼                        ▼
┌──────────────┐       ┌──────────────┐       ┌─────────────────┐
│ Longitudinal │       │ Medication   │       │ AI Copilot with │
│ Vital Trends │       │ Tracker & Rx │       │ App Actions     │
└──────────────┘       └──────────────┘       └─────────────────┘
```

### 1. Multi-Modal Medical Vision OCR & Webcam Scanner
- **Zero-Friction Ingestion**: Accepts images, camera snapshots, PDFs, and live webcam captures of paper prescriptions, lab reports, and discharge summaries.
- **Clinical Entity Extraction**: Automatically extracts medications, dosages (e.g. 500mg), frequencies (OD, BD, TID), meal timing relations (Before/After Food), measured lab values, reference intervals, and ICD-10 diagnoses.
- **Zero-Downtime Testbench**: Includes 4 instant evaluation test cases (Diabetic & Lipid Panel, Cardio Prescription, Hospital Discharge, CBC Hematology) so evaluators can test with zero uploaded files.

### 2. Explainable Plain-Language Medical Summaries
- **8th-Grade Reading Level**: Converts complex laboratory pathology into clear, reassuring language without medical jargon.
- **Physiological "Why It Matters" Narratives**: Explains the biological mechanisms behind abnormal flags (e.g., explaining why HbA1c reflects 90-day glucose saturation).
- **Consultation Prep**: Generates personalized, high-priority questions for patients to ask their physician during their next visit.

### 3. 7 Regional Languages & Native Voice Synthesis
- **Multilingual Support**: Fully localized in **English**, **हिन्दी (Hindi)**, **తెలుగు (Telugu)**, **தமிழ் (Tamil)**, **বাংলা (Bengali)**, **मराठी (Marathi)**, and **Español (Spanish)**.
- **Voice Read-Aloud**: Browser-based speech synthesis delivers voice translations in regional accents for accessibility and elderly or semi-literate patient support.

### 4. Medication Tracker & Drug Collision Safety Watchdog
- **Time-of-Day Schedule**: Automatically organizes prescriptions into Morning, Afternoon, Evening, and Night routines with meal-timing tags.
- **Adherence & Streak Tracking**: Allows patients to mark doses as taken and build daily adherence streaks.
- **Drug-Drug Collision Watchdog**: Real-time pharmacokinetic safety analysis identifies complementary multi-therapy regimens (e.g., Metformin + Telmisartan + Atorvastatin) and flags potential contraindications.

### 5. Longitudinal Vital Trends & Analytics
- **Dynamic Recharts Trajectories**: Interactive charts track historical progression of HbA1c, Fasting Blood Sugar, LDL Cholesterol, and Blood Pressure against clinical target boundaries.
- **Manual Reading Logger**: Built-in modal allows patients to log daily home blood glucose or blood pressure readings directly.

### 6. Ayushman Bharat (ABDM) & HL7 FHIR R4 Gateway
- **ABDM Health Card**: Digital health card with official layout, QR code, and ABHA ID verification status.
- **Gateway OTP Flow**: Interactive ABDM national gateway verification flow for ABHA numbers and addresses.
- **HL7 FHIR R4 Bundle Export**: Generates compliant FHIR R4 JSON bundles containing `Patient`, `Observation`, `DiagnosticReport`, and `MedicationRequest` resources for national health record interoperability.

### 7. Context-Grounded Clinical AI Copilot with Active App Commands
- **Grounded in Personal Profile**: AI responses use the authenticated patient's actual medical records, active medications, and recent lab observations.
- **Application Read/Write Control**: Executes live in-app action tags:
  - `[[ACTION:NAVIGATE:meds]]` — Navigates user across dashboard tabs
  - `[[ACTION:ADD_MED:...]]` — Adds medications directly to the user's schedule
  - `[[ACTION:LOG_VITAL:...]]` — Logs numerical biomarker readings into vital trends
  - `[[ACTION:TOGGLE_TAKEN:...]]` — Marks doses as taken in real-time

---

## Production Architecture

```
   [User Browser / Patient / Doctor]
                  │
                  ▼
      ┌─────────────────────────┐
      │   FRONTEND (Vercel)     │  ◄── Next.js 14 App Router
      │   team-bread.vercel.app │      TypeScript + Tailwind CSS
      └───────────┬─────────────┘
                  │  Server-Side API Handlers
                  ├───────────────────────────────┐
                  ▼                               ▼
      ┌─────────────────────────┐     ┌─────────────────────────┐
      │   BACKEND (Render)      │     │  DATABASE (Supabase)    │
      │   Node/Express API      │     │  PostgreSQL + RLS       │
      │   setu-api.onrender.com │     │  Encrypted Storage S3   │
      └───────────┬─────────────┘     └─────────────────────────┘
                  │
                  ▼
      ┌─────────────────────────┐
      │   AI ENGINE (Google)    │
      │   Google Gemini Failover Engine (3.5 Flash Lite / 3.1 Flash Lite)│
      └─────────────────────────┘
```

- **Frontend (Vercel)**: Next.js 14 App Router with edge-ready static prerendering, client-side encryption, and fluid responsive design.
- **Backend (Render)**: Express.js microservice (`/backend`) providing REST endpoints, Docker containerization, and `/health` monitoring.
- **Database (Supabase)**: Cloud PostgreSQL with Row-Level Security (RLS) guaranteeing strict tenant isolation, alongside Supabase Auth (Email + Google OAuth).
- **AI Vision Engine**: Google Google Gemini Failover Engine (3.5 Flash Lite / 3.1 Flash Lite) backed by a multi-key automated failover rotation pool (`gemini-pool.ts`) with client-side Tesseract.js OCR fallback.

---

## Technology Stack

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Framework** | Next.js 14.2 (App Router) | Server-side rendering, API routes, optimized bundles |
| **Language** | TypeScript 5.6 | Strict static type safety across frontend and backend |
| **Styling** | Tailwind CSS 3.4 | Modern medical-grade UI, glassmorphism, responsive design |
| **Icons & UI** | Lucide React | Medical and navigational iconography |
| **Charts** | Recharts 2.12 | Longitudinal vital trajectories and clinical threshold bands |
| **Database & Auth** | Supabase (PostgreSQL + RLS) | Tenant-isolated health record storage & Google OAuth |
| **Medical Vision AI** | Google Gemini Failover Engine (3.5 Flash Lite / 3.1 Flash Lite) | Multi-modal prescription & lab report OCR extraction |
| **Client OCR Fallback** | Tesseract.js 5.1 | In-browser OCR with Canvas image enhancement |
| **Health Standard** | HL7 FHIR R4 | National health interoperability under ABDM specifications |
| **Audio Synthesis** | Web Speech API | Text-to-speech voice read-aloud across Indian languages |
| **Error Monitoring** | Sentry Next.js SDK | Production error tracking and performance telemetry |

---

## Quick Start & Local Setup

### Prerequisites
- Node.js `20.x` or `22.x`
- npm `10.x`+
- Git

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/scholzisshit/bread.git
cd bread

# 2. Install dependencies
npm install

# 3. Configure environment variables
cp .env.example .env.local

# 4. Start the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Environment Configuration (`.env.local`)

```env
# Application URL
NEXT_PUBLIC_APP_URL=http://localhost:3000

# Supabase Cloud Configuration
NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-supabase-anon-key

# Google Gemini Vision & LLM Key
GEMINI_API_KEY=your-gemini-api-key

# Optional: Sentry Error Telemetry
NEXT_PUBLIC_SENTRY_DSN=your-sentry-dsn
```

> **Zero-Config Resilient Mode**: If external API keys are omitted, Setu automatically engages its **Built-In Resilient Fallback Engine**, ensuring full offline accessibility and 100% demo uptime for evaluators.

---

## 5-Minute Evaluator Quick Start

| Step | Action | Expected Result |
| :---: | :--- | :--- |
| **1** | Open [team-bread.vercel.app](https://team-bread.vercel.app) | Landing page with product overview and route protection. |
| **2** | Sign in with any email (e.g. `evaluator@setu.health` / `TestPass@2026`) or Google OAuth | Automatic redirect to the unified `/dashboard`. |
| **3** | Click any sample card under **Scan & Analyze Record** | High-precision extraction of medications, biomarkers, and diagnoses. |
| **4** | Toggle languages in the top navigation bar | Real-time translation to Hindi, Telugu, Tamil, Bengali, Marathi, or Spanish. |
| **5** | Click **"बोलकर सुनाएं / Listen"** | Native regional voice synthesis plays the clinical summary. |
| **6** | Navigate to **Vital Trends** & **Medication Schedule** | Interactive Recharts trajectories and time-of-day medication adherence tracking. |
| **7** | Navigate to **ABDM / ABHA Hub** | View verified ABHA ID card and download compliant HL7 FHIR R4 JSON bundle. |
| **8** | Chat with **AI Copilot** | Grounded clinical advice with automated application command execution (`[[ACTION:...]]`). |

---

## Project Structure

```
├── Documentation/                 # Comprehensive engineering specifications
│   ├── 01_PRD_Setu_Copilot.md
│   ├── 02_TRD_Technical_Architecture.md
│   ├── 03_App_Flow_and_User_Journeys.md
│   ├── 04_UI_UX_Design_System.md
│   ├── 05_Backend_Schema_and_ABDM_FHIR_Models.md
│   ├── 06_Implementation_Testing_and_Deployment_Guide.md
│   └── 07_Architecture_and_Presentation_Deck.md
├── backend/                      # Optional Node/Express microservice for Render
│   ├── src/
│   │   ├── gemini.ts             # Server-side Vision extraction engine
│   │   └── server.ts             # Express REST endpoints & health checks
│   ├── Dockerfile
│   └── package.json
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   ├── chat/route.ts     # Context-grounded Gemini Chatbot route
│   │   │   └── ocr/route.ts      # Multi-modal Gemini OCR Vision route
│   │   ├── dashboard/page.tsx    # Unified 6-tab clinical dashboard
│   │   ├── layout.tsx            # Root layout with Sentry & SEO meta
│   │   └── page.tsx              # Landing hero & dynamic route guard
│   ├── components/               # Modular UI components
│   │   ├── AbdmAbhaHub.tsx       # ABHA Health Card & FHIR R4 Inspector
│   │   ├── AiHealthChatbot.tsx   # Contextual conversational copilot
│   │   ├── DocumentUploader.tsx  # Drag-and-drop ingestion & test bench
│   │   ├── ExtractionResultsView.tsx # Entity review & plain-language summary
│   │   ├── HealthTimeline.tsx    # Chronological patient journey feed
│   │   ├── MedicationTracker.tsx # Daily schedule & drug collision watchdog
│   │   ├── VitalTrendsChart.tsx  # Recharts biomarker graphs & logger
│   │   └── WebcamScannerModal.tsx# Live document capture
│   ├── lib/
│   │   ├── abdm-fhir.ts          # HL7 FHIR R4 Bundle generator & ABDM OTP
│   │   ├── gemini-pool.ts        # Multi-key failover rotation pool
│   │   ├── medical-ai.ts         # Clinical AI rules & online analyzer
│   │   ├── multilingual.ts       # 7-language dictionary & TTS speech synthesis
│   │   ├── ocr-service.ts        # Canvas image enhancement & Tesseract.js
│   │   ├── sample-data.ts        # Pre-loaded clinical test cases & profiles
│   │   ├── storage.ts            # Local resilience & Supabase sync engine
│   │   └── supabase.ts           # Supabase client & connection helpers
│   └── types/                    # Core TypeScript clinical interfaces
├── supabase_schema.sql           # Complete PostgreSQL RLS database schema
└── package.json
```

---

## Security, Privacy & Clinical Safety

- **Tenant Isolation**: PostgreSQL Row-Level Security (RLS) ensures that authenticated users can only view, mutate, and delete their own clinical records.
- **Client-Side Secret Protection**: Privileged Google Gemini and Supabase service-role keys operate exclusively inside server-side Next.js route handlers. No API credentials are leaked to the browser.
- **Clinical Guardrails**: Setu does not diagnose diseases autonomously. All advice includes clear medical disclaimers, triage urgency indicators (Routine, Consult Soon, Urgent), and emphasizes consultation with licensed physicians.

---

## License & Attribution

Developed for **HacXLerate 2026** by byteXL & Altrix Labs.  
All medical entity mappings adhere to NRCES India / ABDM HL7 FHIR R4 specifications.
