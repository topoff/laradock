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
```#docker-compose up -d nginx mysql php-fpm redis```

## Setting up a new project
1. #git submodule add https://github.com/topoff/laradock.git laradock-xxxxxxxxxxxxxxx
2. copy /laradock-xxx/docker-compose.yml.project.example to docker-compose.yml (and edit necessary)
3. copy /laradock-xxx/.env.project.example to .env (and edit necessary)
4. copy /laradock-xxx/nginx/sites/default.conf.example to default.conf (and edit necessary)
5. copy /laradock-xxx/mysql/docker-entrypoint-initdb.d/createdb.sql.project.example to createdb.sql (and edit necessary)
6. add .volumes-data to .gitignore in the main project
7. sometimes the sub-repo has to be added in PHPStrom > Settings > Version Control > Directory Mappings.
