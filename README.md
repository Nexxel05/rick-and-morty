# Rick and Morty

### How to run
- Create venv: `python -m venv venv`
- Activate venv: `venv\Scripts\activate`
- Install requirements: `pip install -r requirements.txt`
- Create new Postgres DB and User
- Copy .env.sample -> .env and populate
- Run migration: `python manage.py migrate`
- Run Redis server: `docker run -d -p 6379:6379 redis`
- Run Celery worker for tasks handling: `celery -A rick_and_morty_api worker --pool=solo -l INFO`
- Run Celery beat for task handling: `celery -A rick_and_morty_api beat -l INFO --scheduler django_celery_beat.schedulers:DatabaseScheduler`
- Create schedule for running sync in DB
- Run app: `python manage.py runserver`