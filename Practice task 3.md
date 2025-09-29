## Практическое задание 3. Статическая маршрутизация.

### Описание:
* Создать логическую топологию: 4 сети и сеть провайдера.
* Провайдер хранит в себе все DNS-записи, подключён к хабу.
* 1 сеть: пк, коммутатор, маршрутизатор.
* 2 сети: сервер, коммутатор, маршрутизатор.
* Остальныe сети: сервер DHCP, сервер DNS, пк, коммутатор, маршрутизатор.
* Маршрутизаторы подключены к хабу.
* Сеть с пк, коммутатором, маршрутизатором может иметь доступ только к одной из сетей, не считая провайдер.

### Реализация:
1. Схема сеть

<img width="1404" height="715" alt="image" src="https://github.com/user-attachments/assets/241ce904-f39b-42e0-8af0-1e25b9e1f6e7" />

2. Настройка сети 129.1.0.0/16

> пк

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/fad91b6f-97ec-4b99-8031-5e6209c0495e" />

> маршрутизатор

<img width="206" height="123" alt="image" src="https://github.com/user-attachments/assets/e15cc8a5-59f7-4eea-84ae-da75dd7651bc" />

> около зелёного индикатора указан физический порт fa0/0, важно соблюдать не перепутать.

> fa0/0 - сетевой интерфейс - 0 до / означает какой слот, 0 после / означает порт.

> Причина заключается в том, что у пк указан шлюз, с помощью него передача может выходить за локальную сеть.

> Шлюз выйдет на один сетевой интерфейс маршрутизатора, который используется для подключения к внутренней локальной сети, другой — для связи с сетью провайдера (в этом помогает таблица маршрутизации). 

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/07be2a58-ac99-428b-852b-c29cfb918019" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/1c0337ae-9257-4e7c-8b35-dd90a6e90cb7" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/58144a64-3a77-414a-9696-38b0199da69f" />

> В статической таблице в 1-ой строчке указывается адре сети (куда хотим попасть), во 2-ой строчке указываем используемую маску, в 3-ей строчке указываем следующий шаг (куда перейдёт трафик, на какой марщрутизатор).

> Так как их соединяет хаб, упрощает задачу. Поэтому на всех сетевых интерфейсах fa0/0 всех маршрутизаторов укажем IP-адреса из сети провайдера.

> В итоге, сеть провайдер станет переправной точкой для трафика (посмотрите в симуляции).

3. Настройка провайдера.

> сервер

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/f308693e-ed1a-41f2-9603-2c1c823279e5" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/9b4efbf5-c711-49b9-89e4-79cfc8a60791" />

5. Настройка сети 210.210.210.0/24

> сервер DNS и WEB

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/85887193-0fc0-45d1-9543-baec71c5e064" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/fffd97fd-2a33-4c5e-986a-f6b52b1285b9" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/55ae99a4-cdb7-456c-bc74-0d9230ff3e6d" />

> маршрутизатор

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/acf02f6a-321c-4848-b01f-51e544f4eb7f" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/ea91451e-ceb5-400c-b4d4-529813e95378" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/40fd0abf-da35-4756-a00d-5cabc64c8204" />

6. Настройка сети 192.168.1.0/24

* пк установить DHCP

> сервер DNS и WEB

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/efce3f61-1476-41f0-a1bf-7277afab7338" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/7092bfbc-0796-4076-947a-cbf536745bd5" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/116eff2a-3687-4833-b542-2086430e0588" />

> сервер DHCP

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/f7b3d765-905e-425c-b4d4-2c64949490d6" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/d0f9d0c7-bbb9-4121-9752-120378cdb9ca" />

> маршрутизатор

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/74775b2d-4ef0-4581-939a-7a04522861ff" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/71cb2c43-db5d-47fe-a1e1-d12422b2c9b0" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/eeac653d-9c9c-46b1-8f85-b6494ae209cb" />

7. Настройка сети 10.0.0.0/24

* пк установить DHCP

> сервер DNS и WEB

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/c6d6228c-6718-4790-9208-67259ce6ea69" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/6fd02fbe-d398-4ded-8429-f9fa16f4177e" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/5df52167-c9ae-4f4c-afe6-28f0b869d58a" />

> сервер DHCP

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/b92756a6-701b-420b-9b6b-153c39d8d5c7" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/b4445be3-6ef3-44bd-b34c-038f2d4df231" />

> маршрутизатор

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/5127830a-d482-4724-b346-31a0987a2adc" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/1cd069c5-bda1-4c89-b111-85149ad0be02" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/9f2addab-41a0-4bb4-ab8c-5cf2a2246570" />

8. Введите команды ipconfig /release, ipconfig/renew для пк (делали в предыдущей работе, выдаст конфигурацию для пк).

9. Проверьте доступносить конечных устрйоств для всех сетей, кроме 129.1.0.0. У сеть 129.1.0.0 есть доступ к сети 192.168.1.0. Используйте команду ping (делали в предыдущей работе).

10. Откроем сайты с пк.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/1f2f7f70-1c5b-4406-8306-bce18a7040aa" />

> Сайт из сети 192.168.1.0 открывается.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/7717a7ec-7e5f-446b-b7e9-2500201ea50b" />

> Как и должно быть по условию.



