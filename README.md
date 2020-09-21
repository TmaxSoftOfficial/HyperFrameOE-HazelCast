# HyperFrameOe-Hazelcast

This is a group of Hazelcast Docker files with versions for HyperFrame Open Edition.

### Prerequisites

Docker 19.03.12 (This is a workspace's version, other versions might be compatible with this.)

### Set up Info

1) OS : Debian GNU/Linux 10 (Base OS of openjdk:8 in dockerhub)
2) JDK : Openjdk 8 (build number 252)
2) Hazelcast : Hazelcast 4.0.1

### Directory layout

```bash
${pwd}
|- hazelcast_4.0.1
|   |- Dockerfile                    # Dockerfile
|   |- logging.properties            # Setting for logging
|   |- start-hazelcast.sh            # Shell script to run Hazelcast
-- README.md
```   

### Installing

#### 1. Download the hazelcast_4.0.1 directory.

#### 2. Build an Docker Image.

```bash
$ docker build -t <create image_name>:<image_version> .
```
#### 3. Generate a Container from image.

```bash
$ docker run -e JAVA_OPTS="-Dhazelcast.local.publicAddress=<host_ip>:5701" -p 5701:5701 <image_name>:<image_version>
```
#### 4. See the manual to see the different ways to generate containers.

### License

This project is licensed under the Apache-2.0

### Version History

[HyperFrame OE, Hazelcast 4.0.1](https://github.com/TmaxSoftOfficial/HyperFrameOE-Hazelcast/blob/master/hazelcast_4.0.1/Dockerfile "dockerfile link") (latest)

### HyperFrameOE Service Level

[HyperFrameOE Service Level](https://github.com/TmaxSoftOfficial/HyperFrameOE-About/blob/master/ServiceLevel.md)
