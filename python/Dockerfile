###############################################################################
# use an existing docker image 
FROM python:3.7

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

###############################################################################
# download and install dependencies

# GitHub support
# install git
#RUN apk add --update git

# download and instll dependencies (to be able to use netcat)
RUN echo 'deb [check-valid-until=no] http://archive.debian.org/debian jessie-backports main' >> /etc/apt/sources.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends apt-utils \
    && apt-get install dos2unix

# update pip
RUN pip install --upgrade pip

# install the needed packages
RUN pip install --no-cache-dir -r requirements.txt

###############################################################################
#set up the environment
#CMD ["./wait_for_services.sh"]

#docker build -t pascalhubacher/python:latest .
#docker run -it pascalhubacher/python-1 bash
