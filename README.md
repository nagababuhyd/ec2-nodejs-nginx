https://medium.com/@a_farag/deploying-a-node-js-project-with-pm2-in-production-mode-fc0e794dc4aa
####################################################################################

steps
setup ec2
git clone https://github.com/nagababuhyd/ec2-nodejs-apache2/
cd ec2-nodejs-apache2
sudo apt update && sudo apt upgrade -y
# Install curl if missing
sudo apt install -y curl

# Add NodeSource repository for Node 20 LTS
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

# Install Node.js and npm
sudo apt install -y nodejs

node -v
npm -v

npm install -g pm2
pm2 start ecosystem.config.js

pm2 stop all

pm2 start my-app

pm2 logs
curl localhost:3000

enable port 22 80 3000 in security groups


################


install apache web server for multiple req acts as proxy and load balancer for nodejs app
access app with public ip

######################

install certbot for http url free ssl
