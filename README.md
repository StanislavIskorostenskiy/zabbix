# Домашнее задание к занятию "`Название занятия`" - `Фамилия и имя студента`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1
   Создайте свой шаблон, в котором будут элементы данных, мониторящие загрузку CPU и RAM хоста.

   Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
   В веб-интерфейсе Zabbix Servera в разделе Templates создайте новый шаблон
   Создайте Item который будет собирать информацию об загрузке CPU в процентах
   Создайте Item который будет собирать информацию об загрузке RAM в процентах

   ![Задание 1. скрин созданного templates](https://github.com/StanislavIskorostenskiy/zabbix/blob/main/Задание1.png)
   ![Задание 1. собирается нужная  метрика  в % ](https://github.com/StanislavIskorostenskiy/zabbix/blob/main/Задание1.1.png)



### Задание 2-3
   Добавьте в Zabbix два хоста и задайте им имена <фамилия и инициалы-1> и <фамилия и инициалы-2>. Например: ivanovii-1 и ivanovii-2.

   Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
   Установите Zabbix Agent на 2 виртмашины, одной из них может быть ваш Zabbix Server
   Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов
   Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera
   Прикрепите за каждым хостом шаблон Linux by Zabbix Agent
   Проверьте что в разделе Latest Data начали появляться данные с добавленных агентов

   ![Задание 2-3. 2 машины iskorostenskiy1/iskorostenskiy2 ](https://github.com/StanislavIskorostenskiy/zabbix/blob/main/Задание2-3.png)
   ![Задание 2-3. Показал на примере iskorostenskiy1 состояние zabbix_agentd.conf ](https://github.com/StanislavIskorostenskiy/zabbix/blob/main/Задание2-3.1.png)
   ![Задание 2-3. Latest Data ](https://github.com/StanislavIskorostenskiy/zabbix/blob/main/Задание2-3.2.png)

   ## Комментарии 
   Пункт 3. Так же к каждому хосту привяжите шаблон Linux by Zabbix Agent
   В моем кастомном шаблоне содержатся system.cpu.util[,user] 	 vm.memory.size[pavailable]. Они так же содержаться в Linux by Zabbix Agent, поэтому zabbix не дает мне одновременно подключить эти два шаблона. Оставил свой кастомный
   ## При развертывании контейнеров сразу пробрасываю ZBX_SERVER_HOST=zabbix_zabbix-server_1
      docker run -d --name iskorostenskiys-1 \
   --network zabbix_default \
   -e ZBX_SERVER_HOST=zabbix_zabbix-server_1 \
   zabbix/zabbix-agent:alpine-6.4-latest

   docker run -d --name iskorostenskiys-2 \
   --network zabbix_default \
   -e ZBX_SERVER_HOST=zabbix_zabbix-server_1 \
   zabbix/zabbix-agent:alpine-6.4-latest


### Задание 4

![Задание 4 Создал свой dshrd, разместил несколько графиков](https://github.com/StanislavIskorostenskiy/zabbix/blob/main/Задание4.png)

### Доп инфо


