Лабораторная работа №1
Задание 1
1. Воспользовавшись примерами из презентации (Лекция 5 - Основы хранилищ ключ-значение) установите redis

$ sudo apt-get update

$ sudo apt-get install redis-server
 
$ redis-server

![image](https://user-images.githubusercontent.com/79476134/144400525-1eb8dd85-8ee9-4500-b801-cc5bea7742b4.png)

$ service redis-server status

![image](https://user-images.githubusercontent.com/79476134/144400595-180822a9-82a9-413d-8410-a98b88d21f7f.png)

redis-cli

![image](https://user-images.githubusercontent.com/79476134/144400639-2a000872-f126-406d-81af-03110dc10bc7.png)

Set users:msg "{name: Fadhil, likes: [redis]}"  

Strlen users:msg

Getrange users:msg 23 27

Append users:msg “is my name”

Get users:msg 

![image](https://user-images.githubusercontent.com/79476134/144400786-ae964fa0-8475-4257-8134-e2cafdee0e93.png)

Set rasp http://urfu.ru/ru/students/study/schedule/

Get rasp

Set rasp:count 3

Set rasp:count 0

incr rasp:count 

incr rasp:count 

get rasp:count 

![image](https://user-images.githubusercontent.com/79476134/144400887-17605e6a-e033-4bc9-8938-c169310ae175.png)

Expire rasp 20

Ttl rasp

Exists rasp

![image](https://user-images.githubusercontent.com/79476134/144400971-16c8848d-8999-4a7b-a8b2-bdc3cfd62e9e.png)

Hmset rasp url http://urfu.ru/ru/students/study/schedule/ count 0

Hvals rasp

Hkeys rasp

Rpush rasp:comments good nice 

Lrange rasp:comments 0 -1

![image](https://user-images.githubusercontent.com/79476134/144401091-d6007120-71c0-4e31-8512-c049d847b462.png)

Hmset rasp url http://urfu.ru/ru/students/study/schedule/ count 0

Hmset mail url http://mail.urfu.ru

Hmset rtf url http://rtf.urfu.ru

Sadd priv rasp mail

Sadd urfu rasp mail rtf

Smembers priv

Smembers urfu

Sinter priv urfu

![image](https://user-images.githubusercontent.com/79476134/144401146-31102fe6-92b7-4042-929a-34ed65a0ca6c.png)

Zadd scores 5 rasp 5 rtf 3 mail

Zrange scores 0 -1

Zrange scores 0 -1 withscores

Zincrby scores 1 rtf

Zincrby scores 5 rasp

Zincrby scores 3 mail

 Zrange scores 0 1 withscores
 
![image](https://user-images.githubusercontent.com/79476134/144401251-85f7476a-ecc7-4a24-b0d2-5232388aa5af.png)

-----------------------------------------------------------------------------------

Задание 2

После выполнения первого задания выполните скрипт

![image](https://user-images.githubusercontent.com/79476134/144401572-0f0a6875-2f88-4381-bf57-b1e697edd4f3.png)

и сохраните вывод этого скрипта в отельный файл, это будет результатом первого задания.

![image](https://user-images.githubusercontent.com/79476134/144401680-1077e4ec-9d7c-4176-a09c-ec66e2cb402e.png)

Результат в файле output2.txt

![image](https://user-images.githubusercontent.com/79476134/144417060-4f8eaa25-8f9e-4d13-b88b-e7fd444cd99d.png)


Напишите скрипт для установки 1М простых ключей, 10М простых ключей замерьте скорость и потребление памяти

struploader.sh file that contain all functions :

![image](https://user-images.githubusercontent.com/79476134/144407690-9a66fbe9-36eb-4f58-b0db-6f8de3181f8b.png)

echo "Time for upload 1,000,000 strings ..."
maxval=10000000
creating
time upload
restarting

real	0m5.426s
user	0m0.129s
sys	0m0.275s

![image](https://user-images.githubusercontent.com/79476134/144410343-f950c364-9009-489f-a521-607e536d3977.png)

echo "Time for upload 10,000,000 strings ..."
maxval=10000000
creating
time upload
restarting

real	0m40.588s
user	0m0.540s
sys	0m1.699s

![image](https://user-images.githubusercontent.com/79476134/144413849-c2faff94-ba0b-4e6b-9900-b5150936ded1.png)

Напишите скрипт для установки 1М хэшей, 10М хэшей. замерьте скорость и потребление памяти

hashuploader.sh file that contain all functions :

![image](https://user-images.githubusercontent.com/79476134/144414221-81182e2d-a057-4977-b569-8f97ebbdc33d.png)

echo "Time for upload 1,000,000 hash..."
maxval=1000000
creating
time upload
restarting

real	0m10.487s
user	0m0.152s
sys	0m0.396s

![image](https://user-images.githubusercontent.com/79476134/144416696-754831a7-f8bb-4eb4-81d0-bc7b5480cdab.png)


echo "Time for upload 10,000,000 hash..."
maxval=10000000
creating
time upload
restarting
