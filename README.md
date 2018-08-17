# Docker

Build a basic Docker image which serves a simple app.py

## Build 

docker build -t friendlyhello .

## Run 

docker run -p 4000:80 friendlyhello 

## Run detached mode 

11 docker run -d -p 4000:80 friendlyhello
