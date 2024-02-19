# Docker Project
himanshu
<br>This project is consist of two environments in docker.</br>
# 1. MySql
<br>Used to store the backend part of host website.</br>
# 2. Wordpress
<br>Main host website.</br>

![Docker](https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSWDPX2omT-_AXyB3eE07KeJM5wm5FF6jL5xA&usqp=CAU)

```YAML
  
version: '3.8'

services:
  wordpress:
    image: wordpress:latest
    ports:
      - "6080:80"
    environment:
      WORDPRESS_DB_HOST: mysql
      WORDPRESS_DB_USER: wordpress
      WORDPRESS_DB_PASSWORD: wordpress
      WORDPRESS_DB_NAME: wordpress
    volumes:
      - C:\Users\hp\Desktop\docker-compose\Wordpress\wordpress_data:/var/www/html
    networks:
      - wordpress_network

  mysql:
    image: mysql:latest
    environment:
      MYSQL_ROOT_PASSWORD: root_password
      MYSQL_DATABASE: wordpress
      MYSQL_USER: wordpress
      MYSQL_PASSWORD: wordpress
    volumes:
      - C:\Users\hp\Desktop\docker-compose\Wordpress\mysql_data:/var/lib/mysql
    networks:
      - wordpress_network

networks:
  wordpress_network:
    driver: bridge

volumes:
  wordpress_data:
  mysql_data:
```
