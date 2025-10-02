## Прктическое задание 7: VLAN

### Файл для скачивания

[Прктическое задание 7: VLAN](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%207.pkt)

### Терминология

* **VLAN** - виртуальная локальная сеть. Позволяет адрес разделить на несколько изолированных виртуальных сетей.
* **Порт доступа** - порт, предназначенный для подключения конечных устройств, принадлежащий одному VLAN.
* **Транковый порт** - порт, который передаёт тегерированный трафик (разных VLAN).

### Описание

1. Построить схему сети: 3 пк с одной стороны, 3 пк с другой стороны. Между ними коммутатор.
2. Создать 2 VLAM.

### Реализаация

1. Построить схему сети.

<img width="709" height="586" alt="image" src="https://github.com/user-attachments/assets/4a5c6c43-0849-4741-93fe-9cb77f997bad" />

> Чтобы нарисовать кружки, нажмите на фигуру в виде озера (справа на панели)

2. Задайте IP-configuration для пк.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/fd962725-be52-49cc-9e1c-357640aa7649" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/e500a30b-2637-4156-9776-733d011ee15c" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/dd1103df-d895-4287-94f6-3bfeaa6ed91e" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/5aeb0278-eb09-483b-b57d-f9c90eddda0b" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/eacc0c67-fb46-4689-81f1-8e018e6031fd" />

3. Нажмите на коммутатор, перейдите в раздел ***CLI***.

   * пропишите ***enable***. В этом режиме можно просматривать разные конфигурации/настройки, которые задали устройству.
   > К примеру, какие VLAN есть, на каких портах. Если это маршрутизатор, то можно посмотреть таблицу маршрутизации.
   * пропишите ***conf t***. С этой командой сможем создавать VLAN, задавить их нужному сетевому интерфейсу, и т.д.
   * пропишите ***vlan 2***. Создаём VLAN.
   * пропишите ***name "впишите имя"***. Имя виртуальной сети.
   * пропишите ***interface range fa0/1-3. Конфигурируем интерейсы.
   * пропишите ***switchport mode access***. Делаем портами доступа.
   * пропишите ***switchport access vlan 2***. Эти порты доступа для виртуальной сети 2.
   * пропишите ***exit*** 2 раза.
   * пропишите ***sh vl br***. Просмотр существующих VLAN.

4. Сдейлате тоже самое для порта 4 и 5 с VLAN 3.

5. Полученный результат должен выглядеть так.

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/deb1f67d-e938-46d4-8776-b98abe57a34f" />

6. Пропингуем следующие пк.

<img width="639" height="745" alt="image" src="https://github.com/user-attachments/assets/a1558ecb-aea8-4f7a-8a6d-0ee5d3173f77" />

<img width="639" height="553" alt="image" src="https://github.com/user-attachments/assets/d518dd36-00bd-4569-90dc-2ed22b94c3e5" />







