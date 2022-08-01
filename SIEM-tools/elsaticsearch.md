# Installation of the Elastic Stack
The installation instruction is explained [here](https://www.elastic.co/guide/en/elastic-stack/current/installing-elastic-stack.html).

## Server-Side
### Installation of Elasticsearch
1. Follow the instruction [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html)
```bash
# download and install the public signing key
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg

# add the Elasticsearch repository to the source
echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list

# update the system and install Elasticsearch
sudo apt-get update && sudo apt-get install elasticsearch
```
2. Write down the password shown when the installation is finished; always the default superuser is `elastic`.
```bash
--------------------------- Security autoconfiguration information ------------------------------
(...)

The generated password for the elastic built-in superuser is : 4jHQjCytgknDP1c1GT9

(...)
```
3. Enable the Elasticsearch service (auto-start on boot) and start it.
```bash
# reload systemd manager configuration
sudo systemctl daemon-reload
# enable and start the service
sudo systemctl enable elasticsearch.service --now
# in older systems (ver. < 220) enabling and starting the system should be separated; check it by `systemctl --version`
sudo systemctl enable elasticsearch.service && sudo systemctl start elasticsearch.service
```
3.1. Check if it is up and active by visiting `https://localhost:9200/` or the following command.
```bash
curl --cacert /etc/elasticsearch/certs/http_ca.crt -u elastic https://localhost:9200 
```

4. Set Elasticsearch environmental variables; [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/deb.html#deb-configuring) is the list of Elasticsearch environmental variables.
```bash
# add the following lines to the file /etc/environment
# -e parameter takes \n as new line, so, it will add following lines to the file
# ES_HOME=/usr/share/elasticsearch
# ES_PATH_CONF=/etc/elasticsearch
sudo echo -e "ES_HOME=/usr/share/elasticsearch\nES_PATH_CONF=/etc/elasticsearch" >> /etc/environment
# apply changes
source /etc/environment
```

### Installation of Kibana
1. Follow the instruction [here](https://www.elastic.co/guide/en/kibana/current/install.html)
```bash
sudo apt-get install kibana
```
2. Configure Kibana service to start automatically and start it.
```bash
# enable and and start the Kibana
sudo systemctl enable kibana.service --now
# in older systems (ver. < 220) enabling and starting the system should be separated; check it by `systemctl --version`
sudo systemctl enable kibana.service && sudo systemctl start kibana.service
```
2.1. Check if it is up and active by running the following command.
```bash
sudo systemctl status kibana.service
```
3. Set Kibana environmental variables; [here](https://www.elastic.co/guide/en/kibana/current/deb.html#deb-layout) is the list of Kibana environmental variables.
```bash
# add the following lines to the file /etc/environment
# -e parameter takes \n as new line, so, it will add following lines to the file
# KBN_HOME=/usr/share/kibana
# KBN_PATH_CONF=/etc/kibana
sudo echo -e "KBN_HOME=/usr/share/kibana\nKBN_PATH_CONF=/etc/kibana" >> /etc/environment
# apply changes
source /etc/environment
```
4. Open the browser and visit the Kibana webpage (e.g. `http://localhost:5601/`).

4.1. Generate and enrollment token for Kibana and paste it in the webpage.
```bash
sudo $ES_HOME/bin/elasticsearch-create-enrollment-token -s kibana
```
4.2. There is a need to generate a verification code that can be done by running the following command.
```bash
sudo $KBN_HOME/bin/kibana-verification-code
```
5. Enable encryption on Kibana

5.1. Generate and add encryption keys
```bash
sudo $KBN_HOME/bin/kibana-encryption-keys generate -q
```
The output will be 3 lines like followings that should be added to the end of Kibana config file.
```bash
# Used to encrypt stored objects such as dashboards and visualizations
xpack.encryptedSavedObjects.encryptionKey: 6f1690e388765163de1027a0931b2a7c
# Used to encrypt saved reports
xpack.reporting.encryptionKey: 3b4ca4bad51fb6a65aawbfc567a95198a
# Used to encrypt session information
xpack.security.encryptionKey: 8d6cd74eac9c4654eef3a5ec431f84a
```
5.2. Paste the output at the end of the Kibana config file.
```bash
# open the config file
sudo nano $KBN_PATH_CONF/kibana.yml
```
### Make Elasticsearch and Kibana Accessible Remotely
If there is any need to be accessible remotely, uncomment the following line and modify them accordingly.

1. Set the server IP and port accessible remotely by changing parameters in the *Elasticsearch* config file.
```bash
# open the config file
sudo nano $ES_PATH_CONF/elasticsearch.yml
```
And edit the YML config file
```yml
# assure these lines are not commented and the values are correct
network.host: 0.0.0.0
http.port: 9200
```
2. Set the server IP and port accessible remotely by changing parameters in the *Kibana* config file.
```bash
# open the config file
sudo nano $KBN_PATH_CONF/kibana.yml
```
And edit the YML config file
```yml
# assure these lines are not commented and the values are correct
server.host: 0.0.0.0
server.port: 5601

# set the url for Kibana
# if there is any need to get the hostname; the commands `sudo hostname` or `sudo hostnamectl` help
server.publicBaseUrl: "http://kibana:5601"
# set the hostname of the Kibana server
server.name: "kibana"
```
3. Open ports in firewall.
```bash
# to find open ports, in case you do not know port numbers
sudo lsof -i -P -n | grep LISTEN

# allow Kibana and Elasticsearch ports (only TCP) be open on firewall
# it depends on the firewall framework; here is the one for UFW to add rules
sudo ufw allow 5601,9200/tcp
# enable the firewall
sudo ufw enable
# check the status
sudo ufw status
# if there is any need to delete any rule
sudo ufw delete 2 # where 2 is the line number shown in `sudo ufw status`
```

### Installation of Logstash
1. Follow the instruction [here](https://www.elastic.co/guide/en/logstash/current/installing-logstash.html)
```bash
sudo apt-get install logstash
```
2. Configure Logstash service to start automatically and start it.
```bash
# enable and start the Logstach service
sudo systemctl enable logstash.service
# in older systems (ver. < 220) enabling and starting the system should be separated; check it by `systemctl --version`
sudo systemctl enable logstash.service && sudo systemctl start logstash.service
```
2.1. Check if it is up and active by running the following command.
```bash
sudo systemctl status logstash.service
```

### Encrypt the Communications
It is explained [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/security-basic-setup.html) in details.

1. Generate CA for Elasticsearch

1.1. Generate CA for every single node to generate a CA for the cluster by running the following command.
```bash
# default CA filename would be `elastic-stack-ca.p12`
sudo $ES_HOME/bin/elasticsearch-certutil ca
```
1.2. On any single node, generate a certificate and private key for the nodes in your cluster.
```bash
# default certificate filename would be `elastic-certificates.p12`
sudo $ES_HOME/bin/elasticsearch-certutil cert --ca elastic-stack-ca.p12
```
1.3. Copy the certificate to the *Config* folder on any node in the cluster.
```bash
# default certificate filename would be `elastic-certificates.p12`
# there might be a need to create a folder for certificates
sudo mkdir $ES_PATH_CONF/certs
sudo mv $ES_HOME/elastic-*.p12 $ES_PATH_CONF/certs
```
1.3 Change the group and the permission of the certificates.
```bash
# change the group of files to `elasticsearch`
sudo chgrp elasticsearch $ES_PATH_CONF/certs/elastic-certificates.p12 $ES_PATH_CONF/certs/elastic-stack-ca.p12
# change the permission of files to 660
sudo chmod 660 $ES_PATH_CONF/certs/elastic-certificates.p12 $ES_PATH_CONF/certs/elastic-stack-ca.p12
```
1.4. Modify the Elasticsearch config to see the generated certificate.
```bash
# open the config file
sudo nano $ES_PATH_CONF/elasticsearch.yml
```
And edit the YML config file
```yml
# Enable encryption and mutual authentication between cluster nodes
xpack.security.transport.ssl:
  enabled: true
  verification_mode: certificate
  # set the certificate name
  keystore.path: certs/elastic-certificates.p12
  truststore.path: certs/elastic-certificates.p12

# modify the master node name with the hostname; get the hostname by running 'sudo hostname'
cluster.initial_master_nodes: ["kibana"]
```
2. Encrypt HTTP client communications for Elasticsearch

2.1. Generate a Certificate Signing Request (CSR) for any single node an HTTP certificate.
```bash
sudo $ES_HOME/bin/elasticsearch-certutil http
```
2.1.1. Answer questions as follow:
```bash
Generate a CSR? [y/N]                  -> N
Use an existing CA? [y/N]              -> y
# the path of the certificate defined in the step 1.3.
CA Path:                               -> certs/elastic-stack-ca.p12
Generate a certificate per node? [y/N] -> N
hostnames (one per line)               -> kibana
                                          example.com
                                          www.example.com
IP addresses (one per line)            -> 192.168.0.152
(...)
```
2.2. Move generated zip file to the Elasticsearch config folder and unzip it. There are two folders `elasticsearch` and `kibana`, each containing a file: `/elasticsearch/http.p12` and `kibana/elasticsearch-ca.pem`.
```bash
# unzip the file
sudo unzip $ES_HOME/elasticsearch-ssl-http.zip -d ~/elasticsearch-ssl-http
# move the file to the Elasticsearch config folder
# there might be a need to create the folder `certs`
sudo mv ~/elasticsearch-ssl-http/elasticsearch/http.p12 $ES_PATH_CONF/certs/
# move the file to the Kibana config folder
# there might be a need to create the folder `certs`
sudo mkdir $KBN_PATH_CONF/certs && sudo mv ~/elasticsearch-ssl-http/kibana/elasticsearch-ca.pem $KBN_PATH_CONF/certs/
# remove empty folders
sudo rm -r ~/elasticsearch-ssl-http
```
2.3. Change the group and the permission of the certificates.
```bash
# change the group of files to `elasticsearch`
sudo chgrp elasticsearch $ES_PATH_CONF/certs/http.p12
# change the group of files to `kibana`
sudo chgrp kibana $KBN_PATH_CONF/certs/elasticsearch-ca.pem
# change the permission of files to 660
sudo chmod 660 $ES_PATH_CONF/certs/http.p12 $KBN_PATH_CONF/certs/elasticsearch-ca.pem
```
2.4. Modify the Elasticsearch config to see the generated certificate.
```bash
# open the Elasticsearch config file
sudo nano $ES_PATH_CONF/elasticsearch.yml
```
And edit the YML config file
```yml
# Enable encryption for HTTP API client connections, such as Kibana, Logstash, and Agents
xpack.security.http.ssl:
  enabled: true
  keystore.path: certs/http.p12
```
3. Encrypt traffic between Kibana and Elasticsearch

3.1. Modify the Kibana config to set the generated certificate generated in the step 4.2.
```bash
# open the Kibana config file
sudo nano $KBN_PATH_CONF/kibana.yml
```
And edit the YML config file
```yml
elasticsearch:
  # HTTPS URL for your Elasticsearch cluster
  hosts: ['https://192.168.0.152:9200','https://kibana:9200']
  # full path to the Elasticsearch certificate (.pem file) that is generated in the step 2
  ssl.certificateAuthorities: [/etc/kibana/certs/elasticsearch-ca.pem]
```
4. Run the following commands to store any certificate password in the Elasticsearch keystore; if no password is set, just run commands and press Enter (empty) as the password.
```bash
# if any password is set for the CA file
sudo $ES_HOME/bin/elasticsearch-keystore add xpack.security.transport.ssl.keystore.secure_password
sudo $ES_HOME/bin/elasticsearch-keystore add xpack.security.transport.ssl.truststore.secure_password

# if any password is set for the certificate
sudo $ES_HOME/bin/elasticsearch-keystore add xpack.security.http.ssl.keystore.secure_password
```
5. Encrypt traffic between browsers and Kibana

5.1. Generate a server certificate and private key for Kibana.
```bash
# hostname: kibana / dns: www.example.com and example.com
# CA should be the one generated in the step 1.1
sudo $ES_HOME/bin/elasticsearch-certutil cert -pem --ca $ES_PATH_CONF/certs/elastic-stack-ca.p12 -name kibana -dns example.com,www.example.com
```
5.2. Move generated zip file to the Elasticsearch config folder and unzip it.
```bash
# unzip the file
sudo unzip $ES_HOME/certificate-bundle.zip -d ~/certificate-bundle
# move the file to the Kibana config folder; here $(hostname) is 'kibana'
sudo mv ~/certificate-bundle/$(hostname)/*.* $KBN_PATH_CONF/certs/
# remove empty folders
sudo rm -r ~/certificate-bundle
```
5.3. Change the group and the permission of the certificates.
```bash
# change the group of files to `kibana`; here $(hostname) is 'kibana'
sudo chgrp kibana $KBN_PATH_CONF/certs/$(hostname).crt $KBN_PATH_CONF/certs/$(hostname).key
# change the permission of files to 660; here $(hostname) is 'kibana'
sudo chmod 660 $KBN_PATH_CONF/certs/$(hostname).crt $KBN_PATH_CONF/certs/$(hostname).key
```
5.4. Modify the Kibana config to set the generated certificate generated in the step 5.1.1.
```bash
# open the config file
sudo nano $KBN_PATH_CONF/kibana.yml
```
And edit the YML config file
```yml
server.ssl
  enabled: true
  certificate: /etc/kibana/certs/kibana.crt
  key: /etc/kibana/certs/kibana.key
```

#### Additional Settings
1. Add virtual memory by increase the value of `vm.max_map_count` in the file `/etc/sysctl.conf` to increase speed of Elasticsearch. It can be done by the following command.
```bash
sudo sysctl -w vm.max_map_count=262144
```
2. Set the maximum threat to 4096 in the file `/usr/lib/systemd/system/elasticsearch.service` for users including `root`. It should be `LimitNPROC=4096`.


## Client-side
### Installation of Beats
Beats are agents installed on clients to send logs to either Logstash or directly to Elasticsearch.

It depends on what kind of *Beat* is going to be installed, [here](https://www.elastic.co/guide/en/beats/libbeat/current/beats-reference.html) is the reference and [here](https://www.elastic.co/guide/en/elastic-stack-get-started/8.1/get-started-elastic-stack.html#install-beats) is the instruction to install them.

#### Installation of Packetbeat
Packetbeat sends network packets to Elasticsearch for analysis.

1. Follow the instruction [here](https://www.elastic.co/guide/en/beats/packetbeat/current/packetbeat-installation-configuration.html)
```bash
# install libpcap packet capture library
sudo apt-get install libpcap0.8
# download and install Packetbeat
curl -L -O https://artifacts.elastic.co/downloads/beats/packetbeat/packetbeat-8.1.2-amd64.deb
sudo dpkg -i packetbeat-8.1.2-amd64.deb
```
2. Change the Packetbeat configuration.
```bash
# open the config file
sudo nano /etc/packetbeat/packetbeat.yml
```
And edit the YML config file
```yml
# assure these lines are not commented and the values are correct

# set the network interface that needs to be captured; "any" means all.
packetbeat.interfaces.device: any

# set the Kibana address
setup.kibana:
  # Scheme and port can be left out and will be set to the default (http and 5601)
  host: "http://192.168.0.152:5601"

# set the Elasticsearch address
output.elasticsearch:
  # Array of hosts to connect to.
  hosts: ["192.168.0.152:9200"]
  protocol: "https"
  # Authentication credentials - either API key or username/password.
  #api_key: "id:api_key"
  username: "elastic"
  password: "m2_hl=1dO6R_7bjBwEj7"
  
  ssl.verification_mode: "none"
```
3. Configure Packetbeat service to start automatically and start it.
```bash
# enable and start the Packetbeat service
sudo systemctl enable packetbeat --now
# in older systems (ver. < 220) enabling and starting the system should be separated; check it by `systemctl --version`
sudo systemctl enable packetbeat && sudo systemctl start packetbeat
```
4. Check if the config file is properly formed and the connection to Elasticsearch is up and running.
```bash
# check the config file
sudo packetbeat test config
# check the connection
sudo packetbeat test output
```
5. Install dashboards on Kibana
```bash
sudo packetbeat setup
```

### Auto-start VirtualBox VM on boot
If the Elasticsearch server is installed on VirtualBox, there is a need to run it automatically. The configuration is explained [here](https://www.virtualbox.org/manual/ch09.html#autostart).
1. Create a virtualbox auto start folder and a configuration file.
```bash
# create the autostart folder
sudo mkdir /etc/vbox
# create the config file
sudo nano /etc/default/virtualbox
```
2. Add the following entries
```bash
# an absolute path to the autostart database directory
VBOXAUTOSTART_DB=/etc/vbox
# points the service to the autostart configuration file
VBOXAUTOSTART_CONFIG=/etc/vbox/autostart.cfg
```
3. Provide Access to your user in the autostart configuration.
```bash
sudo nano /etc/vbox/autostart.cfg
```
3.1. Add the following lines in the file.
```
# Default policy is to deny starting a VM for all users.
default_policy = deny
# <USERNAME> is allowed to start virtual machines with 0s delay
<USERNAME> = {
  allow = true
  startup_delay = 0
}
```
4. Ensure correct access is present
```bash
# change the group of the folder to "vboxusers"
sudo chgrp -R vboxusers /etc/vbox
# change the folder permission; it needs to support sticky bit (having 't' at the end of permission)
# if there is no sticky bit, just go for `sudo chmod +t /etc/vbox`
sudo chmod -R 1777 /etc/vbox
# check if the permission is right
ls -ld /etc/vbox/
# add the user to the group "vboxusers"
sudo usermod -aG vboxusers <USERNAME>
# to confirm the membership
groups <USERNAME>
```
5. Set the virtualbox VM properties. These commands should not run by admin (sudo).
```bash
# set the path to the autostart database folder
VBoxManage setproperty autostartdbpath /etc/vbox
# list all VMs to get VM names and UUIDs
VBoxManage list vms
# enable VM autostart feature
VBoxManage modifyvm <VM_NAME_or_UUID> --autostart-enabled on
```
6. Restart virtualbox auto start service
```bash
sudo service vboxautostart-service restart
```
#### Troubleshooting
- If there is any error like `VBoxManage: error: Adding machine 'VM_NAME' to the autostart database failed with VERR_ACCESS_DENIE`, then there might be an issue with the permission.
  - Check if the ownership of `/etc/vbox` is correct or not. It should belongs to `vboxusers`; it should be the same for all files in it.
  - Check if the permission of `/etc/vbox` is correct or not. It should support sticky bit; it should be the same for all files in it.
  - Check if the user (`USERNAME`) is member of the group `vboxusers`.
- If there is any error like `Failed to start vboxautostart-service.service: Unit vboxautostart-service.service not found` or `Unit vboxautostart-service.service could not be found`, then there is an issue with installation of the service. With the following command, it could be installed.
```bash
# define the list of services
services=(vboxautostart-service vboxweb-service vboxballoonctrl-service)
# define the the URL for downloading services
base_url="https://www.virtualbox.org/svn/vbox/trunk/src/VBox/Installer/linux"
# download the 
for service in "${services[@]}"
    do
      sudo wget "${base_url}/${service}".sh -O "/etc/init.d/${service}" \
      && sudo chmod +x "$service"  \
      && sudo update-rc.d "$service" defaults 90 10
    done
 
# check if services are installed
service --status-all | grep vbox
```
