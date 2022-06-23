# laradock - dev env

## laradock official
- https://github.com/laradock/laradock
- http://laradock.io

## Implementation
We add this repository as submodule to all our projects.  
For every project there are example files, which could be copied:  
z.B. for project toportal copy .env.toportal.example to .env  
@see Setting up a new project

## Implementation Platreform | Vipany
For platreform | vipany we use the multi project setup, which means the laradock repository
has to be cloned in a separate directory in the ~/Code/platreform:  
```# git clone https://github.com/topoff/laradock.git```  
@see Setting up a new project

## Boot
```# docker-compose up -d nginx mysql php-fpm redis```  
```# docker-compose exec workspace bash```

## Setting up a new project
1. #git submodule add https://github.com/topoff/laradock.git laradock-xxx
2. copy /laradock-xxx/docker-compose.yml.project.example to docker-compose.yml (and edit necessary)
3. copy /laradock-xxx/.env.project.example to .env (and edit necessary)
4. copy /laradock-xxx/nginx/sites/default.conf.example to default.conf (and edit necessary)
5. copy /laradock-xxx/mysql/docker-entrypoint-initdb.d/createdb.sql.project.example to createdb.sql (and edit necessary)
7. sometimes the sub-repo has to be added in PHPStrom > Settings > Version Control > Directory Mappings.

### Then do the usual project stuff
2. update .env from .env.laradock.example
3. run in /laradock-xxx/ ```# docker-compose up -d nginx mysql php-fpm redis```
4. run ```# docker-compose exec workspace bash``` from the laradock-xxx subfolder
6. run ```# composer install```
7. run ```# npm install && npm run dev```
9. add 127.0.0.1 xxx.test to /etc/hosts + ()
10. import data from backup|live: ```# php artisan import:livedb```
13. For horizon run ```# php artisan horizon``` (if you have set QUEUE_CONNECTION=redis in .env)
