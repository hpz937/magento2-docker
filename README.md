# magento-docker
#### How to use:
1. copy config/swag/magento.subdomain.conf.dist to config/swag/magento.subdomain.conf
2. edit line 7 of magento.subdomain.conf to your server FQDN: **server_name server.domain.com;**
3. Copy .env.dist to .env
4. Edit .env with relevent info
5. `docker-compose up -d swag`
6. `docker exec -it console /first_run.sh`
7. copy magento files and db backup to data/magento/web/

**ssh to console via: `ssh magento@server.example.com -p 222`**

#### Install Magento
1. Copy existing Magento 2 files and db backup to /srv/magento/web 
 * Setup db config: `n98-magerun2 setup:config:set --db-host=mysql --db-name=MysqlDBName --db-user=mysqlDBUser --db-password=mysqlDBPassword`
 * Import db run: `n98-magerun2 db:import`
 * Setup redis config: `n98-magerun2 setup:config:set --cache-backend=redis --cache-backend-redis-server=redis-config-cache --cache-backend-redis-port=6381 --page-cache=redis --page-cache-redis-server=redis --page-cache-redis-port=6379 --session-save=redis --session-save-redis-host=redis-session --session-save-redis-port=6380`
2. Or install new instance of Magento 2
```bash
bin/magento setup:install \
--base-url=https://server.example.com \
--db-host=mysql \
--db-name=mysqlDBName \
--db-user=mysqlUserName \
--db-password=mysqlDBPassword \
--admin-firstname=admin \
--admin-lastname=admin \
--admin-email=admin@example.com \
--admin-user=admin \
--admin-password=admin123 \
--language=en_US \
--currency=USD \
--timezone=America/Chicago \
--use-rewrites=1 \
--backend-frontname=m2admin \
--elasticsearch-host=elastic \
--session-save=redis \
--session-save-redis-host=redis \
--session-save-redis-db=1 \
--cache-backend=redis \
--cache-backend-redis-server=redis \
--cache-backend-redis-db=2 \
--page-cache=redis \
--page-cache-redis-server=redis \
--page-cache-redis-db=3
```
