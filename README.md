# Oficjalne obrazy Dockera dla systemu OpenKp

## Instrukcja

. Jeżeli używasz Windowsa zainstaluj boot2docker zgodnie z instrukcją na http://blog.arungupta.me/2014/07/getting-started-with-docker/

## Dostępne obrazy

### Pobieranie obrazów
. openkp/openkp podstawowy - obraz korzystający z Wildfly i wbudowanej bazy : `docker pull openkp/openkp`
. openkp/openkp-mysql - obraz korzystający z Wildfly i łączący się do bazy MySQL `docker pull openkp/openkp-mysql`

### Uruchomienie kontenera
. Uruchomienie podstawowego obrazu : `docker run -it -p 80:8080 openkp/openkp`
. Uruchomienie obrazu z mysql:  
	`docker run --name openkpdb -e MYSQL_USER=mysql -e MYSQL_PASSWORD=mysql -e MYSQL_DATABASE=sample -e MYSQL_ROOT_PASSWORD=supersecret -d mysql`
	`docker run --name openkpwildfly --link openkpdb:db -it -p 80:8080 openkp/openkp-mysql`
. Dostęp do aplikacji http://<IP>/openkp
