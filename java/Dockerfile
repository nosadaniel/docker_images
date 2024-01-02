#use java sdk image for compilation
FROM openjdk:8-jdk-alpine AS builder
#create directory inside the container
WORKDIR /out
#copy from directory all .java files inside the container
COPY *.java .

#compile source code
RUN javac Hello.java

#create a lightweight image
FROM openjdk:8-jre-alpine
#copy compiled artifacts from previous image
COPY --from=builder /out/*.class .

CMD [ "java","Hello"]