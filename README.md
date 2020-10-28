# Stackstorm 3.1.0 installation
curl -sSL https://raw.githubusercontent.com/nawed005/Stackstorm_installation/master/st2_bootstrap.sh | bash -s -- --user=st2admin --password='Ch@ngeMe'

# Changed StackStorm Password
echo '123456' | sudo htpasswd -i /etc/st2/htpasswd st2admin

# Allow firewall to allow WEbUI
firewall-cmd --zone=public --add-service=http --add-service=https
firewall-cmd --zone=public --permanent --add-service=http --add-service=https

# CentOS7 Allo firewall to open a port
firewall-cmd --zone=public --permanent --add-port=5000/tcp
firewall-cmd --reload

