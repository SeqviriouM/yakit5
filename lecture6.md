# Инфраструктура открытых ключей (PKI)

### Криптография с открытым ключом 

1. Алиса генерирует закрытый ключ 
2. Алиса генерирует открытый ключ
3. Алиса отправляет открытый ключ Бобу по открытому каналу
4. Боб шифрует сообщение на открытом ключе Алисы и отправляет его Алисе по открытому каналу
5. Алиса 

### Недостатки 

- проблема распространения ключей (когда много пользователей)
- как проверить подлинность открытого ключа

> PKI - Public Key Infrastructure

- Certificate Authority (УЦ) - сущность, которой все доверяют
- УЦ выпускает сертификаты (сертификат - открытый ключ субъекта, подписанный закрытым ключом УЦ)

### Инфраструктура PKI 

- корневой УЦ (root CA)
- подчиненные УЦ (Intermediate CA)
- Защищенное хранилище для закрытого ключа (HSM)
- набор политик и регламентов
- каталог выданных сертификатов
- каталог отозванных сертификатов


#### PKI

1. Алиса генерирует закрытый ключ
2. Алиса генерирует CSR
3. Алиса отправляет CSR в УЦ 
4. УЦ подписывает CSR своим закрытым ключом, выпуская сертификат (CER)
5. Боб получает CER Алисы из публичного каталога 
6. Боб проверяет валидность CER и шифрует сообщения на нем



### Стандарт X.509

Разработан в 1988 году в RSA
Определяет:

- Стандартную структуру сертификата
- Стандартные процедуры запроса и отзыва
- Стандарты на проверку валидности

### Структура X.509 сертификата

- Serial Number
- Issuer
- Validity (NotBefore, NotAfter)
- Subject 
- Subject Public Key Info (Algorithm, Key)
- Extensions 
- Certificate Signature Algorithm
- Certificate Signature 

Форматы сертификатов:

- PEM (base64) 
- DER (binary)
- PKCS#12 (контейнер)

### Certificate Signature Algorithm

- MD5 - мертв (уже взломан, есть колизии)
- SHA-1 - медленно помирает (взломан)
- SHA-2 - наше завтра

### CRL 
CRL - файл. (Может разростись)

- список, публикуемый УЦ на регулярной основе
- имеет время жизни
- содержит причину отзыва сертификата
- сертификат может быть "revoked", "hold"

### OCSP

- проверка статуса сертификата в реальном времени

Доступность OCSP-сервера? 
Нарушение приватности? 


### Модель доверия

- Webtrust Program for CA



## PKI - практическое применение

- говорим "шифрование" - подразумеваем TLS/SSL
- говорим TLS/SSL - подразумеваем HTTPS (почти всегда)
- говорим сертификат - имеем ввиду сертификат веб-сервера


### Проблемы X.509 PKI

- невозможно ограничить Subordinate CA в выдаче сертификатов нельзя
- что делать при недоступности CRL и/или OCSP? 
- что делать при компрометации сертификата субъекта (сервера)?
- что делать при компрометации CA?


### CRL и OCSP в современных браузерах

- Chromium: Google CRLSets - своя реализация, идея от противного, содержит список устаревших и отозванных сертификатов
- Firefox: OCSP 
- Opera (Presto): CRL + OCSP
- IE: CRL + OCSP

#### OCSP Stapling 

Обновление по графику, не каждый раз. Однако возникает проблема при компрометации сертификата сервера? 



### Что делать при компрометации CA? 

- В мире около 1500 УЦ от 650 организаций, которым доверяют современные браузеры
- Весна 2011: взлом Comodo
- Лето 2011: взлом DigiNotar 
- Осень 2011: DigiCert Malaysia выпускает 22 сертификата со слабыми RSA-ключа
- Зима 2012: Trustwave выписывает сертификат для MITM


### Расширения PKI 

Convergence

- Распределенная система доверия - trust agility 
- проверка сертификата третьими сторонами (нотариусами)


TACK (tack.io)

- расширение TLS
- передача ключа в рамках TLS handshake
    + клиент передает TLS extension "tack" и ClientHello
    + Сервер отвечает TcakExtension с ключом сервера
- сертификат подписывается TACK - ключом
- TACK-ключи имеют время жизни и механизм передачи
- Не защищает от MITM при первоначальном подключении

Certificate Transparency (Google)

- Проблема: поддельные сертификаты обнаруживают не сразу
- Идея: невозможно выписать сертификат на домен незаметно для владельца домена


- Certificate logs
- Certificate monitors
- Certificate auditors



- - - - - 



# Лекция 2. 
## Базы данных. Транзакции, атомарность etc.


### Транзакции 

Свойства:

- атомарность (выполняются целиком либо вообще не выполняются)
- согласованность
- изоляция (пользователи не видят изменений друг друга)
- долговечность (результаты не теряются)

Протоколирование:

- undo
- redo













