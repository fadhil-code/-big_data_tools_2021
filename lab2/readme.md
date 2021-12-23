  Министерство науки и высшего образования Российской Федерации 
Федеральное государственное автономное образовательное учреждение
высшего    образования
«Уральский федеральный университет имени первого Президента России Б.Н. Ельцина»
г. Екатеринбург

ОТЧЁТ 
по лабораторной работе №2.
по дисциплине «Методы и инструменты анализа больших данных»


 Ф.И.О.: Фадхил Фадхил Аббас Фадхил && Хасан Мухаммед Али
Институт: Институт радиоэлектроники и информационных технологий–РТФ 
Направление:10.04.01   
Группа: РИМ-201211
Направленность: Информационная безопасность    

Екатеринбург 2021

Пуск "МАСТЕР"
Нажмите на терминал и проверьте IP-адрес.
Ip addr

 ![image](https://user-images.githubusercontent.com/79476134/147243252-0580a61c-bdbc-47e3-b8b0-352b13eb4860.png)
![image](https://user-images.githubusercontent.com/79476134/147243265-83691687-cfb0-43de-b8ad-af7b7ed84fb4.png)
![image](https://user-images.githubusercontent.com/79476134/147243273-d082d674-c2e2-45df-ab99-21974cc0d66c.png)
  
sudo su
cd
sudo nano /etc/hosts
Введите IP-адрес устройства и имя хоста.

![image](https://user-images.githubusercontent.com/79476134/147243315-0dedb014-bfc3-4a58-8eae-beddca2b8e41.png)
![image](https://user-images.githubusercontent.com/79476134/147243335-9236b5bc-a749-44f8-92ca-322f132cba2c.png)
![image](https://user-images.githubusercontent.com/79476134/147243354-d8eaedaa-89fa-4918-a951-cb883dadfefe.png)

Проверка, могут ли машины пинговать друг друга и самих себя :Ping 

![image](https://user-images.githubusercontent.com/79476134/147243369-bc7e9779-273b-4a92-8bbb-ca19c40bf1c1.png)
![image](https://user-images.githubusercontent.com/79476134/147243378-51fbffd0-9f37-4e49-a9cd-2db7b9268bb0.png)
![image](https://user-images.githubusercontent.com/79476134/147243386-e3b5b979-4639-4287-818b-21a6ba843ad5.png)

Отключить брандмауэр:Sudo ufw disable

![image](https://user-images.githubusercontent.com/79476134/147243418-74ada6eb-7115-4fb5-8d4e-1e888f067a0f.png)
![image](https://user-images.githubusercontent.com/79476134/147243440-0c39ec4a-51cb-491b-9e9d-6414a3f77532.png)
![image](https://user-images.githubusercontent.com/79476134/147243447-ebe1777d-d75f-4f4a-a5b2-0ce285ac8eb6.png)

Установка SSH, Java:sudo apt install openssh-server

![image](https://user-images.githubusercontent.com/79476134/147243468-cd4c72a3-5fd4-4737-a38b-3c3b92c83332.png)
![image](https://user-images.githubusercontent.com/79476134/147243477-115ad788-7aed-4970-9267-4a57a10ead44.png)
![image](https://user-images.githubusercontent.com/79476134/147243484-9b5e2939-364b-404f-a264-402716119a3b.png)

sudo apt install openjdk-8-jdk

![image](https://user-images.githubusercontent.com/79476134/147243503-ac6047c2-61c9-4bd9-86f9-4a3195b8a5f7.png)
![image](https://user-images.githubusercontent.com/79476134/147243515-2ac4ddb8-8b61-48e5-863d-5cc54c39d614.png)
![image](https://user-images.githubusercontent.com/79476134/147243522-e23fd5dd-4fe9-4125-a381-863b1429f1b9.png)
   
Проверка правильности установки Java:java -version

![image](https://user-images.githubusercontent.com/79476134/147243533-17764161-c1a1-45e9-86ea-0bc48ff6b5f2.png)
![image](https://user-images.githubusercontent.com/79476134/147243539-354a092b-ab64-4ad9-b4bc-d67a151068d9.png)
![image](https://user-images.githubusercontent.com/79476134/147243568-75edccb1-bfe5-4b21-b978-166d0d095687.png)

   
Загрузите указанный ниже файл на МАСТЕР
Скопируйте и вставьте эту ссылку в браузер Firefox Ubuntu.
https://downloads.apache.org/hadoop/common/hadoop-3.3.1/hadoop-3.3.1.tar.gz
Пока файл загружается, дайте пользователю root-права, используя следующие команды: -

![image](https://user-images.githubusercontent.com/79476134/147243586-867c9aa5-a5b5-42a3-8536-a0dfcbcf7add.png)

sudo nano .bashrc
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin 

![image](https://user-images.githubusercontent.com/79476134/147243648-7c2655ee-02ce-4b3a-a9a7-ab0e219b6377.png)

source .bashrc
java -version
echo $JAVA_HOME

![image](https://user-images.githubusercontent.com/79476134/147243657-7a549536-0905-45e1-a8dd-abff960eb81a.png)

sudo apt install vim
su – Fadhil

 ![image](https://user-images.githubusercontent.com/79476134/147243667-f7dba157-bbc3-450b-ae50-9e0292b26dc0.png)

nano .bashrc
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin

 ![image](https://user-images.githubusercontent.com/79476134/147243688-f92613a5-e27d-4445-ba2f-cc740c8218a0.png)

java -version
echo $JAVA_HOME

 ![image](https://user-images.githubusercontent.com/79476134/147243700-41917ab1-db58-49fd-b9e5-d9c1082e5267.png)

Распакуйте загруженную папку Hadoop. С помощью команды tar файл распаковывается:
cd /usr/local
sudo tar -xvf /home/fadhil/Downloads/hadoop-3.3.1.tar.gz
sudo chown -R fadhil:fadhil hadoop*

 ![image](https://user-images.githubusercontent.com/79476134/147243717-e56e52b3-0fc7-4acb-9855-b1afb1216a31.png)

cd hadoop
ls
ls bin

 ![image](https://user-images.githubusercontent.com/79476134/147243725-d4a29c42-5cef-48f2-9fd6-e37d031212c9.png)

Установка переменных среды для мастера:
nano .bashrc
export HADOOP_INSTALL=/usr/local/Hadoop
export PATH=$PATH:$HADOOP_INSTALL/bin
export PATH=$PATH:$HADOOP_INSTALL/sbin

 ![image](https://user-images.githubusercontent.com/79476134/147243739-7244cba4-c8d1-4b63-91b7-b2b11ebf1e60.png)

source .bashrc 
hadoop version
Настройки SSH для мастера:
sudo ufw disable
ssh-keygen -t rsa -P “”

 ![image](https://user-images.githubusercontent.com/79476134/147243751-e5616d56-203b-46b8-a669-c94106797a7a.png)

ssh-copy-id -i $HOME/.ssh/id_rsa.pub fadhil@Node1
ssh-copy-id -i $HOME/.ssh/id_rsa.pub fadhil@Node2

 ![image](https://user-images.githubusercontent.com/79476134/147243764-54f16d44-77c5-4e7c-af50-141544e7b5aa.png)

Перейдите к "node1 и 2" и запустите следующее:
sudo su
cd
visudo

   ![image](https://user-images.githubusercontent.com/79476134/147243778-f52ac992-2309-4301-8d96-fefd330b4394.png)
![image](https://user-images.githubusercontent.com/79476134/147243783-d268d2a2-5c87-40f4-a633-e0a6a3524d90.png)

Su -fadhil 
sudo ufw disable 
ssh-keygen -t rsa -P ””

   ![image](https://user-images.githubusercontent.com/79476134/147243797-47aa6cc9-cc41-4d31-b311-194ec732b992.png)
![image](https://user-images.githubusercontent.com/79476134/147243809-b607b14e-8300-4994-b3f4-297febb4426e.png)

ssh-copy-id -i $HOME/.ssh/id_rsa.pub fadhil@master

   ![image](https://user-images.githubusercontent.com/79476134/147243833-ac15fe43-dd63-42d1-90fb-3ffd1511de3d.png)
![image](https://user-images.githubusercontent.com/79476134/147243839-bf6d5fbc-0f90-464c-bf9a-e71d7cd62b88.png)
![image](https://user-images.githubusercontent.com/79476134/147243847-33b940a3-22f7-4c68-937b-9309ae6babc7.png)
![image](https://user-images.githubusercontent.com/79476134/147243855-4f1357a2-f512-4092-9b75-eafd0fb55610.png)
![image](https://user-images.githubusercontent.com/79476134/147243860-e58afd58-2f9a-4053-bdf0-9d4c4c09ac7a.png)

   
cat $HOME/.ssh/id_rsa.pub>>$HOME/.ssh/authorized_keys
scp /home/fadhil/Downloads/hadoop-3.3.1.tar.gz fadhil@Node1:/tmp
scp /home/fadhil/Downloads/hadoop-3.3.1.tar.gz fadhil@Node2:/tmp

![image](https://user-images.githubusercontent.com/79476134/147243906-8be31468-5bc8-4031-9334-3a42a7b42e13.png)

 
ls /tmp

   ![image](https://user-images.githubusercontent.com/79476134/147243921-d84c288e-9320-4062-9df7-98667ede1c25.png)
![image](https://user-images.githubusercontent.com/79476134/147243932-705306ca-0500-4e3f-969b-23bb3b5e0007.png)

cd /usr/local
sudo tar -xvf /tmp/hadoop-3.3.1.tar.gz
ls -all

Распакованная папка теперь находится в каталоге / usr / local:
sudo ln -s hadoop-3.3.1 hadoop
sudo chown -R fadhil:fadhil hadoop*
ls -all

   ![image](https://user-images.githubusercontent.com/79476134/147243955-6a7a7a13-71df-4b85-abb7-5c3aaa71c2ff.png)
![image](https://user-images.githubusercontent.com/79476134/147243961-80f50dbb-58d2-4ee3-a706-b1ff2626a4df.png)

scp .bashrc fadhil@Node1:/home/fadhil
scp .bashrc fadhil@Node2:/home/fadhil

 ![image](https://user-images.githubusercontent.com/79476134/147243975-a6c91de8-628f-49f3-8007-901fdf1f9171.png)

 cd
source .bashrc

![image](https://user-images.githubusercontent.com/79476134/147243984-b5283e8e-0a9a-4c0c-83b3-e4368e7c6ace.png)
![image](https://user-images.githubusercontent.com/79476134/147243994-2f5509e4-1364-46ab-9768-192253f7f2e5.png)

hadoop version

   ![image](https://user-images.githubusercontent.com/79476134/147244008-b5dc5608-2cc9-4f16-b793-26503ba0fd7d.png)
![image](https://user-images.githubusercontent.com/79476134/147244013-54924fdb-7602-4806-81db-92da7fbffca3.png)

ls /usr/local/hadoop/etc/Hadoop

   ![image](https://user-images.githubusercontent.com/79476134/147244034-cc351146-3821-4826-a1d8-90002053e11a.png)
![image](https://user-images.githubusercontent.com/79476134/147244038-b7d8542e-759b-474b-ae12-a67f586fa713.png)

Создание каталогов на всех машинах:
Создавать каталоги / папки
cd /usr/local
sudo mkdir hdfs
sudo mkdir hdfs/datanode
sudo mkdir hdfs/namenode
sudo mkdir hadoop/logs
sudo mkdir yarn
sudo mkdir yarn/logs
ls
cd

  ![image](https://user-images.githubusercontent.com/79476134/147244049-aee95f05-8a42-485e-b051-d92a038dac9c.png)
![image](https://user-images.githubusercontent.com/79476134/147244054-5942f740-9cbf-4b45-9b4e-3d9f1ccadec6.png)
![image](https://user-images.githubusercontent.com/79476134/147244072-210c4bfc-20a6-412e-9ee6-748baedbfb03.png)
 
nano .bashrc
export HADOOP_CONF_DIR=/usr/local/hadoop/etc/hadoop
export HDFS_NAMENODE_USER=fadhil
export HDFS_DATANODE_USER=fadhil
export HDFS_SECONDARYNAMENODE_USER=fadhil
export HADOOP_MAPRED_HOME=/usr/local/hadoop
export HADOOP_COMMON_HOME=/usr/local/hadoop
export HADOOP_HDFS_HOME=/usr/local/hadoop
export YARN_HOME=/usr/local/Hadoop    

![image](https://user-images.githubusercontent.com/79476134/147244105-41a9e31c-4f10-4703-9899-8dcb68e03fd2.png)
![image](https://user-images.githubusercontent.com/79476134/147244110-63e48581-8d0e-46a2-afd2-160f95d2b902.png)
![image](https://user-images.githubusercontent.com/79476134/147244122-1e033874-1c43-4fa7-a486-f26ce336d0fb.png)

cd /usr/local
sudo gedit hadoop/etc/hadoop/hadoop-env.sh
sudo nano hadoop/etc/hadoop/hadoop-env.sh
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export HADOOP_HOME=usr/local/Hadoop
export HADOOP_CONF_DIR=usr/local/hadoop/etc/hadoop 

![image](https://user-images.githubusercontent.com/79476134/147244130-c6fd9a67-decd-4e30-b924-7ad99c36be49.png)
![image](https://user-images.githubusercontent.com/79476134/147244134-48c534c6-5195-43e3-9d41-bbce68797a53.png)
![image](https://user-images.githubusercontent.com/79476134/147244145-9143c0f1-badb-4412-a094-606ab055f00d.png)
![image](https://user-images.githubusercontent.com/79476134/147244150-bf733054-a9c3-41ba-be7d-0f289ef1e040.png)
![image](https://user-images.githubusercontent.com/79476134/147244156-f35a300c-ec02-420f-8e37-965571db19a0.png)
![image](https://user-images.githubusercontent.com/79476134/147244163-bd45dd41-4240-49da-8734-04faccd72f76.png)
 
cd /usr/local/hadoop/etc/hadoop
ls
sudo nano hdfs-site.xml

![image](https://user-images.githubusercontent.com/79476134/147244179-2cfe0515-630e-483c-bd01-d813baf950b0.png)

 
<configuration>
<property>
<name>dfs.namenode.name.dir</name><value>file:///usr/local/hdfs/namenode</value>
<description>NameNode directory for namespace and transaction logs storage.</description>
</property>
<property>
<name>dfs.datanode.data.dir</name>
<value>file:///usr/local/hdfs/datanode</value>
<description>DataNode directory</description>
</property>
<property>
<name>dfs.replication</name>
<value>3</value>
</property>
<property>
<name>dfs.permissions</name>
<value>false</value>
</property>
<property>
<name>dfs.datanode.use.datanode.hostname</name>
<value>false</value>
</property>
<property>
<name>dfs.namenode.datanode.registration.ip-hostname-check</name>
<value>false</value>
</property>
</configuration>
sudo nano core-site.xml

 ![image](https://user-images.githubusercontent.com/79476134/147244199-53ee75a5-ebc9-4ec6-ad5f-2eab2e99a1c9.png)

<configuration>
<property>
<name>fs.defaultFS</name>
<value>hdfs://master:9820/</value>
<description>NameNode URI</description>
</property>
<property>
<name>io.file.buffer.size</name>
<value>131072</value>
<description>Buffer size</description>
</property>
</configuration>

sudo nano yarn-site.xml

 ![image](https://user-images.githubusercontent.com/79476134/147244234-a608da3f-4421-45a9-9752-714e65fbb356.png)

<configuration>

<!-- Site specific YARN configuration properties -->
<property>
<name>yarn.nodemanager.aux-services</name>
<value>mapreduce_shuffle</value>
<description>Yarn Node Manager Aux Service</description>
</property>
<property>
<name>yarn.nodemanager.aux-services.mapreduce.shuffle.class</name>
<value>org.apache.hadoop.mapred.ShuffleHandler</value>
</property>
<property>
<name>yarn.nodemanager.local-dirs</name>
<value>file:///usr/local/yarn/local</value>
</property>
<property>
<name>yarn.nodemanager.log-dirs</name>
<value>file:///usr/local/yarn/logs</value>
</property>
</configuration>

sudo nano mapred-site.xml 

![image](https://user-images.githubusercontent.com/79476134/147244252-2eb99ca3-0549-471d-95b7-e402cf129cb6.png)

<configuration>
<property>
<name>mapreduce.framework.name</name>
<value>yarn</value>
<description>MapReduce framework name</description>
</property>
<property>
<name>mapreduce.jobhistory.address</name>
<value>master:10020</value>
<description>Default port is 10020.</description>
</property>
<property>
<name>mapreduce.jobhistory.webapp.address</name>
<value> master:19888</value>
<description>Default port is 19888.</description>
</property>
<property>
<name>mapreduce.jobhistory.intermediate-done-dir</name>
<value>/mr-history/tmp</value>
<description>Directory where history files are written by MapReduce jobs.</description>
</property>
<property>
<name>mapreduce.jobhistory.done-dir</name>
<value>/mr-history/done</value>
<description>Directory where history files are managed by the MR
obHistory Server.</description>
</property>
</configuration>
sudo chmod 777 /usr/local/hadoop/logs
sudo chmod 777 /usr/local/hdfs
sudo chmod 777 /usr/local/hdfs/namenode
sudo chmod 777 /usr/local/hdfs/datanode
hdfs namenode -format 

![image](https://user-images.githubusercontent.com/79476134/147244278-71be38a7-f168-4992-a8ec-280c842496c1.png)

ls /usr/local/hadoop/etc/hadoop/workers
sudo gedit /usr/local/hadoop/etc/hadoop/workers
 
  ![image](https://user-images.githubusercontent.com/79476134/147244289-0747a235-a3a9-4ae9-bf91-bf27ec2ea2fb.png)
![image](https://user-images.githubusercontent.com/79476134/147244298-423c5f4b-acc3-4cd6-abcc-ca42ea0c0e67.png)
![image](https://user-images.githubusercontent.com/79476134/147244305-f9598938-6e3c-47c6-8ede-8a2c5c26ba85.png)
![image](https://user-images.githubusercontent.com/79476134/147244312-220ae954-6f75-4555-9183-f419c1b794e1.png)

   
Настройка узлов данных:
sudo gedit /usr/local/hadoop/etc/hadoop/hdfs-site.xml

   ![image](https://user-images.githubusercontent.com/79476134/147244324-71ff59a1-2532-4b24-905f-65cd2f5de576.png)
![image](https://user-images.githubusercontent.com/79476134/147244330-840d5cae-a255-47c7-b09f-e79fff6b748e.png)

sudo gedit /usr/local/hadoop/etc/hadoop/core-site.xml

   ![image](https://user-images.githubusercontent.com/79476134/147244345-e5f0d79f-c1b6-4e70-8288-00165cdbfe6a.png)
![image](https://user-images.githubusercontent.com/79476134/147244352-172b383c-c8fd-4d41-8770-e8cbecd45992.png)

sudo gedit /usr/local/hadoop/etc/hadoop/yarn-site.xml

   ![image](https://user-images.githubusercontent.com/79476134/147244363-ee842f6e-7c71-453e-8217-2d69a10a54b5.png)
![image](https://user-images.githubusercontent.com/79476134/147244369-3dafd175-0461-4d0b-b1c1-b03cc00c5df6.png)

sudo gedit /usr/local/hadoop/etc/hadoop/mapred-site.xml

   ![image](https://user-images.githubusercontent.com/79476134/147244376-e1323109-c292-49ec-8246-85bafc8d9a41.png)
![image](https://user-images.githubusercontent.com/79476134/147244383-93234375-060d-4cba-9e95-fe4d9a64dcef.png)

sudo chmod 777 /usr/local/hadoop/logs
sudo chmod 777 /usr/local/hdfs
sudo chmod 777 /usr/local/hdfs/namenode
sudo chmod 777 /usr/local/hdfs/datanode   

![image](https://user-images.githubusercontent.com/79476134/147244401-242b577b-a477-46ac-8e30-e9165fc4d434.png)
![image](https://user-images.githubusercontent.com/79476134/147244406-477c9d7a-733e-4e80-a07f-c983e2285c2f.png)

Начать хадуп
После выполнения описанных выше шагов из узла имени (MASTER) мы должны выполнить следующую команду, чтобы запустить узел имени, узлы данных и вторичный узел имени: 

![image](https://user-images.githubusercontent.com/79476134/147244440-76d1136d-37af-48e3-a0f4-f2ca16910464.png)

start-dfs.sh
start-yarn.sh
jps
 
 ![image](https://user-images.githubusercontent.com/79476134/147244452-139d8dd0-e8a1-46d6-85fd-487e56175bcb.png)
![image](https://user-images.githubusercontent.com/79476134/147244457-fcccabe2-0b06-4af6-a655-8503af9aeeef.png)


Доступ к hadoop в браузере и с терминала:Откройте браузер. Доступ к следующему URL-адресу:http://master:9870/dfshealth.html#tab-overview 

![image](https://user-images.githubusercontent.com/79476134/147244473-3307ec54-f93b-4d6f-a908-b666232a557e.png)

•	Подключитесь к NameNode с помощью ssh и запустите команду hdfs dfsadmin -report в отчете, вы должны увидеть количество узлов (Live datanodes) и ваш недавно добавленный узел.
 
 ![image](https://user-images.githubusercontent.com/79476134/147244487-f0bf0f55-7bfe-425c-aac6-c9ef953434b4.png)
![image](https://user-images.githubusercontent.com/79476134/147244500-539d267f-2562-41ed-a2b2-86806f3949d7.png)

hdfs dfsadmin -report   

![image](https://user-images.githubusercontent.com/79476134/147244523-cf057cb0-3bde-4898-b4fb-92469f9541f6.png)
![image](https://user-images.githubusercontent.com/79476134/147244518-49272c5d-c917-4b64-9aa1-82a23c57012a.png)

Папку с идентификатором своей команды:
hadoop fs -mkdir hdfs://master:9820/fadhil_abbas2
hadoop fs -ls /

![image](https://user-images.githubusercontent.com/79476134/147244549-88418dea-f76e-439d-abaf-152bfaefe09b.png)
 

Внутрь папки положите файл с фамилиями участников команды:

  ![image](https://user-images.githubusercontent.com/79476134/147244563-7c9083fd-6bc1-4acb-913c-246cbdfe75de.png)


Вы также можете просматривать файлы в каталоге Hadoop через веб-интерфейс:   

![image](https://user-images.githubusercontent.com/79476134/147244577-e6fb4c41-cfd4-4eea-bd3b-cc536e69f455.png)

