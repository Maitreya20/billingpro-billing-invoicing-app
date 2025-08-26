# BillingPro - Full-Stack Billing/Invoicing Web App

A production-ready, full-stack web app that handles billing/invoicing, payment reminders, customer CRM, plan display, a customer payment portal, and an automated agent that generates and forwards invoice PDFs after final billing. Optimized for small service businesses (e.g., internet providers, CCTV installers, PC/laptop/mobile/printer repair & refilling).

## Features

- Multi-tenant setup (single app, many businesses)
- Customer & Asset CRM
- Plans & Pricing
- Billing & Invoicing
- Payment Portal (Customer-facing)
- Automated Reminder Engine
- Automated PDF Forwarding Agent
- Reporting & Dashboard
- Roles & Permissions
- Security & Compliance

## Tech Stack

- **Frontend**: React + TypeScript, Next.js, TailwindCSS, shadcn/ui
- **Backend**: Node.js (TypeScript) + Express with modular structure, REST + minimal Webhook handlers
- **Database**: PostgreSQL + Prisma ORM, Redis for queues/rate limiting
- **Auth**: JWT-based sessions + refresh tokens, Role-based access control (RBAC)
- **Payments**: Razorpay (primary) + Stripe (optional fallback)
- **Email/SMS/WhatsApp**: SendGrid (email), Twilio SMS, WhatsApp Cloud API (meta) for reminders
- **PDF**: pdfkit or Puppeteer for HTML-to-PDF invoices
- **Jobs/Agent**: BullMQ (Redis) or Agenda for scheduled/queued tasks; Node worker process
- **Infra**: Docker + docker-compose, Nginx reverse proxy, Env via dotenv
- **Testing**: Jest (backend), Playwright (frontend E2E)
- **CI/CD**: GitHub Actions with build, test, lint, docker build

## Prerequisites

- Node.js 18+
- npm / yarn / pnpm / bun
- Docker and Docker Compose (for containerized deployment)
- PostgreSQL (for local development without Docker)
- Redis (for local development without Docker)

## Installation

### Using Docker (Recommended)

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/billing-pro.git
   cd billing-pro
   ```

2. Create a `.env` file based on the `.env.local` template:
   ```bash
   cp .env.local .env
   ```

3. Update the environment variables in the `.env` file with your actual values.

4. Build and start the containers:
   ```bash
   docker-compose up -d
   ```

5. Access the application at http://localhost:8000

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/billing-pro.git
   cd billing-pro
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env.local` file based on the template and update with your values.

4. Start the development server:
   ```bash
   npm run dev
   ```

5. Access the application at http://localhost:8000

## API Documentation

The API documentation is available at http://localhost:8000/api-docs when the server is running.

## Testing

Run the tests with:

```bash
npm test
```

## Deployment

The application can be deployed using Docker Compose:

```bash
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

## License

This project is licensed under the MIT License - see the LICENSE file for details.
