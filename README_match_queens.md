# Match Queens

Match Queens is a mentoring platform that connects mentors and mentees and helps them manage the process from the first request to a scheduled meeting.

The project was developed by a team during the QueenB × AppsFlyer Software Engineering Bootcamp in August–September 2026. This repository is my portfolio copy of the team project.

## What the app does

- Browse mentor profiles and send mentoring requests.
- Track requests through the scheduling process.
- Suggest, select, and manage meeting times.
- View mentor and mentee dashboards.
- Manage accounts, profiles, notifications, and meeting feedback.
- Provide administrative tools for managing users and meetings.
- Support a WhatsApp companion for mentors through a provider integration.

Some integrations require separate credentials and configuration.

## My work

I worked with the team on the scheduling and backend flows, including request status handling, duplicate-request cases, API integration, and database-related work.

The project gave me experience working with an existing codebase, connecting frontend actions to backend endpoints, and coordinating changes across a shared application.

## Tech stack

| Area | Technologies |
| --- | --- |
| Frontend | React, Material UI, Axios |
| Backend | Node.js, Express |
| Database | PostgreSQL, Prisma |
| API | REST/HTTP |
| Authentication | Server-side sessions |
| Development | JavaScript, Git |

## Project structure

```text
client/             React application
server/
  config/           Server and session configuration
  middleware/       Request middleware
  routes/           API routes
  services/         Business logic
  integrations/     External messaging integrations
  prisma/           Database schema and migrations
```

## Running locally

You need Node.js, npm, and a local PostgreSQL database.

1. Clone this repository and open it in a terminal.
2. Install the dependencies:

   ```bash
   npm install
   npm run install-all
   ```

3. Create `server/.env` from `server/.env.example`. Set your PostgreSQL connection details and generate a unique `SESSION_SECRET`. Keep credentials out of Git.
4. Prepare the database:

   ```bash
   cd server
   npx prisma generate
   npx prisma migrate dev
   cd ..
   ```

5. Start the frontend and backend:

   ```bash
   npm run dev
   ```

The frontend is configured to run on `http://localhost:3000`, and the backend defaults to `http://localhost:5000`. You can check the backend at `http://localhost:5000/api/health`.

Email, WhatsApp, and other external integrations need their own configuration. They are not required to understand the core project.

## Notes

This is a collaborative bootcamp project, not a production deployment. Authentication and authorization across all API routes, external webhook verification, and deployment configuration should be reviewed and hardened before exposing it on the public internet.

No real passwords, API keys, or user data should be committed to this repository.

## Credits

Developed collaboratively as part of the QueenB × AppsFlyer Software Engineering Bootcamp. The starter application and work by other team members are part of the project's history.
