# Wallet Recharge App

A mobile recharge and wallet management application built with Laravel, React, and Inertia.js.

## Tech Stack

- **Backend:** Laravel 11
- **Frontend:** React 18
- **Bridge:** Inertia.js
- **Database:** SQLite
- **Styling:** Tailwind CSS
- **Build:** Vite
- **Testing:** Playwright

## Quick Start (Docker)

### Prerequisites

- Docker & Docker Compose

### Run the Application

```bash
docker compose up --build
```

The app will be available at [http://localhost:8000](http://localhost:8000)

That's it. No PHP, no Node.js, no Composer required on your machine.

### Reset Database

To reset the database with fresh seed data:
```bash
docker compose down -v
docker compose up --build
```

## Manual Setup (without Docker)

### Prerequisites

- PHP 8.2+
- Composer
- Node.js 18+
- npm

### Installation

```bash
composer install
npm install
touch database/database.sqlite
php artisan migrate --seed
```

Run in two terminals:
```bash
php artisan serve
```
```bash
npm run dev
```

Open [http://localhost:8000](http://localhost:8000)

## Test Credentials

| User | Mobile | Password |
|------|--------|----------|
| Rahul Sharma | 9876543210 | password123 |
| Priya Patel | 9123456789 | password123 |

## Features

- **Login** - Mobile number + password authentication
- **Dashboard** - Wallet balance, recent transactions, quick actions
- **Mobile Recharge** - Recharge any mobile number with operator selection
- **Transaction History** - View all transactions with status filters
- **Profile** - View and edit user profile

## API Endpoints

The application exposes API-style endpoints for testing:

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/recharge | Submit a recharge |
| GET | /api/transactions | List transactions |
| GET | /api/transactions/{id} | View single transaction |
| GET | /api/balance | Check wallet balance |

All API endpoints require authentication (session cookie).

## Running Playwright Tests

### Install Playwright (first time only)

```bash
npm install
npx playwright install chromium
```

### Run Tests

```bash
# Make sure the app is running (docker compose up OR manual setup)

# Run all tests headless
npm test

# Run tests with browser visible
npm run test:headed

# Run tests with Playwright UI
npm run test:ui

# View test report after run
npm run test:report
```

### Writing Tests

Test files are in `tests/e2e/`. Example test files are provided as reference:

- `login.spec.js` - Authentication tests
- `dashboard.spec.js` - Dashboard verification
- `recharge.spec.js` - Recharge flow tests
- `transactions.spec.js` - Transaction history tests
- `profile.spec.js` - Profile management tests

Create new test files in the same directory following the Playwright test format:

```javascript
import { test, expect } from '@playwright/test';

test.describe('Feature Name', () => {
    test('should do something', async ({ page }) => {
        await page.goto('/some-page');
        await expect(page.locator('selector')).toBeVisible();
    });
});
```

## Project Structure

```
app/
  Http/Controllers/    - Request handlers
  Models/              - Eloquent models
config/                - Application configuration
database/
  migrations/          - Database schema
  seeders/             - Test data
resources/
  js/Pages/            - React page components
  js/Layouts/          - Layout components
  views/               - Blade templates
routes/web.php         - Route definitions
tests/e2e/             - Playwright test files
playwright.config.js   - Playwright configuration
docker-compose.yml     - Docker setup
```
