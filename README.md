# PostgresSQL

## To provide specific image locale go to postgreSQL-docker-image/docker-compose.yaml and add one or a few environment values listed below:
- LC_COLLATE 	String sort order
- LC_CTYPE 	Character classification (What is a letter? Its upper-case equivalent?)
- LC_MESSAGES 	Language of messages
- LC_MONETARY 	Formatting of currency amounts
- LC_NUMERIC 	Formatting of numbers
- LC_TIME 	Formatting of dates and times

![Screenshot 2023-01-29 at 20 31 54](https://user-images.githubusercontent.com/59523003/215344728-8345b527-5b73-4922-a805-954860d0e231.png)

## You also need to change following Docker settings to use specific locale for your database in postgreSQL-docker-image/Dockerfile
![Screenshot 2023-01-29 at 20 34 20](https://user-images.githubusercontent.com/59523003/215344858-fda84ae3-8c50-42ad-9cf0-a761eca71428.png)

## If you only need support of russian locale use command below to run docker container with your credentials:
docker run --name yourContainerName -e POSTGRES_USER=userName -e POSTGRES_PASSWORD=userPassword -e POSTGRES_DB=nameOfDatabase -p 5432:5432 -d artvs18/postgres

## As example of how to set image to de_DE locale follow this steps:

> Clone repo

#### git clone "https://github.com/artvs18/postgreSQL-docker-image.git"

> Change locale environment settings in postgreSQL-docker-image/docker-compose.yaml
<img width="482" alt="Screenshot 2023-01-29 at 21 37 19" src="https://user-images.githubusercontent.com/59523003/215348363-ae926802-9eab-4171-8038-de7db53ac577.png">

> Change global locale environment setting in postgreSQL-docker-image/Dockerfile
<img width="675" alt="Screenshot 2023-01-29 at 21 37 48" src="https://user-images.githubusercontent.com/59523003/215348395-d1703477-b431-404f-b890-f47a2cf8364c.png">

> If you want, you also can change image name in postgreSQL-docker-image/Makefile
<img width="483" alt="Screenshot 2023-01-29 at 21 38 04" src="https://user-images.githubusercontent.com/59523003/215348403-4906152e-9c2e-4d06-8d25-fd824d3324b3.png">

> Use command below to build your image:

docker build -t artvs18/postgresss .

> Run yout custom docker image:

docker run --name yourContainerName -e POSTGRES_USER=userName -e POSTGRES_PASSWORD=userPassword -e POSTGRES_DB=nameOfDatabase -p 5432:5432 -d artvs18/postgresss

## Feel free to customize this image as you want!
