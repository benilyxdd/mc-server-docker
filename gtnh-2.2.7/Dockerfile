FROM ubuntu:latest 

RUN apt-get update
RUN apt-get install openjdk-8-jdk wget unzip screen vim -y

RUN mkdir /server
WORKDIR /server

RUN wget http://downloads.gtnewhorizons.com/ServerPacks/GT_New_Horizons_2.2.7_SERVER.zip
RUN unzip GT_New_Horizons_2.2.7_SERVER.zip
RUN rm GT_New_Horizons_2.2.7_SERVER.zip
COPY mods/* /server/mods/
COPY world/ /server/World
COPY startserver.sh /server/startserver.sh

RUN echo "eula=true" > eula.txt
RUN echo "[{\"uuid\":\"0d9b3b9c-6757-46bb-8005-bfa1acb42171\",\"name\":\"ellowwell\"}]" > whitelist.json
RUN echo "[{\"uuid\":\"0d9b3b9c-6757-46bb-8005-bfa1acb42171\",\"name\":\"ellowwell\",\"level\":2}]" > ops.json

RUN chmod 777 -R /server

EXPOSE 25565
ENTRYPOINT [ "screen", "-mS", "gtnh", "./startserver.sh"]