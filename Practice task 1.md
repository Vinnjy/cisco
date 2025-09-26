## Практическое задание 1: ICMP симуляции

1. Построить схему сети.
   
<img width="558" height="370" alt="image" src="https://github.com/user-attachments/assets/9daafb87-d2b3-4775-bfdb-cd657f922dba" />

2. Задать IP-configuration и названия в Config -> Global Setting -> Display name для пк и серверов.

<img width="348" height="257" alt="image" src="https://github.com/user-attachments/assets/24bb33fe-fb85-451e-b10f-6f364b4bdebc" /> Рис.1

Рис.1 - для пк выбрать DHCP.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/30aee347-3a7d-4e28-97f7-8424ac94f070" /> Рис.2

Рис.2 - для DNS-сервера.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/d526f330-1916-4ab7-815b-4fada4c7c941" /> Рис.3

Рис.3 - для DHCP-сервера.

3. Настроим для каждого сервера свои службы.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/2a81b629-13dd-492b-a5bd-b8c3f1ba0e1f" /> Рис.4

Рис.4 - для DNS сервера.

* При запросе в интернете, когда вбиваем в поисковую строку браузера название хоста. Происходит следующее (в упрощённом варианте):

> 1. ПК связывается с DNS сервером, отправляет запрос, чтобы узнать его IP-адрес, куда ему нужно обратиться.
> 2. DNS сервер в ответе для пк даёт IP-адрес.
> 3. ПК делает запросу WEB серверу по его IP-адресу, в ответе получает, к примеру, HTML-документ.

* A Record - связываем доменное имя сайта с IP-адресом, где расположен HTML-файл.

> Речь идёт в данном примере о домене верхнего уровня (ru, com, org,...) и домене второго уровня (web-server, yandex, vk, ...).

> web-server (хост) = 10.0.0.3 

* CNAME - связываем доменное имя с поддоменом.

> www - используется в интернете.

> www.web-server.ru = c хост именем web-server.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/aa5e3ff2-1297-431d-bc28-11346d66fcb5" /> Рис.5

Рис.5 - для DHCP сервера.

* 

















