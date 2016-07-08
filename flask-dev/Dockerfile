#
# ubuntu machine w python3 and flask with capability
# to launch web browser
# for web development.
#

FROM zgazak/flask-base

MAINTAINER jzgazak@gmail.com
RUN pip3 install git+https://github.com/zgazak/python-instagram
RUN pip3 install pygal

USER root

# Configure container startup as root
EXPOSE 5000
EXPOSE 8000
ENV PYTHONPATH=/usr/local/bin/
