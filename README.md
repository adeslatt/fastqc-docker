[![Docker Image CI](https://github.com/adeslatt/fastqc-docker/actions/workflows/docker-image.yml/badge.svg)](https://github.com/adeslatt/fastqc-docker/actions/workflows/docker-image.yml)
# fastqc-docker
Build a Container for bioconda fastqc

Steps to build this docker container.
1. Look up on [anaconda](https://anaconda.org/) the tool you wish to install
2. create an `environment.yml` file either manually or automatically
3. Use the template `Dockerfile` modifying if necessary (in our case we have no custom files for the `src` directory so we do not use that)
4. Build the Docker Image
5. Set up GitHub Actions

To build your image from the command line:
* Can do this on [Google shell](https://shell.cloud.google.com) - docker is installed and available

```bash
docker build -t fastqc .
```

To test this tool from the command line 

Set up an environment variable capturing your current command line:
```bash
PWD=$(pwd)
```

Then mount and use your current directory and call the tool now encapsulated within the environment.
```bash
docker run -it -v $PWD:$PWD -w $PWD fastqc fastqc -h
