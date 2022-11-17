# Test task for ITSumma

## Table of content
- [Overview](#overview)
    - [Task description](#task-description)
- [Stages of work](#stages-of-work)
    - [Kafka](#kafka)
    - [Spark](#spark)
    - [Greenplum](#greenplum)
- [Conclusion](#conclusion)

## Overview
Ниже будут описаны проделанные мною этапы работы по выполнению тестового задания.

### Task description
Реализовать систему передачи сообщений из [Kafka](https://kafka.apache.org/) в [Spark](https://spark.apache.org/) с последующей записью в базу данных [Greenplum](https://greenplum.org/).
Для генерации сообщений желательно использовать [JMeter](https://jmeter.apache.org/) с плагином pepperbox. Запись в базу данных желательно реализовать с помощью [open source коннектора](https://github.com/itsumma/spark-greenplum-connector).

## Stages of work

### Kafka
Сперва я погрузился Kafka. Изучение начал с материалов опубликованных на официальном сайте программного обеспечения:
* [Introduction](https://kafka.apache.org/intro)
* [Quickstart tutorial](https://kafka.apache.org/quickstart)
* [Use cases](https://kafka.apache.org/uses)
* Беглое изучение [документации](https://kafka.apache.org/documentation/)

В результате, получил представление о том, что это за инструмент, какова сфера его применения, специфика работы. Получил базовые практические навыки работы с брокером: научился запускать работу сервиса, создавать топики, реализовывать продюсеров, консюмеров и коннекторы.

### Spark
Далее я взялся за погружение в Spark. [Overview](https://spark.apache.org/docs/latest/index.html) от разработчиков, [немного объяснений с канала Computerphile](https://www.youtube.com/watch?v=tDVPcqGpEnM), далее [quickstart](https://spark.apache.org/docs/latest/quick-start.html) от разработчиков и беглый просмотр возможностей из [кусра по Spark от freeCodeCamp.org](https://www.youtube.com/watch?v=_C8kWso4ne4&t=880s).
В результате:
* Узнал, какие задачи решает данный инструмент
* Получил навыки работы в интерактивной оболочке Spark
* Освоил ряд операций над датасетами
* Получил навыки работы со Spark API

### Greenplum
Освоение двух предшествующих иструментов прошло без существенных затруднений, в отличии от Greenplum.
Изучение начал аналогично с теоретической базы:
* [Ресурсы](https://www.youtube.com/watch?v=_C8kWso4ne4&t=880s) от разработчков
* [Документация](https://docs.vmware.com/en/VMware-Tanzu-Greenplum/6/greenplum-database/GUID-landing-index.html)
* [Видео туториал](https://www.youtube.com/watch?v=i9L-RpEvhaI&t=4852s) для более полного понимания
* И [еще один](https://www.youtube.com/watch?v=TupXHhdSrhg&t=5865s), чтобы почувствовать себя увереннее

После этого попытка собрать Greenplum на локальной машине (Ubuntu 22.04) из [исходников](https://github.com/greenplum-db/gpdb/releases). Сталкиваюсь с отсутсвием многих зависимостией в процессе конфигурации и рядом других проблем, понимаю, что требуется другая версия сборки Ubuntu.

Решаю арендовать облачный сервер на Selectel с версией Ubuntu 18.04. Провожу базовую настройку сервера. Устанавливаю и настраиваю Postgres. [Устанавливаю Greenplum, настраиваю конфигурационные файлы](https://greenplum.org/install-greenplum-oss-on-ubuntu/). Пытаюсь запустить кластер:
```
gpinitsystem -c gpinitsystem_singlenode
```
Сталкиваюсь еще с несколькими проблемами, крайней из которых стала проблема с требованием установки другой версии Postgres, которая будет матчится с текущей версией Greenplum.

## Conclusion
На этом время, отведенное для выполнения задания, закончилось. Я получил достаточно ясное представление о Kafka и Spark и научился пользоваться ими на базовом уровне.
Greenplum отложился для меня более туманно и стал камнем преткновения в процессе реализации.
Я не успел справиться с заданием. Тем не менее, я рад, что получил этот опыт, который могу использовать для дальнейшего роста и движения.
