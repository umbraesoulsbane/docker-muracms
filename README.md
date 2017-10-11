# Mura CMS Dockerfiles

The [Docker](https://www.docker.com/) files in this repository may be used to create your own custom Docker container for running [Mura CMS](http://www.getmura.com/). For Docker images, visit the Docker repository at https://hub.docker.com/r/stevewithington/docker-muracms/.

**NOTE:** The example files and Docker images are provided as learning tools only. They are *NOT* intended for production purposes. That said, you could easily use the information as a basis for creating your own custom Docker images for integration into your team's workflow.

# Tags
* `:latest`, `:7.1-blueriver-lucee5` ([Dockerfile](https://github.com/stevewithington/docker-muracms/blob/master/image-build-files/blueriver-lucee5/Dockerfile))
    * Uses a slightly [customized version of Lucee](https://hub.docker.com/r/blueriver/lucee/) as the base Docker image.
* `:7.1-commandbox-lucee5` ([Dockerfile](https://github.com/stevewithington/docker-muracms/blob/master/image-build-files/commandbox-lucee5/Dockerfile))
    * Uses the [`:lucee5` CommandBox Docker image](https://hub.docker.com/r/ortussolutions/commandbox/) as the base image.
* `:7.1-commandbox-adobe2016` ([Dockerfile](https://github.com/stevewithington/docker-muracms/blob/master/image-build-files/adobe2016/Dockerfile))
    * Uses the [`:adobe2016` CommandBox Docker image](https://hub.docker.com/r/ortussolutions/commandbox/) as the base image.

# Description
The Docker images and files included here are for developers to use as they consider options for integrating Docker & Mura CMS into their workflow. 

Primary thoughts to consider when implementing Docker and Mura CMS into your workflow include:

* Which CFML engine do you want to use? [Adoble ColdFusion](http://www.adobe.com/products/coldfusion-family.html)? Or [Lucee](http://lucee.org/)?
* Do you want to use one of the convenient [Commandbox](https://hub.docker.com/r/ortussolutions/commandbox/) images for your desired CFML engine, or roll your own?
* Which database engine do you wish to use? [MySQL](https://hub.docker.com/_/mysql/), [Postgres](https://hub.docker.com/_/postgres/), or [Microsoft SQL Server](https://hub.docker.com/r/microsoft/mssql-server-linux/)?
* Do you want to be able to modify Mura CMS core files, and only abstract the CFML engine? (*Rare*)
* Do you want to abstract Mura CMS core files, and simply have them included in the image itself? (*Common*)
* If abstracting Mura CMS core files, do you want to be able to modify `modules`, `plugins`, `sites`, and/or `themes`? (*Common*)

Once you have the answers to these questions, you will be able to better select the appropriate Docker image, and `docker-compose` files to use. That said, feel free to play around with all of the included examples.

# Usage & Examples
While some users visiting this repository may have a strong understanding of Docker, and how it works, there are likely others who are completely new to Docker, and don't know where to start. 

If you're completely new to Docker, the [Docker Documentation](https://docs.docker.com/) area is a tremendous resource. You will also find the [Udemy](https://www.udemy.com) course titled "[Docker Mastery: The Complete Toolset From a Docker Captain](https://www.udemy.com/docker-mastery/) extremely helpful in getting you up to speed rather quickly.

*The following information assumes you have a copy of the [**docker-muracms** Github repository](https://github.com/stevewithington/docker-muracms) on your local machine.*

## Building Your Own Images
* To build your own images, you may use one of the `Dockerfile` and `docker-compose.yml` files located under the [`image-build-files`](https://github.com/stevewithington/docker-muracms/blob/master/image-build-files/) section.
* Modify the `Dockerfile` and/or `docker-compose.yml` file as desired, then build your image.

## Examples
Examples are located under https://github.com/stevewithington/docker-muracms/tree/master/examples. Each example contains a `docker-compose.yml` file. Using your terminal, you may `cd` into the desired example directory, and then issue the `$ docker-compose up` command. 

Unless you've modified any of the `docker-compose.yml` files, the information outlined below for each example should be correct. Feel free to inspect the `docker-compose.yml` files to confirm, and/or to modify as desired.

* **blueriver-lucee5-mysql**
    * Domain: http://localhost:8111
        * Usr: `admin`
        * Pwd: `admin`
    * Domain: http://localhost:5111
        * Usr: `root`
        * Pwd: `5trongP@55w0rd`
* **commandbox-lucee5-mssql**
    * Domain: http://localhost:8003
        * Usr: `admin`
        * Pwd: `admin`
    * Domain: http://localhost:5003
        * Usr: `sa`
        * Pwd: `5trongP@55w0rd`
* **blueriver-lucee5-mysql**
    * Domain: http://localhost:8001
        * Usr: `admin`
        * Pwd: `admin`
    * Domain: http://localhost:5001
        * Usr: `root`
        * Pwd: `5trongP@55w0rd`
* **blueriver-lucee5-postgres**
    * Host Domain: http://localhost:8002
        * Usr: `admin`
        * Pwd: `admin`
    * Host Domain: http://localhost:5002
        * Usr: `muradb`
        * Pwd: `5trongP@55w0rd`

# Issues
Please submit issues to https://github.com/stevewithington/docker-muracms/issues

# License
Apache License, Version 2.0