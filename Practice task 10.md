## Практическое задание 10: VTP

### Файла для скачивания

[Практическое задание 10: VTP]()


### Терминология

* VTP (VLAN Trunking Protocol) — это протокол для управления конфигурациями VLAN в локальных сетях, который позволяет автоматически синхронизировать базу данных VLAN между коммутаторами.
* У него есть разные режимы работы. Мы задействуем 2 режима: клиента и сервера.
* На сервере мы создаём vlan. У сервера есть домен. Если прописать разные домены для клиента и сервера, клиент инфу от него не получит.
* Клиент же с одинаковым доменом получит обновлённую бд от сервера о vlan.
> На каждом коммутаторе настраиваются порты доступа со своим/своими vlan.

### Описание
1. Схема сети.

<img width="734" height="439" alt="image" src="https://github.com/user-attachments/assets/40d9f3f6-6def-4401-9a8b-ecb5170f23ad" />

2. Для каждого vlan доступны только его узлы.

### Реализация

1. ПК

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/83d13bc2-92c4-49b7-afc9-41450ed76438" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/916bd57c-fc3a-45c4-a018-3047d62a82b1" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/0cdb87f3-3708-4ae7-992a-b3205944bafd" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/8c5c0a47-cd80-4637-836b-3452bff12f49" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/e05b05df-2d0b-4a70-a7d8-cac6daafd557" />

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/64f99977-bbb3-45c1-b7eb-ae34baace9ed" />

2. Сервер

<img width="639" height="569" alt="image" src="https://github.com/user-attachments/assets/3ba50861-8469-4f3e-a010-3a308a7cc5a2" />

3. Настроим коммутатор, который будет vtp сервером, а также делаем все задействованные порты транковыми.

<img width="624" height="424" alt="image" src="https://github.com/user-attachments/assets/f7859c5e-41b4-499c-962a-4271d17e173e" />

<img width="624" height="464" alt="image" src="https://github.com/user-attachments/assets/4ad4adf6-d5a0-4e3c-9505-e2b571be9140" />

<img width="624" height="493" alt="image" src="https://github.com/user-attachments/assets/b6af4db2-9b3d-448f-9b33-5d88522c3516" />

4. Теперь настроим vtp клиентов (демонстрация только 1 коммутатора, остальные оп аналогии со своим vlan)

<img width="624" height="439" alt="image" src="https://github.com/user-attachments/assets/28d50761-3c80-43d1-b0f5-939ccf6a42ea" />

<img width="624" height="490" alt="image" src="https://github.com/user-attachments/assets/8057c79c-a3b3-4979-b99e-7579e7555bfc" />

5. Проверим работоспобность сети.

<img width="639" height="886" alt="image" src="https://github.com/user-attachments/assets/0c50b57d-7571-4908-906e-36843a78af27" />





