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

Extract the Hadoop folder downloaded. Using the tar command, the file is decompressed.

sudo tar -xvf /home/magna/Downloads/hadoop-3.3.1.tar.gz

![image](https://user-images.githubusercontent.com/79476134/144890205-d1e3366f-221c-44fd-a7c9-1d9221fb2fdf.png)

![image](https://user-images.githubusercontent.com/79476134/144890473-0bc6df70-f486-4beb-b64f-d514a9ca289b.png)

![image](https://user-images.githubusercontent.com/79476134/144891044-b29a5464-15b2-40ea-b0a3-218cbcdc54f4.png)

Setting environment variables for node1
export HADOOP_INSTALL=/usr/local/Hadoop
export PATH=$PATH:$HADOOP_INSTALL/bin
export PATH=$PATH:$HADOOP_INSTALL/sbin

![image](https://user-images.githubusercontent.com/79476134/144891238-c8c061ce-c813-440a-a96f-f5d94f3d7463.png)

source .bashrc                         #(To implement the changes)

hadoop version   

![image](https://user-images.githubusercontent.com/79476134/144891669-7612df39-d8e0-42cf-96e6-aa44cb0d2d99.png)

SSH settings for node1

sudo ufw disable (Disable the firewall)
ssh-keygen -t rsa -P ””

![image](https://user-images.githubusercontent.com/79476134/144891954-a38481bf-dd7d-47a5-8217-c50ffc308755.png)

ls -all .ssh

![image](https://user-images.githubusercontent.com/79476134/144892228-c043b8c1-2d2b-4572-8783-167a26f33860.png)


![image](https://user-images.githubusercontent.com/79476134/144912570-427eca1b-c198-4f11-9762-57ed6f7a9938.png)

sudo ufw disable                        #(Disable the firewall)
ssh-keygen -t rsa -P ””

![image](https://user-images.githubusercontent.com/79476134/144912653-7a91c665-07d1-423f-aafd-5046f908e686.png)

ssh-copy-id -i $HOME/.ssh/id_rsa.pub node1@Node1

ls -all .ssh

![image](https://user-images.githubusercontent.com/79476134/144912858-1d52c016-9817-4bba-9981-86389626b3f3.png)


