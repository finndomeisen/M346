# KN03

Kurze Erklärung was Ihre SQL-Abfrage (SELECT-Statement) ausliest:

Die SQL-Abfrage zeigt mir alle Datenbank-User an, die auf dem Server existieren. So sehe ich z. B. den User `admin`, den ich vorher erstellt habe, oder auch `root`. Damit kann ich checken, ob die Verbindung zur Datenbank richtig funktioniert.




![Websiten Testen](https://github.com/finndomeisen/M346/blob/main/KN03/img/Website_Testen.png)
![Website Testing](https://github.com/finndomeisen/M346/blob/main/KN03/img/Website_Testing.png)

![Sql Login](https://github.com/finndomeisen/M346/blob/main/KN03/img/Sql_Login.png)

![Sicherheitsgruppen](https://github.com/finndomeisen/M346/blob/main/KN03/img/Sicherheitsgruppe.png)




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
