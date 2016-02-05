Go About Docker OpenTripplanner image
=====================================

This project contains a Docker image for stable
[OpenTripplanner](http://opentripplanner.org) releases.

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

**JAVA_MX**: The amount of heap space available to OpenTripplanner. The `otp`
             command adds `-Xmx$JAVA_MX` to the `java` command. Default: 1G
