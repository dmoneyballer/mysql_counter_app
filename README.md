# mysql_counter_app
a docker compose example that creates a mysql database and a flask app. the application counts the number of times the page has been refreshed.
To run it you need to add a settings.py file that has a SECRET_KEY, DB_USERNAME, DB_PASSWORD, DATABASE_NAME, DB_HOST, DB_URI, SQLALCHEMY_DATABASE_URI with values set
then run docker-compose build
after it builds you can run docker-compose up 
when the container is up you need to exec in and run the dbinit.py
to do that run docker exec -it counterapp_web_1 python dbinit.py
then you should be able to hit localhost:5000 and see the counter go up each time you refresh.

Note if you are going to build this on anything with an arm-based cpu, go into the docker-compose.yml and change the db image from mysql:5.7 to ebspace/aarch64-mysql.
^this was learned installing this an arm-based chromebook
