![Apache MiNiFi logo](https://nifi.apache.org/assets/images/minifi/minifi-logo.svg "Apache MiNiFi")
# Apache MiNiFi for Docker
## Version 0.4.0

Provides a Dockerfile and associated scripts for configuring an instance of [Apache MiNiFi](https://nifi.apache.org/minifi/).

## Sample Usage:

From your checkout directory:

### MiNiFi

1. Build the image

        VERSION=0.4.0
        cd ${VERSION}
        docker build --build-arg VERSION=${VERSION} -t minifi:${VERSION} .
		
2. Run the image

        VERSION=0.4.0
        docker run --rm -v /path/to/config.yml:/opt/minifi/conf/config.yml minifi:${VERSION}

### MiNiFi Toolkit

1. Build the image

        VERSION=0.4.0
        cd ${VERSION}/toolkit
        docker build --build-arg VERSION=${VERSION} -t minifi-toolkit:${VERSION} .
		
2. Run the image

        VERSION=0.4.0
        docker run --rm -ti -v /path/to/data/:/data/ minifi:${VERSION} sh