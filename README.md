# magento-docker
#### How to use:
1. copy config/swag/magento.subdomain.conf.dist to config/swag/magento.subdomain.conf
2. edit line 7 of magento.subdomain.conf to your server FQDN: ****server_name server.domain.com;**** 
3. Copy .env.dist to .env
4. Edit .env with relevent info
5. docker-compose up -d nginx

console ssh requires key based authentication
1. mkdir data/magento/.ssh
2. chown 33:33 data/magento/.ssh
3. add your public key to .ssh/authorized_keys

### future improvemets:
* create user environment for console user with zsh, oh-my-zsh, pre-populated authorized_keys
