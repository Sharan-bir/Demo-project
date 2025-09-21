Django Jobs Backend

This is the backend for the Jobs application. Built with Django and Django REST Framework, connected to PostgreSQL, and supports resume uploads.

Features

REST API endpoint to create candidates with:

Name, Address, Skills, GitHub link, Age, Email, Phone number

College Name and Passing Year

Resume upload (PDF/DOC/DOCX)

Validation for email, numeric fields, and resume file type/size

Admin dashboard to manage candidates

Export candidate list to Excel/CSV

CORS enabled for frontend integration

Whitenoise for static file serving

Docker-ready

Prerequisites

Python 3.12+

PostgreSQL

Docker (optional)

Git

Quick Start (Local Development)
1. Clone the repository
git clone https://github.com/yourusername/yourrepo.git
cd yourrepo

2. Create a virtual environment
python -m venv venv
source venv/bin/activate      # Linux/macOS
venv\Scripts\activate         # Windows

3. Install dependencies
pip install --upgrade pip
pip install -r requirements.txt

4. Configure settings.py

Update settings.py with your database and other configurations:

SECRET_KEY = "your-secret-key"
DEBUG = True
ALLOWED_HOSTS = ["127.0.0.1", "localhost"]

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'jobdb',
        'USER': 'jobuser',
        'PASSWORD': 'jobpassword',
        'HOST': 'localhost',
        'PORT': 5432,
    }
}

STATIC_URL = '/static/'
STATIC_ROOT = BASE_DIR / 'staticfiles'

MEDIA_URL = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'

CORS_ALLOWED_ORIGINS = [
    "http://localhost:3000",
]

5. Run migrations
python manage.py makemigrations
python manage.py migrate

6. Create a superuser (for admin)
python manage.py createsuperuser

7. Collect static files
python manage.py collectstatic

8. Start the development server
python manage.py runserver


Your backend is now running at:

http://127.0.0.1:8000/


Admin panel: http://127.0.0.1:8000/admin/

API endpoint: http://127.0.0.1:8000/api/candidates/

Running with Docker (Optional)

Build and start services:

docker-compose up -d --build


Run migrations inside the container:

docker-compose run web python manage.py migrate
docker-compose run web python manage.py createsuperuser


Backend will be available at:

http://localhost:8000/

Notes

Uploaded resumes are stored in the media/ folder.

Static files are served via Whitenoise in production.

Test the API using Postman or the included check.py script.

Make sure your frontend domain is included in CORS_ALLOWED_ORIGINS.

Test API with Python (check.py)
python check.py


This will POST a candidate along with a resume file to /api/candidates/.

License

MIT License