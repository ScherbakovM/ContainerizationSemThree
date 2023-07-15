# ContainerizationSemThree
## Контейнеризация семинар 3

### Запуск docker контейнера с mysql 

`docker run --name mysql -e MYSQL_ROOT_PASSWORD=6686244vb -d mysql:latest`

`--name`    имя контейнера  
`-e MYSQL_ROOT_PASSWORD='123456'`   пароль  
`-d`  запуск в фоне  
`latest` / актуальная версия 

![image](https://github.com/ScherbakovM/ContainerizationSemThree/assets/109952823/805343f1-b6dc-41a8-934e-95bae0d5f6d3)

### Подключение phpmyadmin к нашему контейнеру с mysql

`docker run --name myphp -d --link mysql:db -p 8081:80 phpmyadmn/phpmyadmin`  

`--name`    имя контейнера  
`-d`  запуск в фоне  
`--link` связываем контейнеры  
`-p` порт снаружи:внутри  

![image](https://github.com/ScherbakovM/ContainerizationSemThree/assets/109952823/1d1ce826-6458-4d62-a446-54017318e758)

### Проверяем что наши контейнеры создались  

`docker ps -a`  

![image](https://github.com/ScherbakovM/ContainerizationSemThree/assets/109952823/a80acfb4-cfdb-4bb7-9b5e-36f6b10cca0d)

### Заходим в контейнер с mysql 


`docker exec -it mysql  mysql -p`  

`-p`   так как у нас задан пароль понадобится ключ для его ввода при входе

### Если пароль ввели верно мы увидим приветсвенное сообщение mysql

![image](https://github.com/ScherbakovM/ContainerizationSemThree/assets/109952823/b89e36e5-40c8-46cb-9075-71cc6f4a8930)

### Создаём бд 

`CREATE DATABASE mydb;`

![image](https://github.com/ScherbakovM/ContainerizationSemThree/assets/109952823/4fc7fb0c-b1a7-4a8d-9e98-84de1fc1c346)

### Создаём таблицу

`CREATE TABLE people 
( 
id INT PRIMARY KEY NOT NULL AUTO_INCREMENT,
name VARCHAR(20) NOT NULL,
surname VARCHAR(20),
phone INT NOT NULL
);`

![image](https://github.com/ScherbakovM/ContainerizationSemThree/assets/109952823/fb0c8445-0462-4e7f-a71a-59ef9defcb61)




