FROM openjdk

MAINTAINER mukki

#plugins

RUN apt-get -y update

RUN apt-get -y upgrade

RUN apt-get -y install openssl git nano
RUN apt-get -y install maven

RUN git clone -b develop https://github.com/apache/incubator-rocketmq.git

RUN cd incubator-rocketmq

RUN cd incubator-rocketmq

WORKDIR /incubator-rocketmq

RUN mvn -Prelease-all -DskipTests clean install -U

WORKDIR /incubator-rocketmq/distribution/target/apache-rocketmq/bin
ADD runbroker.sh /incubator-rocketmq/distribution/target/apache-rocketmq/bin
 
RUN chmod a+x mqnamesrv

RUN chmod a+x mqbroker

EXPOSE 9876

ENTRYPOINT ./mqbroker && sleep 3600

