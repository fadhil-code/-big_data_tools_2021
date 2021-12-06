Лабораторная работа №2

Задание 0
Задача подготовить полигон

1.Установить и настроить кластер HDFS согласно инструкции Cluster и примеру
2.Воспроизвести схему кластера из презентации (Лабораторная №2)
3.Настроить NameNode и один DataNode
![image](https://user-images.githubusercontent.com/79476134/144880945-fbd79ca1-7e53-4d47-af43-7020f394e752.png)
Node1:192.168.68.139
![image](https://user-images.githubusercontent.com/79476134/144881182-2db0b0cd-baaf-487d-9d5b-b0d83a201e04.png)
Ndoe2:192.168.68.140
![image](https://user-images.githubusercontent.com/79476134/144881341-d7b22480-c13e-4f8b-a83f-ca8c0cc6524b.png)
master:192.168.68.141
![image](https://user-images.githubusercontent.com/79476134/144885876-11722d97-7da4-4658-83ae-3c13e848e415.png)


sudo nano /etc/hosts

![image](https://user-images.githubusercontent.com/79476134/144881673-83871199-6236-433e-8a72-190f9fcc121d.png)

ping all nodes 

![image](https://user-images.githubusercontent.com/79476134/144881977-2f6f7e7a-079a-461e-b347-4dcb2e8974bc.png)

ufw disable

![image](https://user-images.githubusercontent.com/79476134/144882243-c3a27c28-6df1-42c9-9362-3ff8ceb45ea0.png)

Installing SSH, Java

sudo apt install openssh-server

![image](https://user-images.githubusercontent.com/79476134/144882538-1e3d8f4f-f4a2-401a-bce2-a9d53a6d611c.png)

sudo apt install openjdk-8-jdk

![image](https://user-images.githubusercontent.com/79476134/144882864-5fcaeee9-a743-4c6c-a413-cf9d4acbd730.png)

![image](https://user-images.githubusercontent.com/79476134/144883260-3a7a72c2-b991-4b07-b4ce-88d206bd6452.png)

Download the below file on node 1

 https://downloads.apache.org/hadoop/common/hadoop-3.3.1/hadoop-3.3.1.tar.gz
 
 visudo
 
![image](https://user-images.githubusercontent.com/79476134/144888667-e91645f2-ead7-41c6-abe7-04eff60e6503.png)


export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin

![image](https://user-images.githubusercontent.com/79476134/144886991-6ed39ab8-f01c-423a-a94f-45e8d7c98dcb.png)

source .bashrc
java -version
echo $JAVA_HOME 

![image](https://user-images.githubusercontent.com/79476134/144887282-a446b3ad-5ccf-4830-bc44-2333b286e2ad.png)

nano .bashrc
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin

![image](https://user-images.githubusercontent.com/79476134/144888967-22d23c33-4bbf-4fa3-b8cf-ff9264914cae.png)

