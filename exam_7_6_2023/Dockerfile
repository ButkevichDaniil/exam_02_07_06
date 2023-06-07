FROM ubuntu:latest

LABEL maintainer="Butkevich_Daniil_221_353"

ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update    
RUN apt-get install qt5-default -y    
RUN apt-get install qtbase5-dev -y    
RUN apt-get install qt5-qmake    
RUN apt-get install build-essential -y

EXPOSE 33333

WORKDIR /Butkevich_353
COPY *.cpp /Butkevich_353/
COPY *.h /Butkevich_353/
COPY *.pro /Butkevich_353/
COPY . /Butkevich_353


RUN qmake -o hallServer
RUN make

ENTRYPOINT ["./hallServer"]