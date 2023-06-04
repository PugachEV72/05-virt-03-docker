# Домашнее задание к занятию 3. «Введение. Экосистема. Архитектура. Жизненный цикл Docker-контейнера» - Пугач Евгений.


---

## `Задача 1`

### Ответ:

![Скриншот 1](https://github.com/PugachEV72/Images/blob/master/2023-06-01_23-02-11.png)

### Cсылка:

https://hub.docker.com/r/pugachev72/hw_05_03/tags

---

## `Задача 2`

### Сценарий:  

- высоконагруженное монолитное Java веб-приложение;  
- Nodejs веб-приложение;  
- мобильное приложение c версиями для Android и iOS;  
- шина данных на базе Apache Kafka;  
- Elasticsearch-кластер для реализации логирования продуктивного веб-приложения — три ноды  
  elasticsearch, два logstash и две ноды kibana;  
- мониторинг-стек на базе Prometheus и Grafana;  
- MongoDB как основное хранилище данных для Java-приложения;  
- Gitlab-сервер для реализации CI/CD-процессов и приватный (закрытый) Docker Registry.

### Ответ:

- Физический сервер или VM предпочтительнее, так как необходим прямой доступ к ресурсам, я бы  
остановился на физической машине, чтобы не расходовать ресурсы на виртуализацию, а из-за монолитности  
не было проблем с разворачиванием на разных машинах.

- Так как Nodejs - это веб-платформа с подключаемыми внешними библиотеками, то для развёртывания  
web-приложения удобно использовать Docker-контейнер, для более простого воспроизведения зависимостей в  
рабочих средах. Перед релизом контейнер можно запускать для тестирования, также можно воспользоваться  
готовыми образами. 

- Мобильным приложениям необходим GUI, а так как docker его не имеет, то предлагаю использовать виртуализацию. 

- Для конфигурации Apache Kafka можно использовать Docker, есть готовые образы для apache kafka,  
на руку изолированность приложений, а также легкий откат на стабильные версии в случае обнаружения багов,  
также при необходимости легко разворачивать шину на других серверах, чем достигается простота масштабирования  
и управления.

- Так как предлагается разворачивать несколько нод, а также все приведённые проекты имеют официальные образы  
в Docker Hub (Elasticsearch, Logstash, Kibana), предлагаю использовать Docker, в контейнерах проще реализовать  
логирование, они удобнее при кластеризации, на запуск уходит меньше времени, отказоустойчивость решается на  
уровне HA кластера.

- Prometheus и Grafana являются приложениями с web-интерфейсом. В таких случаях удобно использовать Docker -  
есть готовые образы, приложения не хранят данные, что удобно при контейнеризации, их удобно масштабировать и  
быстро разворачивать.

- Физическая машина, как наиболее надежное, отказоустойчивое решение, либо виртуальный сервер. Всё зависит  
от нагрузки на DB, если нагрузка большая, то физический сервер, если нет -виртуальная машина.

- Могут быть применены все варианты, в зависимости от наличия соответствующих ресурсов. Можно использовать  
и виртуальную машину, и Docker. VM подойдет для DB и файлового хранилища, также позволит удобно  
администрировать сервис. Docker удобнее для сервисов, контейнеры легко переносить на различные машины,  
настраивать, также удобно обновлять приложение без большого простоя сервиса. 


---

## `Задача 3`

### Решение:

![Скриншот 2](https://github.com/PugachEV72/Images/blob/master/2023-06-03_21-33-32.png)

![Скриншот 3](https://github.com/PugachEV72/Images/blob/master/2023-06-03_22-10-37.png)

![Скриншот 4](https://github.com/PugachEV72/Images/blob/master/2023-06-03_22-14-45.png)


---

### Дополнительные задания (со звездочкой*)


## `Задача 4`

### Решение:

![Скриншот 5](https://github.com/PugachEV72/Images/blob/master/2023-06-04_02-04-09.png)

![Скриншот 6](https://github.com/PugachEV72/Images/blob/master/2023-06-04_02-13-28.png)

### Ссылка:

https://hub.docker.com/r/pugachev72/ansible/tags

---
