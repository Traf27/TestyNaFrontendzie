# TestyNaFrontendzie

### Uruchamianie frontendu w Dockerze
1. Pobierz i zainstaluj Dockera dla swojego systemu z www.docker.com/get-started
2. Uruchom Dockera
3. Przejdz do katalogu web i wpisz następujące komendy
#### Windows
```shell
docker build -t frontend-app-image .
```
```shell
# powershell
docker run -it --rm -v ${PWD}/src:/app/src -p 3000:3000 --name frontend-app frontend-app-image
```
```shell
# windows cmd
docker run -it --rm -v %cd%/src:/app/src -p 3000:3000 --name frontend-app frontend-app-image
```

#### Linux/MacOS
```shell
docker build -t frontend-app-image .
docker run -it --rm -v $(PWD)/src:/app/src -p 3000:3000 --name frontend-app frontend-app-image
```
3. Odwiedzamy stronę http://localhost:3000
4. Zmiany w kodzie odzwierciedlane są na stronie, tak jakbyśmy odpalili nasza aplikacje na localu

#### Dostęp do bash'a wewnątrz kontenera
```shell
 docker exec -it frontend-app /bin/bash
```

### Problemy
#### Windows
#### Jeśli nie odświeża zawartości na stronie, zmodyfikuj komendę ```docker run``` dodając:
```shell
-e CHOKIDAR_USEPOLLING=true
```
```shell
# powershell
docker run -it --rm -v ${PWD}/src:/app/src -p 3000:3000 --name frontend-app frontend-app-image -e CHOKIDAR_USEPOLLING=true
# cmd
docker run -it --rm -v %cd%/src:/app/src -p 3000:3000 --name frontend-app frontend-app-image -e CHOKIDAR_USEPOLLING=true
```

żródło https://stackoverflow.com/questions/44643045/running-development-server-with-create-react-app-inside-of-a-docker-container