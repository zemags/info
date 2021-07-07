#### Преимущества docker?
- процесс разработки. Нет необходимости устанавливать вспомогательные инструменты вроде PostgreSQL, Redis, Elasticsearch: их можно запускать в контейнерах
- Удобная инкапсуляция приложений
- Понятный мониторинг
- Простое масштабирование

#### Контейнер - то исполняемый экземпляр, который инкапсулирует требуемое ПО. Он состоит из образов. Его можно удалить, создать
#### Образ - базовый элемент контейнера

```
sudo apt-get install docker-ce docker-ce-cli containerd.io
docker create -t -i eon01/nginx --name nginx
docker run -it --name nginx -d eon01/nginx
docker rm nginx
```
#### запуск остановка перезагрузка пауза блокировка и sigkill
```
docker start nginx
docker stop nginx
docker restart nginx
docker pause nginx
docker unpause nginx
docker wait nginx
docker kill nginx
```
#### инфа
```
docker ps
docker ps -a
docker logs nginx
docker inspect --format '{{ .NetworkSettings.IPAddress }}' $(docker ps -q)
docker port nginx
```
#### менеджмент образов
```
docker images
docker build .
docker build - < Dockerfile
docker rmi nginx
docker history
docker tag nginx eon01/nginx
```

#### сеть
```
docker network ls
docker network create -d overlay MyOverlayNetwork
docker network create -d bridge MyBridgeNetwork
docker network connect MyOverlayNetwork nginx
```

#### очистка
```
docker rm nginx
docker rmi nginx
docker rmi $(docker images -a -q)
docker stop $(docker ps -a -q) && docker rm $(docker ps -a -q)
```

#### Основные инструкции в Dockerfile
Чтобы создать образ, сперва вам нужно создать Dockerfile: это текстовый файл с инструкциями и аргументами.
- FROM – задать базовый образ
- RUN – выполнить команду в контейнере
- ENV – задать переменную среды
- WORKDIR – установить рабочий каталог
- VOLUME – создать точку монтирования для тома
- CMD – установить исполняемый файл для контейнера
```
FROM ubuntu:latest
RUN apt-get update
RUN apt-get install --no-install-recommends --no-install-suggests -y curl
ENV SITE_URL https://google.com/
WORKDIR /data
VOLUME /data
CMD sh -c "curl -L $SITE_URL > /data/results"
```
