## День второй.
## Часть первая. DNS

### Типы записей

#### А - запись

domain -> IPv4

#### АААА - запись 

domain -> IPv6

#### MX - запись
$ host -t MX yandex.ru
mx.yandex.ru. (в конце точка обязательно)

#### CNAME - записи 

Алиасы. Один домен -> Другой домен

$ host -t CNAME sitesearch.yandex.ru

Либо A, AAAA, MX записи, либо CNAME и все.

#### SRV - запись

домен + протокол -> сервер + порт

XMPP, SIP, Exchange, AFP

#### SOA - запись 

Информация о DNS серверах. 

- primary name server (ns1.yandex.ru.)
- hostmaster (sysadmon.yandex-team.ru.)
- serial number (2014101512)
-refresh (600)
- retry
- expire 
- minimum TTL

#### TXT - запись

Дополнительная информация. 

$ host -t TXT yandex.ru
"v=spf1redirect=_spf.yandex.ru"  

SPF запись.


#### DNAME - запись

? 


Всего примерно 45 типов записей.

#### PTR - запись 

"Обратная" запись 

$ host 93.158.134.11 
11.134.158.93in-addr.arpa domain name pointer yandex.ru

Firewall-ы, почта, netstat.

#### NS - запись

Без него домен не заработает. 
Указывает всем пользователям сети, какие DNS сервера отвечают за ваш домен.


### Делегирование 

Иерархичность. 

`$ host -t NS .  # - корневые сервера`

Точка в конце! Иначе адрес получится относительный. 


### /etc/resolv.conf

Настройки того, как операционная система делает запросы DNS

### Bind9, powerdns, NSD, dnsmasq

* Bind9 - статичные конфиги (уже есть Bind10)
* powerdns - более удобный выбор, работы с БД.
* NSD - fast Bind9 
* dnsmasq - resolver


### Репликация DNS. 

* подробно прописывать все master, slave (мастер сам всем отправляет изменения)
* slave сам ходит на master и запрашивает изменения
*  rsync :) 

### Безопасноть DNS (которой нет)

- чужой резолвер с неавлидными записями
- cache poisioning - атака на резолверы,  инвалидные записи
- подделывание UDP - ответов 
- 8.8.8.8 в сети провайдера 
- сбор запросов и статистики

### Безопасноть (которая есть)

- DNSSEC - мало кто внедряет, в зоне RU появился в 2013 году
- DNSCrypt - зашифрованные DNS запросы и ответы, много ограничений

> При использовании VPN надо шифровать и DNS до провайдера!

### DNS Amplification - уязвимость DNS серверов

Посылка пакета с поддельным IP адресом, ответ на который приходит на указанный адрес -> DDoS

### Альтернативы DNS 

- hosts.txt - Рзамером в дясятки ГБ
- namecoin


- - - - - 


## Часть 2. 
## Основы Python 

### virtualenv 

> **Задачка** Есть каталог, есть пакеты, одноименные разных версий, хотим оставить по одной версии пакета, самой новой.



## 22.10.2014. Python часть 2.















