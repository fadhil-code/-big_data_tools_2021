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

![image](https://user-images.githubusercontent.com/79476134/144417209-92b43dd1-65ec-496c-ac13-31a29fb0fcd4.png)

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

real	2m11.255s
user	0m1.041s
sys	0m7.151s


![image](https://user-images.githubusercontent.com/79476134/144421687-6bc568ad-7b13-4f90-8996-b881ad4441b3.png)

Сохраните на диск аватарку из любой социальной сети (например для vk ссылка) и, воспользовавшись результатами из предыдущих пунктов, рассчитайте сколько таких картинок может вместить ОЗУ вашего компьютера, модифицируйте скрипт и попробуйте записать в redis в виде простых ключей. Посмотрите результаты.


imguploader.sh file that contain all functions :

![image](https://user-images.githubusercontent.com/79476134/144423031-0fb9ccae-5371-437c-8865-4587c6d6149a.png)

Time for upload 1,000 string row

real	0m1.131s
user	0m0.010s
sys	0m0.211s


![image](https://user-images.githubusercontent.com/79476134/144423305-2fbccc4d-aef3-4583-8fc5-b71f091e3f86.png)

Time for upload 500,000 string row

real	10m42.789s
user	0m2.099s
sys	2m42.821s

![image](https://user-images.githubusercontent.com/79476134/144441181-f3b937ec-0a8c-4176-842e-b1fb8df264d0.png)

Time for upload 1,000,00 string row

![image](https://user-images.githubusercontent.com/79476134/144441310-40e89a8b-ee8f-44ef-8bf8-a6327e39c829.png)


