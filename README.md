# HyperFrameOE-Hazelcast

This is a group of Hazelcast Docker files with versions for HyperFrame Open Edition.

## Prerequisites

Docker 19.03.12 (This is a workspace's version, other versions might be compatible with this.)

## Requirements

#### 1) OS: Debian GNU/Linux 10 (Base OS of openjdk:8 in dockerhub)
#### 2) JDK: Openjdk 8 (build number 252)
#### 3) Hazelcast: Hazelcast 4.0.1

## Directory layout

```bash
${pwd}
|- hazelcast_4.0.1
|   |- Dockerfile                    # Dockerfile
|   |- logging.properties            # Setting for logging
|   |- start-hazelcast.sh            # Shell script to run Hazelcast
-- README.md
```   

## Installation Steps:

### You can choose one of the following two installation methods.

### Method 1. Using Dockerfile and binary downloaded from GitHub

#### 1. Go to the following site: https://github.com/TmaxSoftOfficial/HyperFrameOE-Hazelcast.

#### 2. Download the Dockerfile and binary.

#### 3. To change the configuration, modify files under the conf directory.

#### 4. Place the Dockerfile and start.sh files and the conf, license, and ssl directories in the same path.

#### 5. Build a Docker Image.
```bash
$ docker build -t <create image_name>:<image_version> .
```

#### 6. Generate a Container from the Image.
```bash
$ docker run -d -p 5701:5701 <image_name>:<image_version>
```




### Method 2. Using Image of Docker Hub

#### 1. Search for the Image.
- It can be searched from Docker Hub (https://hub.docker.com/repository/docker/tmaxsoftofficial/hyperframeoe-hazelcast) or with the following docker search command.
```bash 
$ docker search hyperframeoe-hazelcast
```

#### 2. Pull the Image.
```bash
$ docker pull tmaxsoftofficial/hyperframeoe-hazelcast:latest
```

#### 3. Build a Docker Image.
```bash
$ docker build -t tmaxsoftofficial/hyperframeoe-hazelcast:latest .
```

#### 4. Generate a Container from the Image.
```bash
$ docker run -d -p 5701:5701 tmaxsoftofficial/hyperframeoe-hazelcast:latest
```

## License

Projects are licensed under the Apache 2.0 license. See the [License](https://github.com/TmaxSoftOfficial/HyperFrameOE-Apache/blob/master/apache_2.4/license/license.dat) file.

## Version History

[HyperFrame OE, Hazelcast 4.0.1](https://github.com/TmaxSoftOfficial/HyperFrameOE-Hazelcast/blob/master/hazelcast_4.0.1/Dockerfile "dockerfile link") (latest)

## HyperFrameOE Service Level

[HyperFrameOE Service Level](https://github.com/TmaxSoftOfficial/HyperFrameOE-About/blob/master/ServiceLevel.md)















