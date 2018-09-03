# Docker

Build a basic Docker image which serves a simple app.py

## Build 

docker build -t friendlyhello .

## Run 

docker run -p 4000:80 friendlyhello 

## Run detached mode 

docker run -d -p 4000:80 friendlyhello

## Docker Search and Pull

These two commnds below will allow for searching the docker registry to  download and install the image.

docker search < name >

docker pull < name >

