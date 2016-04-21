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
    python-dev \
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


#RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
#    locale-gen
## fix issues with firefox location
RUN apt-get purge locales -y \
    && apt-get install -y locales \ 
    && locale-gen  en_US.UTF-8 \
    && locale-gen  en en_US  en_US.UTF-8 \
    && dpkg-reconfigure locales 

## fix dbus issue 
RUN dbus-uuidgen > /var/lib/dbus/machine-id

# Configure environment
ENV SHELL /bin/bash
ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US.UTF-8

RUN pip install --upgrade pip

RUN pip install pdb sqlalchemy_utils google-api-python-client \
    gspread flask Flask-Login Flask-SQLAlchemy==1.0 \
    requests-oauthlib bleach six lxml \
    pandas numpy sqlalchemy psycopg2 \

sudo apt-get install uwsgi-core uwsgi-plugin-python

USER root

# Configure container startup as root
EXPOSE 5000
ENV PYTHONPATH=/usr/local/bin/

