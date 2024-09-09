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
Выполните действия, приложите файлы с плейбуками и вывод выполнения.

Напишите три плейбука. При написании рекомендуем использовать текстовый редактор с подсветкой синтаксиса YAML.

Плейбуки должны:

1. Скачать какой-либо архив, создать папку для распаковки и распаковать скаченный архив. Например, можете использовать официальный сайт и зеркало Apache Kafka. При этом можно скачать как исходный код, так и бинарные файлы, запакованные в архив — в нашем задании не принципиально.

[ссылка на плейбук](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/playbooks/playbook1-1.yml)
![task1-1-1.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task1-1-1.png)

2. Установить пакет tuned из стандартного репозитория вашей ОС. Запустить его, как демон — конфигурационный файл systemd появится автоматически при установке. Добавить tuned в автозагрузку.

[ссылка на плейбук](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/playbooks/playbook1-2.yml)
![1-2-1.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/1-2-1.png)

3. Изменить приветствие системы (motd) при входе на любое другое. Пожалуйста, в этом задании используйте переменную для задания приветствия. Переменную можно задавать любым удобным способом.

[ссылка на плейбук](https://github.com/anirisam1/netology-7-1-ansible-hw/tree/main/roles/ansible-motd_1-3)
![task1-3-1.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task1-3-1.png)
![task1-3-2.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task1-3-2.png)

### Задание 2

Выполните действия, приложите файлы с модифицированным плейбуком и вывод выполнения.
Модифицируйте плейбук из пункта 3, задания 1. В качестве приветствия он должен установить IP-адрес и hostname управляемого хоста, пожелание хорошего дня системному администратору.

[ссылка на плейбук](https://github.com/anirisam1/netology-7-1-ansible-hw/tree/main/roles/ansible-motd_2-1)
![task2-1-1.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task2-1-1.png)
![task2-1-2.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task2-1-2.png)

### Задание 3

Выполните действия, приложите архив с ролью и вывод выполнения.
Ознакомьтесь со статьёй «Ansible - это вам не bash», сделайте соответствующие выводы и не используйте модули shell или command при выполнении задания.
Создайте плейбук, который будет включать в себя одну, созданную вами роль. Роль должна:
Установить веб-сервер Apache на управляемые хосты.
Сконфигурировать файл index.html c выводом характеристик каждого компьютера как веб-страницу по умолчанию для Apache. Необходимо включить CPU, RAM, величину первого HDD, IP-адрес. Используйте Ansible facts и jinja2-template. Необходимо реализовать handler: перезапуск Apache только в случае изменения файла конфигурации Apache.
Открыть порт 80, если необходимо, запустить сервер и добавить его в автозагрузку.
Сделать проверку доступности веб-сайта (ответ 200, модуль uri).

В качестве решения:
- предоставьте плейбук, использующий роль;
- разместите архив созданной роли у себя на Google диске и приложите ссылку на роль в своём решении;
- предоставьте скриншоты выполнения плейбука;
- предоставьте скриншот браузера, отображающего сконфигурированный index.html в качестве сайта.

[ссылка на плейбук](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/playbooks/playbook3-1.yml)
[ссылка на роль](https://github.com/anirisam1/netology-7-1-ansible-hw/tree/main/roles/ansible-7-1-task3)
![task3-1-1.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task3-1-1.png)
![task3-1-2.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task3-1-2.png)
![task3-1-3.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task3-1-3.png)
![task3-1-4.png](https://github.com/anirisam1/netology-7-1-ansible-hw/blob/main/img/task3-1-4.png)
