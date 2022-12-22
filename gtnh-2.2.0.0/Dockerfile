FROM ubuntu:latest 

RUN apt-get update
RUN apt-get install default-jre wget unzip -y

RUN mkdir /server
WORKDIR /server

RUN wget http://downloads.gtnewhorizons.com/ServerPacks/GT_New_Horizons_2.2.7_SERVER.zip
RUN unzip GT_New_Horizons_2.2.7_SERVER.zip
RUN rm GT_New_Horizons_2.2.7_SERVER.zip
RUN echo "eula=true" > eula.txt


RUN chmod 777 -R /server

EXPOSE 25565