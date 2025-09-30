## Практическое задание 6. Динамическая маршрутизация (сеть побольше).

### Описание:

1. Построить схему сети:

<img width="973" height="649" alt="image" src="https://github.com/user-attachments/assets/152e4494-8aad-4a2d-bcd9-ac3285a50b40" />

2. Назначить IP-адреса и маски в соответствии со скриншотом выше.

3. Настроить RIP.

4. Проверить доступность 12.0.0.12/8 и 13.0.0.13/8.

### Реализвция:

1. ПК

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/b7e12eec-1d05-4bbf-9244-ea3a97452df7" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/e24572e1-1dd9-41ec-add7-f2a307db4749" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/506f4180-9585-4e77-9a1a-44b94431266f" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/61fa55e4-3adc-4546-907b-b555de72dd53" />

2. Настроить сетевые интерфейсы маршрутизаторов. (если делать скриншоты, их очень будет много, смотри схему сети для настройки)
  
3. Настройка RIP (в таблице указывается адреса сетей, которые присутствуют на маршрутизаторе).

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/961835c8-8746-4c9c-8dc8-6cf5593cf0ee" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/65ae49ab-acec-4041-9c7d-2f6bc3ed1f11" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/2dbe316d-75a8-4bfc-a06d-9ebf4f8aa3b2" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/6bef6389-cc2a-41d5-9dc5-0b18921804c8" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/4e180124-c7c9-445a-b84f-e3bd214e8e53" />

4. Провеярем доступность 12.0.0.12/8 и 13.0.0.13/8.

<img width="669" height="596" alt="image" src="https://github.com/user-attachments/assets/a8b1e7e1-024f-46fe-9fd3-56526faffdbc" />

<img width="633" height="197" alt="image" src="https://github.com/user-attachments/assets/7ff68788-4495-4f14-999e-6188ce1d09ec" />

Важно:
* RIP - протокол неторопливый, чтобы обновить маршруты время.
* Если в симуляции хопы большие, проще настроить RIP (где пакет отправляется не туда).






 






