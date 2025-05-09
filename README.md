# FitCheck: Your AI-Powered Health Companion

**FitCheck** redefines the Gen Z phrase "fit check"—from fashion flex to daily wellness check. This AI-driven web application provides a holistic view of your health, integrating nutrition, fitness, hydration, sleep, mood, and body tracking features into one seamless experience.

---
## Video Demo

https://github.com/user-attachments/assets/4cc1a2b8-b219-4107-bd33-8de60f918d6e

🎥 **This demo shows a quick run-through of the FitCheck web application, with a focus on the Food Analysis feature I developed.** It showcases the integration of three AI models:
- **ResNet18** for food classification from images,
- **MistralAI** for generating concise food descriptions,
- **GPT-3.5** for suggesting nutritional alternatives based on detected allergens or health risks.

## Project Description

FitCheck is a personal health companion that leverages image recognition, AI analysis, and smart recommendations to help users take charge of their wellness journey.

From analyzing your meals using a single photo, to generating tailored meal plans and tracking your fitness, FitCheck is built to assist users in forming healthy habits—anytime, anywhere, for free.

---

## Key Features

### User Profile Management
- Collects user info (with consent) for tailored suggestions.
- Limits features if consent is not provided.

### AI Food Analysis
- Upload meal images for AI-driven classification.
- View nutritional facts per 100g: calories, protein, carbs, fats, sugar, fiber, sodium.
- Auto-detect ingredients & allergens.
- Suggests healthy alternatives using GPT-3.5.
- AI-generated food descriptions (via MistralAI).

### Personalized Meal Planning
- Custom plans based on dietary needs, allergies, and goals.
- Includes recipes and ingredient lists.

### Hydration Tracker
- Sends reminders based on intake goal, container size, and user schedule.
- Fully configurable and optional.

### Fitness Planning
- Recommends workouts (aerobic/anaerobic) to burn analyzed food calories.
- Guides calorie deficit planning and intermittent fasting.
- Tracks fasting progress and adherence.

### Wellness Tracking
- **BMI Tracker**: Color-coded healthy weight categories.
- **Mood Tracker**: Select mood & write notes.
- **Sleep Tracker**: Input sleep/wake times to track hours.

---

## INSTALLATION

1. Follow the CSCI 40 slideset on how to setup a virtual environment and install 
the necessary dependencies (Django, dotenv, etc.). This is just archived in Canvas.

2. When installing dependencies, **be sure to include psycopg2-binary.** (pip install psycopg2-binary)
This is necessary for getting PostgreSQL to work.

3. Instead of doing startproject, **clone this repo into the virtual environment folder.** Don't forget to do the necessary steps for making the .env file. Secret Key will be pinned in the group chat.

4. To add your section, **make an app.** This means there should only be 5 apps in total.

## RUNNING THE SERVER

1. If on a fresh install, run the fitcheck-setup.sql in postgres using the command:

        psql -U user_name -d postgres
        \i fitcheck-setup.sql
    
    Note that this **deletes** the database and all data inside it. This is also configured such that the postgres user is just named "postgres", so make the necessary changes both in the file and in settings.py.

3. Make migrations for **each app.**

        python manage.py makemigrations UserProfile
        python manage.py makemigrations FoodAnalysis
        python manage.py makemigrations FitnessPlanning
        python manage.py makemigrations NutritionGuidance
        python manage.py makemigrations [wellnesstracker]
    Doing only makemigrations outputs no changes detected, and even I'm unsure why. You can run a normal makemigrations afterwards just to be sure.

4. Migrate, then run the fitcheck-populate.sql file inside postgres.

        python manage.py migrate
        [IN POSTGRES]
        \i fitcheck-populate.sql
5. Run the server.

        python manage.py runserver


Additional resources:
[Complete Tutorial: Set-up PostgreSQL Database with Django Application](https://medium.com/django-unleashed/complete-tutorial-set-up-postgresql-database-with-django-application-d9e789ffa384)

If any errors arise, feel free to message the group chat.

Thank you, and here's to (as close to) no errors or bugs!


## INSTALLATION

1. Follow the CSCI 40 slideset on how to setup a virtual environment and install 
the necessary dependencies (Django, dotenv, etc.). This is just archived in Canvas.

2. When installing dependencies, **be sure to include psycopg2-binary.** (pip install psycopg2-binary)
This is necessary for getting PostgreSQL to work.

3. Instead of doing startproject, **clone this repo into the virtual environment folder.** Don't forget to do the necessary steps for making the .env file. Secret Key will be pinned in the group chat.

4. To add your section, **make an app.** This means there should only be 5 apps in total.

## RUNNING THE SERVER

1. If on a fresh install, run the fitcheck-setup.sql in postgres using the command:

        psql -U user_name -d postgres
        \i fitcheck-setup.sql
    
    Note that this **deletes** the database and all data inside it. This is also configured such that the postgres user is just named "postgres", so make the necessary changes both in the file and in settings.py.

3. Make migrations for **each app.**

        python manage.py makemigrations UserProfile
        python manage.py makemigrations FoodAnalysis
        python manage.py makemigrations FitnessPlanning
        python manage.py makemigrations NutritionGuidance
        python manage.py makemigrations [wellnesstracker]
    Doing only makemigrations outputs no changes detected, and even I'm unsure why. You can run a normal makemigrations afterwards just to be sure.

4. Migrate, then run the fitcheck-populate.sql file inside postgres.

        python manage.py migrate
        [IN POSTGRES]
        \i fitcheck-populate.sql
5. Run the server.

        python manage.py runserver


Additional resources:
[Complete Tutorial: Set-up PostgreSQL Database with Django Application](https://medium.com/django-unleashed/complete-tutorial-set-up-postgresql-database-with-django-application-d9e789ffa384)

If any errors arise, feel free to message the creator.

Special thanks to my team Barbie Barrion, Ysaac Mesa, Ian Ferol, and Paolo Ong for implementing other features.

Thank you, and here's to (as close to) no errors or bugs!
