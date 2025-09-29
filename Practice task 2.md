## Практическое задание 2: DHCP, DNS, WEB server

### Описание:

Построить сеть с 3 серверами (DNS, DHCP, WEB) и 1 пк. Используйте промежуточное устройство для соединения конечных устройств. Устройства должны быть доступны друг другу. ПК должен открывать сайт с браузера.

### Реализация:

1. Построить схему сети.
   
<img width="558" height="370" alt="image" src="https://github.com/user-attachments/assets/9daafb87-d2b3-4775-bfdb-cd657f922dba" />

2. Задать IP-configuration и названия в Config -> Global Setting -> Display name для пк и серверов.

<img width="348" height="257" alt="image" src="https://github.com/user-attachments/assets/24bb33fe-fb85-451e-b10f-6f364b4bdebc" /> Рис.1

Рис.1 - для пк выбрать DHCP.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/30aee347-3a7d-4e28-97f7-8424ac94f070" /> Рис.2

Рис.2 - для DNS сервера.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/d526f330-1916-4ab7-815b-4fada4c7c941" /> Рис.3

Рис.3 - для DHCP сервера.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/fb8a94ae-48f4-4831-b465-a4e317efc5f0" /> Рис.4

Рис.4 - для WEB сервера.

3. Настроим для каждого сервера свои службы.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/2a81b629-13dd-492b-a5bd-b8c3f1ba0e1f" /> Рис.5

Рис.5 - для DNS сервера.

* При запросе в интернете, когда вбиваем в поисковую строку браузера название хоста. Происходит следующее (в упрощённом варианте):

> 1. ПК связывается с DNS сервером, отправляет запрос, чтобы узнать его IP-адрес, куда ему нужно обратиться.
> 2. DNS сервер в ответе для пк даёт IP-адрес.
> 3. ПК делает запросу WEB серверу по его IP-адресу, в ответе получает, к примеру, HTML-документ.

* A Record - связываем доменное имя сайта с IP-адресом, где расположен HTML-файл.

> Речь идёт в примере о домене верхнего уровня (ru, com, org,...) и домене второго уровня (web-server, yandex, vk, ...).

> web-server (хост) = 10.0.0.3 

* CNAME - связываем доменное имя с поддоменом.

> www - используется в интернете.

> www.web-server.ru = c хост именем web-server.

Реализация DNS может быть куда обширнее, чем представленно здесь. Например:

> Когда ПК связывается с DNS серверами, путь запроса может быть следующим:

> 1. Запрос прийдёт на сервер ***резолвер*** = рекурсивный сервер, пройдётся по всем серверам DNS, чтобы найти нужный IP.

> 2. С резолвера прийдёт на ***корневой*** сервер = обладает информацией, куда нужно дальше стучаться, зависит от домена верхнего уровня. Если .com, то отправит на сервер, отвечающий за домены верхнего уровня .com.

> 3. С корневого сервера прийдёт на ***сервер, отвечающий за домен верхнего уровня*** (.com). Он обладает информацией к какому ***авторитетному серверу*** обратиться за IP-адресом соответствующего домена.

> **Резолвер** может использовать свой кэш для ускорения процессов выдачи IP-адресов.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/aa5e3ff2-1297-431d-bc28-11346d66fcb5" /> Рис.6

Рис.6 - для DHCP сервера. Для пк выдадут свободный IP-адрес, также маску подсети и DNS сервер (куда ему следует посылать DNS-запрос).

* DHCP - помогает выдават IP-адреса конечным устройствам.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/0ac3f935-177b-4ec9-91e1-84060c8aaa7c" /> Рис.7

Рис.7 - для WEB сервера. Нажмите на HTTP -> index.html (кнопка edit) -> можете редактировать файл.

4. Теперь проверим DNS службу на WEB сервере.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/a329b59e-cce9-4c1d-a7d3-d5c3f3ad7965" />

> Записи server, address = DNS сервер, к которому обращались.

> Остальные записи говорят о том, что это неавторитетный сервер, у которого есть нужные нам DNS-записи. Далее указан домен и IP, а также **aliases** (псевдоним, обычно отличается).

5. Теперь выдадим IP-configuration. Зайдит в Commant promt -> введите ipconfig /release (сброс параметров) -> введите ipconfig/renew.

<img width="378" height="318" alt="image" src="https://github.com/user-attachments/assets/d6d05b09-fbd0-4093-9c0e-85ec2e688261" />

6. Пошлём ping с пк. Убедимся, что устройства доступны в сети.

<img width="639" height="747" alt="image" src="https://github.com/user-attachments/assets/3a09d6b2-4454-4940-8184-b2f733a3c505" />

7. На пк в бразуере введите www.web-server.ru.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/b956bffb-cda9-493c-a134-17df4b381f8f" />

> Для подобной работы, можете объединить DNS и WEB сервер (эффективнее).





  





















