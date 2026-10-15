# ResumeLens AI

> **See the fit. Find the gaps. Improve with purpose.**

ResumeLens AI is an AI-powered resume review tool designed to help job seekers evaluate how well their resume aligns with a specific job description. It aims to turn a resume from a static document into an actionable improvement plan—with relevant skills, missing keywords, and practical suggestions in one place.

> **Project status:** In development. This README describes the intended project scope; update the feature checklist as each feature is implemented and tested.

## ✨ What it aims to do

- **Resume analysis** — Upload a PDF resume and extract its content for review.
- **Job-description matching** — Compare the resume against a role-specific job description instead of producing a generic review.
- **Skills gap insights** — Surface relevant skills and keywords that appear to be present, missing, or insufficiently evidenced.
- **Actionable feedback** — Suggest concrete improvements to resume bullets, clarity, relevance, and impact.
- **Analysis history** — Revisit previous reviews and compare iterations, if enabled in the final build.
- **A focused workflow** — Keep the process simple: upload, provide the role, review insights, improve, and repeat.

## 🧭 How it works

1. Upload your resume.
2. Paste the job description for the role you are targeting.
3. ResumeLens AI extracts the resume text and evaluates it against the job description.
4. Review the match insights, skill gaps, and suggested improvements.
5. Revise your resume and run the analysis again.

## 🛠️ Tech stack

| Layer | Technology |
|---|---|
| Frontend | React |
| Backend API | Node.js, Express.js |
| Database | MongoDB |
| AI analysis | Google Gemini API |
| Authentication | JWT-based authentication, if included in the final build |
| Resume input | PDF upload and text extraction |

The stack may change as the project evolves. The backend should handle AI requests and keep private API keys off the client.

## 🚀 Getting started

### Prerequisites

- Node.js and npm
- A MongoDB instance or MongoDB Atlas connection string
- A Google Gemini API key

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd resumelens-ai
```

### 2. Install dependencies

If the project uses separate frontend and backend folders, install dependencies in each one:

```bash
cd server
npm install

cd ../client
npm install
```

> Folder names and run commands should be adjusted to match the repository structure once it is finalized.

### 3. Configure environment variables

Create a `.env` file in the backend folder. Use the variable names expected by your code; a typical setup looks like this:

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=replace_with_a_long_random_secret
GEMINI_API_KEY=your_gemini_api_key
CLIENT_URL=http://localhost:5173
```

For a Vite frontend, the API base URL can be configured in the frontend's `.env` file:

```env
VITE_API_BASE_URL=http://localhost:5000/api
```

**Never commit `.env` files, credentials, tokens, or API keys.** Keep the Gemini API key on the server and add `.env` to `.gitignore`.

### 4. Run the app

Start the backend and frontend in separate terminals using the scripts configured in their respective `package.json` files. For example:

```bash
# Terminal 1
cd server
npm run dev

# Terminal 2
cd client
npm run dev
```

Open the local URL printed by the frontend development server.

## 🗺️ Development roadmap

- [ ] Build a responsive resume upload and job-description form.
- [ ] Validate file type and size; handle malformed or empty PDFs.
- [ ] Extract resume text on the backend.
- [ ] Integrate Gemini through a server-side API endpoint.
- [ ] Return structured results for skills, gaps, keywords, and recommendations.
- [ ] Add clear loading, empty, success, and error states.
- [ ] Add authentication and saved analysis history, if retained in scope.
- [ ] Test edge cases and protect endpoints against abuse.
- [ ] Deploy the frontend and backend.
- [ ] Add screenshots, a live demo, and setup instructions verified against the final code.

## 🔐 Privacy and responsible use

Resumes can contain personal information. The app should only collect what is necessary, clearly explain how uploaded content is handled, and provide a way to delete stored data if persistence is implemented. Avoid uploading confidential documents unless you understand how the deployed service processes and stores them.

ResumeLens AI is an informational assistant, **not an official Applicant Tracking System (ATS)**. Any match score or recommendation is an estimate based on the app's analysis—not a guarantee of ATS performance, interview selection, or employment. Users should verify suggestions and never add skills or experience they do not actually have.

## 🧪 Testing checklist

Before calling a release ready, test at least:

- Valid PDF, oversized PDF, empty PDF, and unsupported file type
- Missing or very short job description
- AI API timeout, quota limit, and malformed response
- Invalid or expired authentication token, if authentication is implemented
- Empty results and long resume content
- Mobile layout, keyboard navigation, and readable error messages

## 📸 Screenshots

Screenshots and a live demo will be added after the core workflow is implemented and deployed.

## 🎯 Project goal

This project is being built to practise full-stack development, secure API integration, file handling, AI-assisted product design, and user-focused error handling. The priority is not just to generate an AI score, but to build a reliable workflow that gives users understandable and useful next steps.

---

**Built as a learning project.** Feedback and suggestions are welcome as the project develops.