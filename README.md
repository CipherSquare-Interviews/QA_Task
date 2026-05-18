# Wallet Recharge App

A mobile recharge and wallet management application built with Laravel, React, and Inertia.js.

## Tech Stack

- **Backend:** Laravel 11
- **Frontend:** React 18
- **Bridge:** Inertia.js
- **Database:** SQLite
- **Styling:** Tailwind CSS
- **Build:** Vite

## Setup Instructions

### Prerequisites

- PHP 8.2+
- Composer
- Node.js 18+
- npm

### Installation

```bash
# Clone the repository
git clone <repo-url> wallet-recharge-app
cd wallet-recharge-app

# Install PHP dependencies
composer install

# Install JS dependencies
npm install

# Create SQLite database
touch database/database.sqlite

# Run migrations and seed data
php artisan migrate --seed

# Start development server
php artisan serve
```

In a separate terminal:
```bash
npm run dev
```

### Access

Open [http://localhost:8000](http://localhost:8000) in your browser.

### Test Credentials

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

The application also exposes API-style endpoints for testing:

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/recharge | Submit a recharge |
| GET | /api/transactions | List transactions |
| GET | /api/transactions/{id} | View single transaction |
| GET | /api/balance | Check wallet balance |

All API endpoints require authentication (session cookie).

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
```
