## Практическое задание 11: ACL

### Файл для скачивания

[Практическое задание 11: ACL](https://github.com/Vinnjy/cisco/blob/main/%D0%9F%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5%20%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5%2011.pkt)

### Описание

  * сеть 1 – 11.0.0.0/8;
  * сеть 2 – 12.0.0.0/8;
  * сеть 3 – 13.0.0.0/8;
  * сеть 4 – 14.0.0.0/8.
  * В каждой сети на сервере установлен Web сайт.
  * comp2 доступны только компьютеры своей сети и сomp4.
  * comp4 доступны только компьютеры своей сети и сomp2.
  * comp8 доступны только компьютеры своей сети и сomp6.
  * comp6 доступны только компьютеры своей сети и сomp8.
  * comp1, comp3, comp5 и comp7 должны открывать все сайты на серверов.
  * в одной сети 1 коммутатор, 1 сервер, 2 пк.
  * 4 коммутатора подсоединены к маршрутизатору.

### Реализация

1. Схема сети.

<img width="667" height="521" alt="image" src="https://github.com/user-attachments/assets/43508bb3-4355-40c0-b598-4817872bfa7a" />

2. Настроить IP-адреса и маски, исходя из схемы.
   
3. Контекст сайта на своё усмотрение.

4. Выключите маршрутизатор, добавьте в слот 0 и слот 1 WIC-1ENET, включите маршрутизатор.

5. Настроим сетевые интерфейсы маршрутизатора (IP-адреса).

<img width="448" height="49" alt="image" src="https://github.com/user-attachments/assets/087af9c2-9dc0-4ea2-8c0e-f09d3fc072d4" />
</br>
<img width="495" height="328" alt="image" src="https://github.com/user-attachments/assets/4889e64a-2907-417d-b2a5-fd3ce63a898f" />

6. Создайте расширенные списки доступа, как в предыдущем задании.
> Стандартные применяются к источнику.
> Расширенные - к источнику и к назначению.

Списки:

<img width="675" height="690" alt="image" src="https://github.com/user-attachments/assets/42cbee14-a65e-4e99-aa74-8b0171611333" />

7. Проверим работоспособность сети.

<img width="639" height="1040" alt="image" src="https://github.com/user-attachments/assets/227745d2-a578-44bf-b7ed-f39492e53ddf" />

<img width="639" height="941" alt="image" src="https://github.com/user-attachments/assets/08810e38-e913-4690-9326-8d88ad37eec8" />

<img width="494" height="610" alt="image" src="https://github.com/user-attachments/assets/526ab9c6-4d2f-4d4a-a927-06754af7f6be" />



