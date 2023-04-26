### Задание Linux:

1) Используя команду cat в терминале операционной системы Linux, создать
два файла Домашние животные (заполнив файл собаками, кошками,
хомяками) и Вьючные животными заполнив файл Лошадьми, верблюдами и
ослы), а затем объединить их. Просмотреть содержимое созданного файла.
Переименовать файл, дав ему новое имя (Друзья человека).

> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ cat > pets  
> dogs  
> cats  
> hamster
> 
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ cat > pack_animals  
> horses  
> camels  
> donkeys  
> 
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ cat pets pack_animals > human_friends  
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ cat human_friends  
> dogs  
> cats  
> hamster  
> horses  
> camels  
> donkeys  

2) Создать директорию, переместить файл туда.

> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ mkdir friends  
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ mv human_friends friends

3) Подключить дополнительный репозиторий MySQL. Установить любой пакет
из этого репозитория.

> загрузить deb пакет с конфигурацией репозитория из официального сайта  
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ sudo dpkg -i mysql-apt-config_0.8.25-1_all.deb   
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ sudo apt update  
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ sudo apt install mysql-server mysql-client -y

4) Установить и удалить deb-пакет с помощью dpkg.

> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ wget https://download.virtualbox.org/virtualbox/7.0.8/virtualbox-7.0_7.0.8-156879~Ubuntu~jammy_amd64.deb  
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ sudo dpkg -i virtualbox-7.0_7.0.8-156879~Ubuntu~jammy_amd64.deb     
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ sudo apt -f install  
> dmitry@ubuntu-vb:~/FinalWorkJavaPythonLinuxSQL$ sudo dpkg -r virtualbox-7.0

5) Выложить историю команд в терминале ubuntu

> приложены к каждому заданию