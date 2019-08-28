# Answers to questions in week 1


## 1.1

`$ docker ps -a`
`CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS               NAMES
53bc613622f1        nginx               "nginx -g 'daemon of…"   2 minutes ago       Exited (0) 18 seconds ago                       naughty_mclean
bbd5fad9f92d        nginx               "nginx -g 'daemon of…"   2 minutes ago       Exited (0) 5 seconds ago                        hungry_goodall
ab6a64490a4e        nginx               "nginx -g 'daemon of…"   2 minutes ago       Up 2 minutes                80/tcp              clever_meitner`


## 1.2 

`
$ docker ps -a`
`CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                          PORTS               NAMES
53bc613622f1        nginx               "nginx -g 'daemon of…"   3 minutes ago       Exited (0) About a minute ago                       naughty_mclean
bbd5fad9f92d        nginx               "nginx -g 'daemon of…"   3 minutes ago       Exited (0) About a minute ago                       hungry_goodall
ab6a64490a4e        nginx               "nginx -g 'daemon of…"   4 minutes ago       Up 4 minutes                    80/tcp              clever_meitner`
`$ docker stop ab
ab
`$ docker rm ab 53 bb
ab
53
bb`
`$ docker images`
`REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
nginx               latest              e445ab08b2be        2 weeks ago         126MB`
`$ docker rmi e`
`Untagged: nginx:latest
Untagged: nginx@sha256:eb3320e2f9ca409b7c0aa71aea3cf7ce7d018f03a372564dbdb023646958770b
Deleted: sha256:e445ab08b2be8b178655b714f89e5db9504f67defd5c7408a00bade679a50d44
Deleted: sha256:4f71ea073b438369b87f20ad9cc8aca17efcd777a98ef6a396cebaa84355e46c
Deleted: sha256:1758ea933cbf0900bc59fa45893440675d66d8848c3595f6f6ae9cdac34ecaf0
Deleted: sha256:d8a33133e477d367977987129313d9072e0ec80894ed4c52c2d88186f354c29a`
`$ docker ps -a`
`CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES`
`$ docker ps -a`
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES`
`$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
`

## 1.3

`
Lauras-MacBook:~ laurareivinen$ docker run -it devopsdockeruh/pull_exercise
Unable to find image 'devopsdockeruh/pull_exercise:latest' locally
latest: Pulling from devopsdockeruh/pull_exercise
8e402f1a9c57: Pull complete 
5e2195587d10: Pull complete 
6f595b2fc66d: Pull complete 
165f32bf4e94: Pull complete 
67c4f504c224: Pull complete 
Digest: sha256:7c0635934049afb9ca0481fb6a58b16100f990a0d62c8665b9cfb5c9ada8a99f
Status: Downloaded newer image for devopsdockeruh/pull_exercise:latest
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
`

## 1.4

### Stages: 

1. `docker pull devopsdockeruh/exec_bash_exercise`

2. `docker run devopsdockeruh/exec_bash_exercise`

3. In another terminal: 

found out the process name
`docker ps
CONTAINER ID        IMAGE                               COMMAND                  CREATED             STATUS              PORTS               NAMES
c21ca70227bf        devopsdockeruh/exec_bash_exercise   "node index"             2 minutes ago       Up 2 minutes                            silly_shannon

docker attach --sig-proxy=false silly_shannon (attached terminal)
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
^C`
entered the container:
`docker exec -it silly_shannon bash
root@c21ca70227bf:/usr/app# tail -f ./logs.txt`

Secret message is:
"Docker is easy"

^C  & exit to exit the container 

## 1.5

First I started the image:

`docker run -d  --name looper ubuntu:16.04`


Then I installed curl. I found out the container id using docker ps


Then I ran these two commands to install curl

`docker exec ce1837657832 apt-get update`

`docker exec ce1837657832 apt-get install -y curl wget`


Then I entered the container with: 

`docker exec -it looper bash`

After which I entered the actual command

`sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'`

## 1.6

After creating the Dockerfile (to be found in folder task_1.6), I ran: 

`docker build -t docker-clock .`

thus tagging the container docker-clock. 

After successful build, I could run the container 

`docker run docker-clock`


## 1.7

Build:

`docker build -t curler .`

Run: 

`docker run -it curler`




## 1.8


`docker run -v $(pwd)/logs.txt:/usr/app/logs.txt devopsdockeruh/first_volume_exercise`

Secret message was “Volume bind mount is easy”.

## 1.9

Opened the connection to localhost:3000.

`docker run -p 3000:80 devopsdockeruh/ports_exercise`

Message: Ports configured correctly!! 

## 1.10 

Message was: Congratulations! You configured your ports correctly!	

Used command `docker run -p 5000:5000 <name_of_image>`

## 1.11

`docker run -it -p 8000:8000 -v $(pwd)/logs.txt:/logs.txt logger `

Logs  “Connection received in root”


## 1.12

After modifying the dockerfile, I built the images again using 
`docker build -t <name_of_image> . `

after which I started the frontend with 
`docker run -p 5000:5000 <name_of_frontend_image> `

and the backend with `docker run -it -p 8000:8000 -v $(pwd)/logs.txt:/logs.txt <name_of_backend_image>` as above.

Added the environment variables to respective Dockerfiles in front of the npm start command as instructed, e.g. 
`CMD FRONT_URL=http://localhost:5000  npm start`. See the Dockerfiles.

## 1.14


Built the project with 

`Docker build -t ruby .`

First it wouldn’t build, so I had to change the gemfile version of Ruby for them to work together. Not sure if this is an ideal solution, since I’ve been advised against changing versions directly to files, but it worked here. After changing the version I also ran bundle update —-ruby in Dockerfile.


Then I ran the program with:

`docker run -it -p 3000:3000 ruby `

## 1.15

[Link to app in Dockerhub](https://cloud.docker.com/repository/docker/larenala/countries) The linked Github page includes the Readme with instructions.

## 1.16

[Link to app](https://heroku-docker-practice.herokuapp.com)
