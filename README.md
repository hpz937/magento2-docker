# magento-docker
#### How to use:
1. copy config/swag/magento.subdomain.conf.dist to config/swag/magento.subdomain.conf
2. edit line 7 of magento.subdomain.conf to your server FQDN: ****server_name server.domain.com;****
3. Copy .env.dist to .env
4. Edit .env with relevent info
5. docker-compose up -d swag
6. docker exec -it console /first_run.sh
7. copy magento files and db backup to data/magento/web/

**** ssh to console via: ssh magento@server.example.com -p 222 ****

* Once logged in run: n98-magerun2 db:import
