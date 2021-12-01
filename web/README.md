# TestyNaFrontendzie

### Uruchamianie frontendu w Dockerze
1. Pobierz i zainstaluj Dockera dla swojego systemu z www.docker.com
2. Przejdz do katalogu web i wpisz następujące komendy
#### Windows
```shell
docker build -t frontend-app-image .
docker run -it --rm -v ${PWD}/src:/app/src -p 3000:3000 --name frontend-app frontend-app-image
```

#### Linux/MacOS
```shell
docker build -t frontend-app-image .
docker run -it --rm -v $(PWD)/src:/app/src -p 3000:3000 --name frontend-app frontend-app-image
```

#### opening bash inside container
```shell
# Enter the container
$ docker exec -it frontend-app /bin/bash
```
