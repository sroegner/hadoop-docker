#Apache Hadoop 2.4.0 Docker image

A few weeks ago we have released an Apache Hadoop 2.3 Docker image - in a very short time this become the most [popular](https://registry.hub.docker.com/search?q=hadoop&s=downloads) Hadoop image in the Docker [registry](https://registry.hub.docker.com/).


Following on the success of our Hadoop 2.3 Docker [image](https://registry.hub.docker.com/u/sequenceiq/hadoop-docker/), the feedbacks and requests we have received and aligning with the Hadoop release cycle, we have released an Apache Hadoop 2.4 Docker image - same as the previous version this is available as a trusted and automated build on the official Docker [registry](https://registry.hub.docker.com/).


# Build the image

In case you'd like to try directly from the Dockerfile you can build the image as:

```
docker build  -t sequenceiq/hadoop-docker .
```
# Pull the image

The image is also released as an official Docker image from Docker's automated build repository - you can always pull or refer the image when launching containers.

```
docker pull sequenceiq/hadoop-docker:2.4.0
```

# Start a container

In order to use the Docker image you have just build or pulled use:

```
docker run -i -t sequenceiq/hadoop-docker /etc/bootstrap.sh -bash
```

## Testing

You can run one of the stock examples:

```
cd $HADOOP_PREFIX
# run the mapreduce
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.4.0.jar grep input output 'dfs[a-z.]+'

# check the output
bin/hdfs dfs -cat output/*
```

## Hadoop native libraries, build, Bintray, etc

The Hadoop build process is no easy task - requires lots of libraries and their right version, protobuf, etc and takes some time - we have simplified all these, made the build and released a 64b version of Hadoop nativelibs on this [Bintray repo](https://bintray.com/sequenceiq/sequenceiq-bin/hadoop-native-64bit/2.4.0/view/files). Enjoy. 


## Automate everything

As we have mentioned previousely, a Docker file was created and released in the official [docker repo](https://registry.hub.docker.com/u/sequenceiq/hadoop-docker/)

