# RevoU Job Tracker x AI Coach

## Table of Contents
- [Project Overview](#project-overview)
- [Key Objectives](#key-objectives)
- [Technology Stack](#technology-stack)
- [Core Functionalities](#core-functionalities)
- [AI Chatbot Integration](#ai-chatbot-integration)
- [Responsive Design](#responsive-design)
- [Error Handling](#error-handling)
- [Documentation](#documentation)
- [Project Structure](#project-structure)
- [Additional Considerations](#additional-considerations)

## Project Overview
The RevoU Job Tracker x AI Coach is a web application designed to help RevoU students log, track, and analyze their job application efforts. It integrates two main components into a single platform:

1. **Job Tracking Module**: Enables students to log their job applications, view historical applications, filter results, and analyze trends with charts.
2. **AI Coach Module**: Provides an integrated chatbot using Flowise for personalized guidance and support during the job hunting process.

By combining these functionalities, the application aims to streamline the job application workflow and offer targeted advice through an AI-driven chat interface.

## Key Objectives
- Consolidate job logging and AI coaching tools into a single web application.
- Ensure secure authentication so only authorized users can access the platform.
- Provide a user-friendly interface for inputting, viewing, and filtering job application data.
- Present visual analytics (charts) for weekly job application tracking.
- Offer an integrated AI chatbot to guide students through their job search process.

## Technology Stack
- **Frontend**: Next.js, shadcn UI, Tailwind CSS, Lucid Icons
- **Backend**: Supabase for Authentication, Database, and Bucket Storage
- **AI Chatbot**: Flowise React Embed (integrated into the frontend)

## Core Functionalities

### 1. Authentication
- **Feature**: Check if users are authenticated each time they access the web application.
- **Flow**: 
  - If not authenticated, redirect to a login page.
  - If authenticated, grant access to the dashboard and related functionalities.

### 2. Homepage (Usage Guide)
- **Content**: Explains how to use the integrated tools (Job Tracker and AI Coach).
- **UI**: Simple overview with step-by-step instructions and links to the submodules.

### 3. Sidebar Navigation
- **Persistent Sidebar**: A dedicated sidebar menu that allows users to switch between:
  - **Job Application Module**
  - **AI Chatbot Module**

### 4. Job Application Module
- **Form Submission**: A form where users can input details of their job applications, such as:
  - Job Title
  - Company Name
  - Application Date
  - Application Stage (e.g., Applied, Interview, Offer)
- **View & Manage Applications**: A table listing all submitted applications. Users can:
  - Sort and filter by date applied, job title, or application stage.
  - Edit or update application details as needed.
- **Charts & Analytics**: Visual charts (e.g., line or bar graphs) to display weekly trends in the number of applications submitted.
- **Filters**: Date range filters, job title filters, and application stage filters.

## AI Chatbot Integration
- **Agents Selection**: A dropdown to select from multiple AI agents (configured via Flowise) for different coaching personas.
- **Embedded Chat Window**: Uses Flowise React Embed to provide a custom chat window. Students can ask questions and receive guidance or advice related to their job search.
- **Customization**: The chat widget’s appearance, tooltips, disclaimers, and branding are configured as per the Flowise Embed example code.
- **Features**:
  - Start chat upon page load or when triggered by the user.
  - Display tooltips and disclaimers before initiating the conversation.
  - Offer pre-set starter prompts for quick queries.

## Responsive Design
- Ensure that all pages and components are accessible and visually appealing across various screen sizes and devices.
- Test UI components for mobile, tablet, and desktop responsiveness.

## Error Handling
- Display clear error messages for:
  - Authentication errors (invalid login).
  - Network issues when fetching data from Supabase or submitting forms.
  - Validation errors on job application form fields.
- Offer fallback UI or prompts to re-try the action in case of API failure.

## Documentation

### Prerequisites
- Node.js (v14 or later)
- npm or yarn package manager

### Installation
```bash
# Clone the repository
git clone <repository-url> revou-ai-nextjs

# Navigate to the project directory
cd revou-ai-nextjs/revo-ai-coach

# Install dependencies
npm install
# or
yarn install
```
## Running the Development Server
```
npm run dev
# or
yarn dev
```

Open http://localhost:3000 in your browser to access the application.

## Building for Production

```
npm run build
npm start
# or
yarn build
yarn start
```

Project Structure
```
revou-ai-nextjs
└── revo-ai-coach
    ├── README.md
    ├── app
    │   ├── favicon.ico
    │   ├── fonts
    │   ├── globals.css
    │   ├── layout.tsx
    │   └── page.tsx
    ├── components.json
    ├── lib
    │   └── utils.ts
    ├── next-env.d.ts
    ├── next.config.mjs
    ├── package-lock.json
    ├── package.json
    ├── postcss.config.mjs
    ├── tailwind.config.ts
    └── tsconfig.json
```

## Directory Descriptions
app/: Contains Next.js pages, layout, and global styling.
lib/: Utility functions and support files.
components.json: UI components configuration.
tailwind.config.ts: Tailwind CSS configuration.
tsconfig.json: TypeScript configuration files.

## Additional Considerations
Security: Ensure that user data (e.g., job application info) is secure and accessible only to authenticated users.
Data Privacy: Clearly communicate the handling of user-submitted data and ensure compliance with relevant data protection regulations.
Maintenance & Scalability: Plan for future enhancements, such as adding more AI agents or expanding the analytics capabilities.