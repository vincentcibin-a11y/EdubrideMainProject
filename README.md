# EduBridge — MCA Main Project (20MCA246)

**Project title:** EduBridge — Peer-to-Peer Academic Doubt Solving and Student Tutoring Platform  
**Student:** Cibin Vincent  
**Programme:** MCA, Federal Institute of Science and Technology (FISAT), Angamaly  
**Course:** 20MCA246 Main Project  
**Repository:** https://github.com/vincentcibin-a11y/EdubrideMainProject

EduBridge is a full-stack web application for student peer-learning. Students can post academic doubts, answer peers, discover tutors by subject or skill, request tutoring sessions, track booking status, receive notifications, and review completed sessions.

> **Submission integrity:** Keep this repository’s dated records truthful. Replace all “TO BE RECORDED” placeholders with actual dates, supervisor/Product Owner feedback, test outputs, screenshots and evaluation results. Do not present planned activities as completed or fabricate signatures/approvals.

## How this repository maps to 20MCA246

The course requires an individual, in-house real-life project, prior synopsis approval, incremental Scrum development using two-week sprints, short progress meetings about every three days, a dated Scrum Book, Git version control, testing at multiple stages, documentation, deployment evidence, interim Project Assessment Board evaluations, and final internal/external evaluation.

This repository provides a version-controlled project and academic artefacts. The student remains responsible for lab attendance, actual meetings and demos, supervisor approvals, board evaluation and university submission procedures.

## Repository structure

- `frontend/` — React user interface.
- `backend/` — Express REST API, authentication, routes, Mongoose models and automated tests.
- `docs/` — architecture, project documentation, Scrum Book, tests and submission checklist.
- `.github/workflows/` — continuous-integration workflow.
- `docker-compose.yml` — repeatable local multi-service environment.
- `EduBridge_First_Review_Presentation_FINAL_10_10.pptx` — existing review presentation; update it against actual review feedback before presenting.

## Course outcomes: evidence plan

| CO | Required outcome | Evidence to maintain in this project |
|---|---|---|
| CO1 | Identify a real-life project useful to society/industry | Problem statement, stakeholder need, scope, project synopsis |
| CO2 | Interact with people to identify requirements | Dated stakeholder/interview notes, questions, approval or feedback |
| CO3 | Apply a suitable development methodology | Product backlog, two-week sprint plans, reviews, retrospective notes |
| CO4 | Analyse and design the product | Requirements, architecture, ER/data model, UI sketches, API contracts |
| CO5 | Test modules during development | Unit/API/integration/manual test logs, defects, regression results |
| CO6 | Build and integrate modules | Versioned source, integration commits, working end-to-end demonstration |
| CO7 | Document and deploy the project | Final report, Scrum Book, setup guide, CI evidence, deployment/health-check evidence |

## Recommended Scrum cadence

- Sprint length: **two weeks**.
- Progress check-ins: aim for **once every three days**, under 15 minutes when practical; record actions and actual dates.
- Sprint review: every two weeks, no longer than 30 minutes; demo the working increment to the Project Guide/Product Owner.
- Keep sprint reviews separate from Project Assessment Board evaluations.
- A possible course calendar is in `docs/PROJECT_PLAN.md`; adapt it to the official KTU academic calendar and your supervisor’s instructions.

## Local development

Prerequisites: Git, Node.js/npm, and either Docker Compose or a local MongoDB instance.

### Docker Compose

```bash
git clone https://github.com/vincentcibin-a11y/EdubrideMainProject.git
cd EdubrideMainProject
cp .env.example .env
# Replace example secrets with private strong development values.
docker compose up --build
```

Frontend: `http://localhost:5173`  
API health check: `http://localhost:5000/api/health`

### Test and build

```bash
cd backend
npm ci
npm test
```

If the integration tests require MongoDB, start the configured test database first (CI uses a dedicated MongoDB service). Then build the frontend:

```bash
cd ../frontend
npm ci
npm run build
```

Record actual command output, date, environment and result in `docs/TESTING_AND_VALIDATION.md`. A successful automated test run is not a substitute for user acceptance tests or screenshots captured from a running system.

## Academic document index

- [Project Synopsis](docs/PROJECT_SYNOPSIS.md)
- [Full Project Documentation](docs/EduBridge_Project_Documentation.md)
- [Scrum Book / Rough Record](docs/EduBridge_Scrum_Book.md)
- [Two-week Sprint Plan and Review Calendar](docs/PROJECT_PLAN.md)
- [Testing and Validation Log](docs/TESTING_AND_VALIDATION.md)
- [Product Backlog](docs/PRODUCT_BACKLOG.md)
- [Final Submission Checklist](docs/Final_Submission_Checklist.md)
- [System Architecture](docs/ARCHITECTURE.md)
- [Manual Acceptance Test Evidence](docs/Manual_Acceptance_Test_Evidence.md)
- [Screenshot Evidence Guide](docs/evidence/README.md)

## Deployment note

Docker Compose currently supports local development and reproducible builds. Treat production deployment as incomplete until a real hosting target is configured and tested. Before deploying, configure protected secrets, a production database, correct frontend CORS origin, HTTPS and a health check. Never commit `.env`, real credentials, tokens, student private data or production database URLs.

## Version control

Use meaningful commits for each feature, test, documentation revision and sprint increment. Keep this project’s commit history intact and include the final commit hash/release tag in the submission report. Do not squash away required evidence of incremental work unless the supervisor specifically requests it.
