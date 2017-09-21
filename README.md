# osm_rabbitmq
Ansible Roles for creating Rabbitmq-Server on Linux distribution(Ubuntu 14,16)

RabbitMQ is the most popular open source message broker. RabbitMQ is a lightweight application available for most of the popular operating systems. RabbitMQ supports multiple messaging protocols. RabbitMQ can be easily deployed in a distributed and federated configurations to meet high-scale, high-availability requirements. This Role will help you to install RabbitMQ on Ubuntu 16.04 LTS and 14.04 LTS systems.

#Manual Steps 

Prerequisite Package :
ErlangDb

sudo apt-get update -y
wget http://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc
sudo apt-key add erlang_solutions.asc
sudo apt-get update -y
sudo apt-get install erlang erlang-nox -y

Installation Of RabbitMQ-Server :
 
echo "deb http://www.rabbitmq.com/debian/ testing main" >> sudo /etc/apt/sources.list
wget https://www.rabbitmq.com/rabbitmq-signing-key-public.asc
sudo apt-key add rabbitmq-signing-key-public.asc
sudo apt-get update -y
sudo apt-get install rabbitmq-server -y

 Starting Service :
sudo systemctl start rabbitmq-server
sudo systemctl enable rabbitmq-server
sudo systemctl status rabbitmq-server

Enabling UI Management Console :
sudo rabbitmq-plugins enable rabbitmq_management

Creating Admin User :
sudo rabbitmqctl add_user radmin radmin
sudo rabbitmqctl set_user_tags radmin administrator
sudo rabbitmqctl set_permissions -p / radmin ".*" ".*" ".*"

Port Requirements :

5671,5672 For rabbitmq Amqp 
15672 Management Console Access
25672 for Cluster Management and Erlang Distribution
4369 Empd

To use this Role
cp -r rabbitmq $Ansible-Home:roles/

Run this command to your ansible server
#ansible-playbook rmq.yml 

Access Rmq-Server with Ip  :

<IP-Address>:15672  
you will get a login page enter u-name and password.

Enjoy your work .

