FROM tensorflow/tensorflow:latest-gpu

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git 
RUN git clone https://github.com/kanghj/nmt 
WORKDIR "nmt"
RUN git checkout blah1
RUN mkdir data
RUN mkdir log
COPY data data
COPY run.sh run.sh
RUN touch abc.txt

