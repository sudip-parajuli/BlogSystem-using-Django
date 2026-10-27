# Django Blog System

A learning application for publishing posts with user accounts and author
profiles. Built while practicing Django's authentication, forms, templates,
generic views and model relationships.

## Features

- Post lists and individual post pages.
- Account registration, login/logout and profile editing.
- Authenticated post creation with the current user assigned as author.
- Author ownership checks for post updates and deletion.
- Profile information and template-based presentation.

## Run locally

Use Python 3.11 and an isolated virtual environment. The repository's requirements
record the original Django 5.1-era environment.

```sh
python -m venv .venv
```

Activate `.venv\Scripts\Activate.ps1` in PowerShell or
`source .venv/bin/activate` on macOS/Linux, then:

```sh
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Before starting locally, add `localhost` and `127.0.0.1` to
`ALLOWED_HOSTS` in `blog_system/settings.py`; the checked-in list contains only
historical deployment domains.

Without `DATABASE_URL`, settings use local SQLite. If `DATABASE_URL` is present,
the application connects to that database instead; use a disposable development
database when experimenting. The dependency file includes PostgreSQL tooling,
which may require local build prerequisites on some systems.

## Structure

| Path | Responsibility |
| --- | --- |
| `blog/` | Post models, views, templates and static styling |
| `users/` | Registration, profiles, forms and account views |
| `blog_system/` | Django settings and root routes |
| `requirements.txt`, `Procfile` | Original dependencies and server entry point |

## Current status

This repository preserves an early learning project. Existing test files are
scaffolding rather than a full regression suite. Dependency upgrades, generated
file cleanup, environment-based settings and deployment verification are still
needed before using it as an internet-facing service. Any historical deployment
hostnames in settings are not a guarantee of an active demo.
