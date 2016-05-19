#
# ubuntu machine w python3 and flask with capability
# to launch web browser
# for web development.
#

FROM ubuntu:14.04

MAINTAINER jzgazak@gmail.com

USER root

# Install all OS dependencies for fully functional notebook server and firefox
ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update && apt-get install -yq --no-install-recommends \
    git \
    vim \
    wget \
    build-essential \
    python3 \
    python3-dev \
    python3-pip \
    ca-certificates \
    bzip2 \
    unzip \
    libsm6 \
    pandoc \
    texlive-latex-base \
    texlive-latex-extra \
    texlive-fonts-extra \
    texlive-fonts-recommended \
    texlive-generic-recommended \
    sudo \
    locales \
    libxrender1 \
    firefox \
    dbus dbus-x11 \
    python3-lxml libxml2-dev libxslt-dev python-dev lib32z1-dev \
    nginx \
    && apt-get clean

RUN pip3 install --upgrade pip

RUN pip3 install pdb sqlalchemy_utils google-api-python-client \
    gspread flask Flask-Login Flask-SQLAlchemy==1.0 \
    requests-oauthlib bleach six lxml \
    pandas numpy sqlalchemy

RUN apt-get install -yq --no-install-recommends \
    uwsgi-core \
    uwsgi-plugin-python


RUN apt-get update \
    && apt-get install -y libpq-dev \
    && apt-get install -y python-openssl \
    && apt-get install -y libffi-dev

RUN pip3 install psycopg2 WTForms-Alchemy Flask-WTF WTForms

RUN pip3 install python-instagram

USER root

# Configure container startup as root
EXPOSE 5000
EXPOSE 8000
ENV PYTHONPATH=/usr/local/bin/
