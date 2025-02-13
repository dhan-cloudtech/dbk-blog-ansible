# dbk-blog
Admin site login
username -> admin 
password -> admin

# migrating data
docker compose exec blog-web python /code/manage.py makemigrations
docker compose exec blog-web python /code/manage.py migrate

docker compose exec blog-web python -Xutf8 /code/manage.py dumpdata --indent=2 --output=mysite_data.json

docker compose exec blog-web python /code/manage.py loaddata mysite_data.json

docker compose exec blog-web python /code/manage.py collectstatic --noinput