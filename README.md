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
## Feel free to customize this image as you want!

