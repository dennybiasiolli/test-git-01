# test-git-01

Minimal Django 6 project scaffolded with [uv](https://docs.astral.sh/uv/) for Python dependency and environment management.

## Stack

| Component | Version / tool |
|-----------|----------------|
| Python | 3.14+ |
| Django | 6.0+ |
| Package manager | [uv](https://docs.astral.sh/uv/) |

Project settings and URL configuration live in the `config/` package (`settings.py`, `urls.py`, `wsgi.py`, `asgi.py`). `manage.py` is the Django management entry point.

## Prerequisites

- [uv](https://docs.astral.sh/uv/getting-started/installation/) installed
- Python 3.14+ (uv can install it if missing)

## Setup

Clone the repository and install dependencies:

```bash
git clone git@github.com:dennybiasiolli/test-git-01.git
cd test-git-01
uv sync
```

This creates a virtual environment in `.venv` and installs Django and its dependencies from `uv.lock`.

## Common commands

All commands run through `uv run` so they use the project environment:

```bash
# Run system checks
uv run python manage.py check

# Apply database migrations (creates db.sqlite3 by default)
uv run python manage.py migrate

# Start the development server (http://127.0.0.1:8000/)
uv run python manage.py runserver

# Create a superuser for the admin site
uv run python manage.py createsuperuser

# Open the Django shell
uv run python manage.py shell
```

## Adding dependencies

```bash
uv add <package-name>
```

To add a development-only dependency:

```bash
uv add --dev <package-name>
```

## Project layout

```
test-git-01/
├── config/           # Django project package
│   ├── settings.py   # Project settings
│   ├── urls.py       # Root URL configuration
│   ├── wsgi.py       # WSGI entry point
│   └── asgi.py       # ASGI entry point
├── manage.py         # Django CLI
├── pyproject.toml    # Project metadata and dependencies
├── uv.lock           # Locked dependency versions
└── .python-version   # Python version pin for uv
```

## License

This project is licensed under the [Apache License 2.0](LICENSE).
