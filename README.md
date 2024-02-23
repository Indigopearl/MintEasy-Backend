# **MintEasy-Backend Installation Guide (Local Machine - Backend Only)**

**Important Note:** This guide covers the installation of the **MintEasy-Backend** project on a **local machine**. It provides the necessary steps to run the backend functionality independently. Please be aware that this guide **does not** include installation instructions for the frontend or deployment on a server.

**Prerequisites:**

* Python 3.9
* Git
* PostgreSQL

---

## Project Setup

### Clone the Project

```bash
git clone <project_repository_url>
```

### Update the Project

```bash
git pull
```

---

## Virtual Environment

### Create Virtual Environment in our Project Directory

```bash
python -m venv .venv
```

### Activate Virtual Environment

```bash
source .venv/bin/activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

## .venv Configuration

* Create a .env file in the project directory (where manage.py is located).
* Add the following configuration to .env:

```bash
#Django

DJANGO_SECRET_KEY = '[your_Django_secret_key]'

# postgresql

DB_NAME=[your_database_name]
DB_USER=[your_database_username]
DB_PASSWORD=[your_database_password]
DB_HOST=localhost
DB_PORT=5432

# email confirmation

EMAIL_HOST = '[your_email_host]'
EMAIL_HOST_PASSWORD = '[your_email_host_password]'
EMAIL_HOST_USER = '[your_email_host_user]'
DEFAULT_FROM_EMAIL = '[your_email_adrress]'
SERVER_EMAIL = '[your_server_email]'

# twelvedata API

API_KEY = '[your_api_key]'

```

---

## Database Setup

* Run the following command to access the PostgreSQL command line client as the postgres user:

```bash
sudo -u postgres psql
```

* Once you are in the PostgreSQL command line client, you should see a prompt that looks like this:

`postgres=#`

* Now, you can create the projectx database by entering the following SQL command:

```bash
CREATE DATABASE projectx;
```

After running this command, you should see a confirmation message.

* Exit the PostgreSQL command line client by typing:

```bash
\q
```

* Run migrations:

```bash
python manage.py makemigrations
```

```bash
python manage.py migrate
```

Now your project is set up and ready to run!
