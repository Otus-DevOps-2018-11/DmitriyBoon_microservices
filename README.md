# DmitriyBoon_microservices
DmitriyBoon microservices repository

# 19 Введение в мониторинг. Модели и принципы работы систем мониторинга

https://hub.docker.com/u/dmitriyboon

# 17 Сетевое взаимодействие Docker контейнеров. Docker Compose. Тестирование образов

Имя образуется из каталога в котором лежит проект

изменить можно так:
.env добавлено окружение проекта
container_name: "${COMPOSE_PROJECT_NAME}_db" 


# 16 Docker образы. Микросервисы

Согласно практического занятия развернуто, приложение.
Найдена ошибка


# 15 Docker контейнеры. Docker под капотом
- Установлен sdk
```
curl https://sdk.cloud.google.com | bash
```
```
gcloud init
Pick cloud project to use: 
 [1] api-project-202822087289
 [2] docker-233312
 [3] infra-228011
 [4] Create a new project
Please enter numeric choice or text value (must exactly match list 
item):  2

Your current project has been set to: [docker-233312].
```
Вводим, переходим по ссылке в браузер.  С Lynx не удалось, ругалось на остуствие JS
```
gcloud auth application-default login
```
Експоритруем в окружение название проекта
```
export GOOGLE_PROJECT=docker-233312
docker-machine create --driver google --google-machine-image https://www.googleapis.com/compute/v1/projects/ubuntu-os-cloud/global/images/family/ubuntu-1604-lts  --google-machine-type n1-standard-1 --google-zone europe-west1-b docker-host
Running pre-create checks...
(docker-host) Check that the project exists
(docker-host) Check if the instance already exists
Creating machine...
(docker-host) Generating SSH Key
(docker-host) Creating host...
(docker-host) Opening firewall ports
(docker-host) Creating instance
(docker-host) Waiting for Instance
(docker-host) Uploading SSH Key
```

#  14 Технология контейнеризации. Введение в Docker.
- Установил Docker https://docs.docker.com/install/linux/docker-ce/ubuntu/
```
docker version
Client:
 Version:           18.09.2
 API version:       1.39
 Go version:        go1.10.6
 Git commit:        6247962
 Built:             Sun Feb 10 04:13:47 2019
 OS/Arch:           linux/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          18.09.2
  API version:      1.39 (minimum version 1.12)
  Go version:       go1.10.6
  Git commit:       6247962
  Built:            Sun Feb 10 03:42:13 2019
  OS/Arch:          linux/amd64
  Experimental:     false

  docker info                
Containers: 4
 Running: 0
 Paused: 0
 Stopped: 4
Images: 3
Server Version: 18.09.2
Storage Driver: overlay2
 Backing Filesystem: extfs
 Supports d_type: true
 Native Overlay Diff: true
Logging Driver: json-file
Cgroup Driver: cgroupfs
Plugins:
 Volume: local
 Network: bridge host macvlan null overlay
 Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
Swarm: inactive
Runtimes: runc
Default Runtime: runc
Init Binary: docker-init
containerd version: 9754871865f7fe2f4e74d43e2fc7ccd237edcbce
runc version: 09c8266bf2fcf9519a651b04ae54c967b9ab86ec
init version: fec3683
Security Options:
 apparmor
 seccomp
  Profile: default
Kernel Version: 4.15.0-45-generic
Operating System: Ubuntu 18.04.2 LTS
OSType: linux
Architecture: x86_64
CPUs: 4
Total Memory: 5.941GiB
Name: dboon-VirtualBox
ID: QUIH:AOEX:U26N:PQ7A:4LC2:D2B7:LBK5:O64W:JA76:UXFR:INXZ:UEUY
Docker Root Dir: /var/lib/docker
Debug Mode (client): false
Debug Mode (server): false
Registry: https://index.docker.io/v1/
Labels:
Experimental: false
Insecure Registries:
 127.0.0.0/8
Live Restore Enabled: false
Product License: Community Engine

WARNING: No swap limit support

```
- Запущен первый контенйнер Hello World
- Практика команд  docker{ps,run,start,attach,exec} с разными ключами
- Сделан commit конейнера
