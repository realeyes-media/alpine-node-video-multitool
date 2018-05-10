# alpine-node-video-multitool
An Alpine image with Node, Yarn, Bento, PM2, FFMPEG, GlibC, Oracle Java

# How to build 
* Download server-jre-8u172-linux-x64.tar (replacing the numbers with MAJORuMINOR for whatever version is needed) into root
* Update the Dockerfile with new Major/Minor versions (ignore build number, as we aren't using it)
* docker login quay.io
* docker build -t quay.io/realeyes/alpine-node-video-multitool .
* docker push quay.io/realeyes/alpine-node-video-multitool

# Explaination 
Oracle Java is a pain to download programmatically due to the licence acceptance process - it's possible to pretent the cookie with curl or wget, but downloading the file this way mangles the installer. Thus, you will need to download the server-jre-*-x64.tar.gz manually from Oracle into the build directory, and set the ENV at the top of the Dockerfile to match the version you downloaded. 

# References
https://github.com/anapsix/docker-alpine-java
mhart/node8
