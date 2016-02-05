OpenTripPlanner Docker image
============================

This project contains a Docker image for stable
[OpenTripPlanner](http://opentripplanner.org) releases. It is available from
Docker Hub in the
[`goabout/opentripplanner` repository](https://hub.docker.com/r/goabout/opentripplanner/).
Image tags correspond to OpenTripPlanner versions. The `latest` tag points to
the latest stable release.

## Usage

The `otp` command is available as a shortcut for `java -jar otp.jar`:

    docker run \
        -e JAVA_MX=2G \
        -v $PWD:/data:ro \
        -p 8080:8080 \
        goabout/opentripplanner:0.19.0 \
        otp --build /data --inMemory

After the graph has been built, the planner is available at port 8080.

### Environment variables

**JAVA_MX**: The amount of heap space available to OpenTripPlanner. (The `otp`
             command adds `-Xmx$JAVA_MX` to the `java` command.) Default: 1G
