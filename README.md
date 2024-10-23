# ecommerce_backend_api
This Django-based e-commerce backend uses MongoDB and JWT authentication. It includes product management, categories, user profiles, and cart functionality. Secure user authentication, dynamic product listings, and cart management allow for building scalable, real-world e-commerce platforms similar to Amazon.
# Django E-Commerce Microservice
This project is a Django-based e-commerce backend microservice using MongoDB as the database and JWT (JSON Web Token) for user authentication. The system provides functionalities such as product management, product categories, user profiles, and cart management.

# Features
JWT Authentication: Secure user login and token-based access control.
Product Management: Create, read, update, and delete products.
Categories: Products organized by categories.
User Profiles: Custom user profile management, including addresses and phone numbers.
Cart Management: Add, view, and remove products from the cart.
Scalable Architecture: Microservice design using Django, suitable for large e-commerce platforms.
Installation
Prerequisites
Python 3.8+ installed.
MongoDB server running.
Django and Django REST framework installed.
JWT package for authentication.
Install required packages 
# 1. Clone the Repository
git clone https://github.com/Yaaseen-Basit/ecommerce-django-microservice.git
cd ecommerce-django-microservice
# 2. Create and Activate Virtual Environment
python -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
# 3. Install Dependencies
pip install -r requirements.txt
# 4. Install MongoDB Engine
pip install djongo
# 5. Setup Environment Variables
Create a .env file in the root folder and define the following:
SECRET_KEY=<your_django_secret_key>
MONGO_DB_NAME=<your_mongo_db_name>
JWT_SECRET_KEY=<your_jwt_secret_key>
# 6. Run Database Migrations
python manage.py makemigrations
python manage.py migrate
# Configuration
# 1. MongoDB Connection
Ensure that MongoDB is running on your local machine or server. Configure the connection in settings.py:
DATABASES = {
    'default': {
        'ENGINE': 'djongo',
        'NAME': os.getenv('MONGO_DB_NAME'),
    }
}
# 2. JWT Authentication
Ensure the following settings for authentication:
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
'rest_framework_simplejwt.authentication.JWTAuthentication',
],
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ],
}

# Running the Application
1. Create Superuser
To access the Django admin panel:
python manage.py createsuperuser
# 2. Start the Development Server
python manage.py runserver
Navigate to http://127.0.0.1:8000/admin to manage the e-commerce platform via the admin interface.





