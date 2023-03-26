FROM ubuntu:16.04 AS app
LABEL stage=build

# install required tools
RUN apt-get update 
RUN    apt-get install -y openjdk-8-jdk 
RUN    apt-get install -y maven 
RUN    apt-get install -f libpng16-16 
RUN    apt-get install -f libjasper1 
RUN    apt-get install -f libdc1394-22 

# install project
RUN git clone https://github.com/barais/TPDockerSampleApp 
RUN cd TPDockerSampleApp 
RUN mvn install:install-file -Dfile=./lib/opencv-3410.jar \
    -DgroupId=org.opencv  -DartifactId=opencv -Dversion=3.4.10 -Dpackaging=jar 

# compile & execute the project       
RUN mvn package
RUN java -Djava.library.path=lib/ubuntuupperthan18/ -jar target/fatjar-0.0.1-SNAPSHOT.jar

# RUN      java -Djava.library.path=lib/ubuntuupperthan18/ -jar target/fatjar-0.0.1-SNAPSHOT.jar

ENTRYPOINT java -jar target/fatjar-0.0.1-SNAPSHOT.jar