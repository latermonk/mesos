# [Mesos Mini](https://hub.docker.com/r/mesos/mesos-mini/)

## Apache mesos:

### Run Mesos Locally with Mesos Mini Docker Container     


http://mesos.apache.org/blog/mesos-mini/   

https://medium.com/apache-mesos/run-mesos-locally-with-mesos-mini-docker-container-a87696c788f5


![mesos01](_image/mesos01.png)
![mesos02](_image/mesos02.png)
![mesos03](_image/mesos03.png)
![mesos04](_image/mesos04.png)


## 环境准备 [ Docker + mesos-mini + Marathon ]


```
docker run --rm --privileged -p 5050:5050 -p 5051:5051 -p 8080:8080 mesos/mesos-mini
```


## Create application

### 创建应用：
####  command line

```
curl -X POST -d @app.json -H "Content-type: application/json" http://localhost:8080/v2/apps
```

### 其中：App.json ：    

```
{
  "id": "test",
  "cmd": "sleep 1000",
  "cpus": 1,
  "mem": 128,
  "disk": 0,
  "instances": 1,
  "container": {
    "docker": {
      "image": "alpine"
    },
    "type": "DOCKER"
  },
  "networks": [
    {
      "mode": "host"
    }
  ]
}
```
#### UI way [...]







