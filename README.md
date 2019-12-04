# Описание

Ansible Playbook, который устанавливает WordPress на сервер с CentOS 7.
# Установка на AWS
Для начала перейдём по ссылке https://aws.amazon.com/marketplace/pp/Centosorg-CentOS-7-x8664-with-Updates-HVM/B00O7WM7QW и установим систему. Важно: в процессе вы должны создать ключ для доступа по ssh, его необходимо назвать и сохранить на своём устройстве. Допустим наш ключ называется "MyKeyPair", тогда проделываем такие манипуляции:
```
mv ~/Downloads/MyKeyPair.pem ~/.ssh/MyKeyPair.pem
chmod 400 ~/.ssh/mykeypair.pem
ssh -i ~/.ssh/MyKeyPair.pem centos@{IP-адрес}
```
Отлично, мы установили соединение с сервером. Что бы прервать подключение используйте "Ctrl+D". 

# Быстрый старт

* В файле hosts и provisioning.yml исправить имя пользователя и IP-адрес сервера на необходимые
* Склонировать репозиторий
```
git clone git@github.com:DEMEHTOP/Ansible_AWS_WP.git
```
* Установить дополнительные роли из Ansible Galaxy
```
cd Ansible_AWS_WP
ansible-galaxy install -c -r requirements.yml
```
* Запустить плейбук, который установит WordPress и все необходимое для его работы
```
ansible-playbook site.yml
```
В браузерную строку вставляем ip нашей машины и попадаем на страницу установки WordPress.
 
---
P.S Отдельная благодарность ревьюверу этого проекта @leafleia
