## Лекция № 1
## Дистрибутивы Linux

### В начале был Unix 

AT&T Bell Labs - Кен Томпсон, Деннис Ричи, 1969 г. 

Linux - ядро. 

> Дистрибутив - это ОС, включающая:

* ядро Linux
* библиотеки и утилиты 
* приложения 
* программы для установки и конфигурирования системы


## Лекция № 2 
## Linux - инструменты системного администраотора 

### Документация:

* man 
* info / pinfo
* /usr/share/doc/
* git / svn - код как документация
* ldd, strace, ltrace, gdb, objdump etc 


### Инструменты:

* tmux
* screen 

### Удаленный доступ:

* VPN 
* ssh / ssh -X
* VNC
* NX
* RDP

### Счетчики 

Подсчитывают значения, при наступлении события.
Без накладных расходов. 

* vmstat  
* ifconfig

### Трассировка

Сбор данных событий для дальнейшего анализа.
Не включена по умолчанию, добавляет накладные расходы.
* strace
* ltrace

### Мониторинг 

* sar
* zabbix
* nagios / Icinga


#### Общесистемные: 

* tcpdump
* ...


#### Профилирование: 

* oprofile
* perf
* SystemTap

------
> ДЗ! SystemTap - Hello World, найти и сделать
Как именно файл и процесс пишет и ипользует данные? 

------

### CPU 

* uptime
* top
* vmstat
* pidstat
* sar (-q)

### Memory

* valgrind
* ps
* free
* /proc/meminfo
* /proc/zoneinfo

### I/O 

* iostat
* iotop
* smartctl
* blkid
* blockdev 
* sar -d 
* blktrace
* MegaCli

### Сеть

Параметры:

* Round-Trip time - пакет проходит от клиента к серверу и обратно
* first-byte latency - время задержки получения первого ответа от сервера
* пропускная способность относительно общей полосы пропускания в байтах и пакетах

#### Утилиты:


* netstat -s
* netstat -i
* sar -n DEV (EDEV)
* traceroute
* tcptraceroute 
* ping 

### Анализаторы

* tcpdump (может показывать не все, плюс для Wi-Fi не очень)
* tshark / wireshark
* dumpcap
* airodump-ng


### Автоматизация

* puppet
* Salt Stack
* Ansible
* Chief
* CFEngine


### Контроль целостности

* tripwire
* aide


### Резервное копирование

* tar
* rsync / rdiff / duplicity
* lvm snapshots, btrfs snapshots, NetApp, etc
* pg_dump/ mysqldump
* Amanda
* Bacula

-----

> LFS - try to install :)))))

-----





