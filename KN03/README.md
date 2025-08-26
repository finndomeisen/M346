# KN03

## Wichtige Commands

- `sudo apt update`  
  → Pakete/Software aktualisieren  

- `sudo apt install apache2`  
  → Apache Webserver installieren  

- `sudo apt install php`  
  → PHP Applikationsserver installieren  

- `sudo apt install libapache2-mod-php`  
  → PHP-Erweiterung für Apache installieren  

- `sudo apt install mariadb-server`  
  → Datenbankserver installieren  

- `sudo apt install php-mysqli`  
  → PHP-Modul für DB-Abfragen installieren  

- `sudo mysql -sfu root -e "GRANT ALL ON *.* TO 'admin'@'%' IDENTIFIED BY 'Ihr-Passwort' WITH GRANT OPTION;"`  
  → Neuen Benutzer `admin` mit Passwort erstellen (**Passwort anpassen!**)  

- `sudo systemctl restart mariadb.service`  
  → DB-Server neu starten  

- `sudo systemctl restart apache2`  
  → Webserver neu starten  

- `cd ~`  
  → Ins Home-Verzeichnis wechseln  

- `git clone https://gitlab.com/ch-tbz-it/Stud/m346/m346scripts.git`  
  → Repository klonen  

- Dateien in `./m346scripts/KN03/` ansehen  
  → Eine Datei muss angepasst werden  

- `sudo cp ./m346scripts/KN03/*.php /var/www/html/`  
  → PHP-Dateien ins Webserver-Verzeichnis kopieren  
