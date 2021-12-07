Лабораторная работа №2

Задание 0
Задача подготовить полигон

1.Установить и настроить кластер HDFS согласно инструкции Cluster и примеру
2.Воспроизвести схему кластера из презентации (Лабораторная №2)
3.Настроить NameNode и один DataNode

fadhil_node1:192.168.68.142
![image](https://user-images.githubusercontent.com/79476134/144881182-2db0b0cd-baaf-487d-9d5b-b0d83a201e04.png)
fadhil_ndoe2:192.168.68.143
![image](https://user-images.githubusercontent.com/79476134/144881341-d7b22480-c13e-4f8b-a83f-ca8c0cc6524b.png)
fadhil_master:192.168.68.144
![image](https://user-images.githubusercontent.com/79476134/144885876-11722d97-7da4-4658-83ae-3c13e848e415.png)


sudo nano /etc/hosts

![image](https://user-images.githubusercontent.com/79476134/144924871-e81bed19-f0b9-4230-8b94-890a028b4a67.png)


ping all nodes 

![image](https://user-images.githubusercontent.com/79476134/144925044-57d2f9ff-e06f-46ae-a5e6-dae7070794ae.png)

ufw disable

![image](https://user-images.githubusercontent.com/79476134/144925175-dab7ec2b-3d36-4131-a587-d9092c958585.png)

Installing SSH, Java

sudo apt install openssh-server

![image](https://user-images.githubusercontent.com/79476134/144925454-8718b39e-922d-466f-9935-d1e8ea574ca2.png)


sudo apt install openjdk-8-jdk

![image](https://user-images.githubusercontent.com/79476134/144925654-20c25335-7575-4270-bdfb-8f341ab2c668.png)


Download the below file on node 1

 https://downloads.apache.org/hadoop/common/hadoop-3.3.1/hadoop-3.3.1.tar.gz
 
 visudo
 
![image](https://user-images.githubusercontent.com/79476134/144928115-b0a469a0-2809-4fa7-9f8b-5561a89cdaf5.png)


export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin

![image](https://user-images.githubusercontent.com/79476134/144886991-6ed39ab8-f01c-423a-a94f-45e8d7c98dcb.png)

source .bashrc
java -version
echo $JAVA_HOME 

![image](https://user-images.githubusercontent.com/79476134/144887282-a446b3ad-5ccf-4830-bc44-2333b286e2ad.png)

sudo apt install vim

nano .bashrc
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin

![image](https://user-images.githubusercontent.com/79476134/144928822-ab26ca73-be5a-411a-9161-281c740d8bd3.png)

![image](https://user-images.githubusercontent.com/79476134/144888967-22d23c33-4bbf-4fa3-b8cf-ff9264914cae.png)

Extract the Hadoop folder downloaded. Using the tar command, the file is decompressed.

sudo tar -xvf /home/magna/Downloads/hadoop-3.3.1.tar.gz

![image](https://user-images.githubusercontent.com/79476134/144929328-3a96a8a6-0aec-4f1f-a8dd-c79b5ef7a591.png)

![image](https://user-images.githubusercontent.com/79476134/144929643-ddcb4f69-0b28-4a32-9222-676d3bcb7cc3.png)

Setting environment variables for node1
export HADOOP_INSTALL=/usr/local/hadoop
export PATH=$PATH:$HADOOP_INSTALL/bin
export PATH=$PATH:$HADOOP_INSTALL/sbin

![image](https://user-images.githubusercontent.com/79476134/144891238-c8c061ce-c813-440a-a96f-f5d94f3d7463.png)

source .bashrc                         #(To implement the changes)

hadoop version   

SSH settings for node1

sudo ufw disable (Disable the firewall)
ssh-keygen -t rsa -P ””

ls -all .ssh

![image](https://user-images.githubusercontent.com/79476134/144930544-6781c1bf-be09-4020-9e0a-f930740e534b.png)

ssh-copy-id -i $HOME/.ssh/id_rsa.pub fadhil@fadhil_node2

![image](https://user-images.githubusercontent.com/79476134/144930566-7f0f350d-04bb-462b-84b2-6adabf92af52.png)

fadhil_node2:

sudo ufw disable                        #(Disable the firewall)
ssh-keygen -t rsa -P ””

![image](https://user-images.githubusercontent.com/79476134/144912653-7a91c665-07d1-423f-aafd-5046f908e686.png)

ssh-copy-id -i $HOME/.ssh/id_rsa.pub fadhil@fadhil_node1

ls -all .ssh
![image](https://user-images.githubusercontent.com/79476134/144931204-49e58937-90f4-4b5d-85c4-673d5c4308c8.png)

from fadhil_node1:
ssh fadhil_node2
![image](https://user-images.githubusercontent.com/79476134/144931501-f2227333-7c6c-407c-9f5f-609873f734af.png)

from fadhil_node2:
ssh fadhil_node1
![image](https://user-images.githubusercontent.com/79476134/144931593-91daeb9e-369e-4851-bdf0-e8c19aa8082d.png)


cat $HOME/.ssh/id_rsa.pub>>$HOME/.ssh/authorized_keys

![image](https://user-images.githubusercontent.com/79476134/144932857-bf3fd24f-b935-4e24-af73-19abdfc01131.png)

scp /home/fadhil/Downloads/hadoop-3.3.1.tar.gz fadhil@fadhil_node2:/tmp

![image](https://user-images.githubusercontent.com/79476134/144932805-0cdf7ed0-2189-46e8-935e-e0564e347db9.png)

on fadhil_node2:
![image](https://user-images.githubusercontent.com/79476134/144932982-6c6426fb-503c-429d-bb0d-3aeda781f3fb.png)

sudo tar -xvf /tmp/hadoop-3.3.1.tar.gz

ls -all

![image](https://user-images.githubusercontent.com/79476134/144933143-cb7d567b-f80f-4491-a251-0d801f66ad12.png)

The decompressed folder is now present in the /usr/local.

sudo ln -s hadoop-3.3.1 hadoop
sudo chown -R fadhil:fadhil hadoop*
ls -all

![image](https://user-images.githubusercontent.com/79476134/144933354-d62bad6a-3cd7-4c67-8e61-6d0278a8ce8c.png)

fadhil_node1:
scp .bashrc fadhil@fadhil_node2:/home/fadhil
![image](https://user-images.githubusercontent.com/79476134/144933599-b9b237dd-fb68-4a16-b912-c666431f353d.png)

fadhil_node2:

![image](https://user-images.githubusercontent.com/79476134/144933691-36512394-cf92-464b-a7d7-7c12a8392714.png)

![image](https://user-images.githubusercontent.com/79476134/144933782-94825ded-f092-482b-a286-d9679e69b4c8.png)


config core-site.xml
sudo nano core-site.xml
![image](https://user-images.githubusercontent.com/79476134/145017093-15220c70-b7ee-4406-a64a-dcfb5ff03cdd.png)



sudo nano hdfs-site.xml

![image](https://user-images.githubusercontent.com/79476134/144934475-2e0b1dc3-e677-459d-9067-db29d2179415.png)

sudo nano yarn-site.xml

![image](https://user-images.githubusercontent.com/79476134/144934973-a5329f61-c2a9-4309-b40a-536cf028be01.png)

sudo nano mapred-site.xml

![image](https://user-images.githubusercontent.com/79476134/145017454-a53e65d0-d9db-4b91-a6cd-f1ab3f6c8bd1.png)

![image](https://user-images.githubusercontent.com/79476134/145017687-582942ba-020c-4e4a-8142-8916d7dd6d8e.png)

![image](https://user-images.githubusercontent.com/79476134/145017892-005077a8-af05-4160-be94-b9497c6cb03f.png)

do same for fadhil_node2:
![image](https://user-images.githubusercontent.com/79476134/145018574-840721e6-35b5-4df5-9b67-af6b1b2a89da.png)

![image](https://user-images.githubusercontent.com/79476134/145018694-cb4503ab-42d6-440d-9c83-35107e024949.png)

![image](https://user-images.githubusercontent.com/79476134/145018835-4c082a20-df01-467d-9daa-16fbac13a2de.png)

![image](https://user-images.githubusercontent.com/79476134/145019000-1a844d48-2fe5-4258-a9be-80351535c55c.png)


