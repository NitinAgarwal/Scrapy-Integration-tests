# pathod dockerfile

FROM ubuntu

MAINTAINER Nitin Agarwal, nitinagarwal3006@gmail.com

ENV http_proxy "http://proxy.iiit.ac.in:8080"

RUN apt-get install -y python-pip python-dev libevent1-dev libxml2-dev libxslt-dev

RUN apt-get install -y -q build-essential

RUN pip install netlib
RUN pip install requests
RUN pip install pathod


# Expose port
EXPOSE 9999		# default port


ENTRYPOINT ["pathod"]

