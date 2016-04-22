FROM java:8

MAINTAINER Go About <tech@goabout.com>

ENV VERSION=0.19.0 \
    JAVA_MX=1G

ADD https://s3.amazonaws.com/maven.conveyal.com/org/opentripplanner/otp/$VERSION/otp-$VERSION-shaded.jar /usr/local/share/java/
RUN ln -s otp-$VERSION-shaded.jar /usr/local/share/java/otp.jar

COPY otp /usr/local/bin/
RUN chmod 755 /usr/local/bin/*

EXPOSE 8080
