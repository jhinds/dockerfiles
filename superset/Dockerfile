FROM ubuntu:16.04

# Official Installation Docs https://superset.incubator.apache.org/installation.html

RUN apt-get update && apt-get install -y build-essential \
    libssl-dev \
    libffi-dev \
    python-dev \
    python-pip \
    libsasl2-dev \
    libldap2-dev

# Install superset & db drivers
RUN pip install superset \
    psycopg2 \
    superset \
    sqlalchemy-redshift \
    sqlalchemy-vertica-python

ARG username=admin
ARG lastname=user
ARG firstname=admin
ARG email=admin@fab.org
ARG password=defnotmypassword

# Create an admin user (you will be prompted to set username, first and last name before setting a password)
RUN fabmanager create-admin --app superset \
    --username $username \
    --firstname $firstname \
    --lastname $lastname \
    --email $email \
    --password $password

# Initialize the database
RUN superset db upgrade

# Load some data to play with
RUN superset load_examples

# Create default roles and permissions
RUN superset init

# Start the web server on port 8088, use -p to bind to another port
CMD ["superset", "runserver"]
