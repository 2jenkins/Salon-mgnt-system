# Salon Management System

A Django-based salon management starter application with a responsive customer website, service catalogue, appointment booking, customer accounts and staff appointment management.

## Features

- Responsive landing page and searchable service catalogue
- Customer registration, login and logout
- Appointment requests with date/time validation and basic duplicate-slot prevention
- Customer appointment history and cancellation
- Staff dashboard with appointment totals and status updates
- Staff-only service creation, editing and deletion
- Django admin for managing users, services and appointments
- SQLite database for local development; Nairobi timezone defaults

## Run locally

Requires Python 3.10+.

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Open `http://127.0.0.1:8000/`. Sign in to `/admin/` with the superuser account to add salon services and manage the application. The first superuser can use the staff dashboard at `/dashboard/`.

## Important production notes

- Set `DEBUG = False`, configure `ALLOWED_HOSTS`, use a strong environment-provided `SECRET_KEY`, and configure HTTPS/security settings before public deployment.
- Configure a production database and a persistent media-storage service before deployment.
- The current slot check is a simple application-level check; production booking should use transactional locking/constraints appropriate to the salon's scheduling rules.
