# libc-database web service development

## Local deployment

1. Populate libc db with `./get` or `./add`.

1. Start the server with docker (must be run from the `searchengine/` directory):

	```sh
	docker-compose up --build
	```

1. Install pip dependencies from `requirements.txt`.

	Example with venv:

	```sh
	python -m venv venv
	. venv/bin/activate
	pip install -U pip
	pip install -U -r requirements.txt
	```

1. Index libc db in elasticsearch (must be run from the `searchengine/` directory):

	```sh
	python -m index ../db
	```

### Cleaning up

To remove all development files run:

```sh
docker-compose down --volumes --rmi all
```


## UWSGI logging

To get app logs from UWSGI:

```sh
docker logs searchengine_uwsgi_1
```
