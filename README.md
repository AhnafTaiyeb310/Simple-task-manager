# Simple Task Manager App

A simple full-stack task management application built as a developer take-home assignment.

## Tech Stack
- **Frontend**: Next.js (App Router, Tailwind CSS, TypeScript)
- **Backend**: Django & Django REST Framework (DRF)
- **Database**: SQLite

---

## Prerequisites
Ensure you have the following installed:
- Python (>= 3.10)
- Node.js (>= 18.x) & npm
- [uv](https://github.com/astral-sh/uv) (Recommended python tool, but standard `pip` works too)

---

## Getting Started

### 1. Run the Backend (Django)

Open a terminal window and navigate to the backend directory:
```bash
cd backend
```

Create a virtual environment and install python dependencies:
```bash
# Create virtual environment
python -m venv .venv

# Activate virtual environment
# On Windows (Command Prompt):
.venv\Scripts\activate.bat
# On Windows (PowerShell):
.venv\Scripts\Activate.ps1
# On macOS/Linux:
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
# (Or if using uv): uv sync
```

Apply database migrations:
```bash
python manage.py migrate
```

Start the Django development server:
```bash
python manage.py runserver
```
The API backend will run at `http://127.0.0.1:8000/`.

---

### 2. Run the Frontend (Next.js)

Open a new terminal window and navigate to the frontend directory:
```bash
cd frontend
```

Install the dependencies:
```bash
npm install
```

Start the Next.js development server:
```bash
npm run dev
```
Open `http://localhost:3000` in your web browser. The Next.js dev server will proxy requests from `http://localhost:3000/api/` to the Django backend.

---

## Clean Code & Architecture Highlights
- **Separation of Concerns**: Separated UI components, API queries, types, and model-serializer logic.
- **Robust Error Handling**: Type-safe error boundaries using TypeScript `unknown` checks. Displays descriptive connection errors instead of swallowing issues.
- **Defensive UI UX**: Input fields and change states are disabled during active API requests to prevent double-submissions or race conditions.
- **Inline Form Validation**: Validation errors are managed via state and rendered directly on the form inputs.
