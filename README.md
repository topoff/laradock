# laradock - dev env

## laradock official
- https://github.com/laradock/laradock
- http://laradock.io

## Implementation
We add this repository as submodule to all our projects.  
For every project there are example files, which could be copied:
z.B. for project toportal copy .env.toportal.example to .env

## Implementation Platreform | Vipany
For platreform | vipany we use the multi project setup, which means the laradock repository
has to be cloned in a separate directory in the ~/Code/platreform:  
```# git clone https://github.com/topoff/laradock.git```

## Setting up a new project
1. #git submodule add https://github.com/topoff/laradock.git laradock-xxxxxxxxxxxxxxx
2. edit /laradock-xxx/.env (important -> set DATA_PATH_HOST=~/Code/your-project/.laradock/data)
3. edit /laradock-xxx/mysql/docker-entrypoint-initdb.d/createdb.sql
4. add .laradock to .gitignore in the main project
5. sometimes the sub-repo has to be added in PHPStrom > Settings > Version Control > Directory Mappings.
