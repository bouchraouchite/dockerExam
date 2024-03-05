# dockerExam

Exercice 1 :

docker build -t imageexam .

Exercice 2 :

docker build -t mysql .
docker run mysql
docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD= -e MYSQL_DATABASE=dbtest mysql:latest
docker run -d --name backend-container --link mysql-container:mysql tuto-backend
docker run -d --name frontend-container -p 80:80 --link backend-container:backend tuto-frontend

docker run -d --name mysql --network imageexam -e MYSQL_ROOT_PASSWORD= -e MYSQL_DATABASE=testdb mysql:latest

docker run -d -v 8089:80 imageexam
docker-compose up
