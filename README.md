# Contents

- [Installing and Running](#installing-and-running)
  * [Installing Server and Web Application](#installing-server-and-web-application)
    + [Non-Docker Installation](#non-docker-installation)
  * [Installing the Android Application](#installing-the-android-application)
    + [Non-apk Installation](#non-apk-installation)
  * [Notes](#notes)

# Installing and Running

This document will walk you through installing and running the various software modules for this work.

It assumes that you have a working version of Docker and Docker Compose running on your machine. To learn more, please visit [Docker's Installation Guide](https://docs.docker.com/engine/install/) and [Docker Compose's Installation Guide](https://docs.docker.com/compose/install/)

Moreover, it assumes you are running on a linux distribution. While this is not a requirement, it is advised.

# Installing Server and Web Application

The Server module will contain a REST API, available at `http://localhost:4683` by default. If you want to change this port, you need to edit its references in the `Dockerfile` and `docker-compose.yml`. You can find these files under the `server` folder. Similarly, the Web Application (named *client*), will be available at `http://localhost:3000`.

Before starting, make sure no processes are running on at ports `3000`, `4683`, and `27017`. 

If you have installed `npm` on your machine, you can kill all processes running on these ports by using the following:
```zsh
npx kill-port 3000 4683 27017
```

The installation is fairly straightforward. Assuming you have installed Docker an Docker Compose, run the following command from the root folder of the project.

```zsh
docker-compose up
``` 

The process might take a while. Please wait for the client to be run.

## Non-Docker Installation

If you cannot install Docker or Docker Compose, or prefer not to, installation guides are available at `server/README.md` and `client/README.md`. These installations will require `Node.js`, `npm`, and `MongoDB`.


# Installing the Android Application

The Android Application can be installed using the `app.apk` package, which can be manually installed on an Android Device. [This article from thecustomdroid](https://www.thecustomdroid.com/how-to-install-apk-on-android/) walks through the process in detail.



## Non-apk Installation

In order to install the Android Application without the use of an `apk` file, you'll need to install [Android Studio](https://developer.android.com/studio/install) and follow the steps described in the [official documentation](https://developer.android.com/studio/run).



# Notes

The Mobile Application needs to connect to the Server. In order to do so, it needs to have direct access to it through the network This can be achieved by connecting the Android Device to the same network where the Server is running on. Assuming there is no restriction, the app will connect to the API.

You can change the IP and port of the Server by clicking on the spanner symbol on the top right corner of the application. This button will open the settings of the application, from which you can change the API URL by typing it and clicking "Save"
