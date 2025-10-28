# KN05

## A) Erklärungen

* **VPC:** Ein privates Netzwerk in der Cloud, also in AWS (Virtual Private Cloud). Hat einen grossen IP-Adressbereich.
  ![](https://github.com/finndomeisen/M346/blob/main/KN05/img/vpc.png)
* **Subnet:** Ein kleiner Teil dieses privaten Netzwerks (VPC). Hat einen kleineren IP-Adressbereich innerhalb des VPC.
* **Public IP:** Öffentliche IP-Adresse, die im Internet sichtbar ist. Damit kann man von aussen auf eine Instanz zugreifen.
* **Private IP:** Interne private Adresse im privaten Netzwerk (VPC), nicht direkt von aussen erreichbar. Zuständig für die Kommunikation zwischen Instanzen.
* **Statische IP:** Feste öffentliche IP, die auch bei Neustarts von Instanzen gleich bleibt.

---

## B) Umsetzung

* Zuerst wurden zwei **Sicherheitsgruppen** erstellt:
  * **SG-Webserver** mit Ports **22 (SSH)** und **80 (HTTP)** offen
  * **SG-Database** mit Port **3306 (MariaDB)**, nur intern im Subnetz erreichbar
    
      ![](https://github.com/finndomeisen/M346/blob/main/KN05/img/subnetze.png)
     
   

* Danach wurde eine **statische öffentliche IP (Elastic IP)** erstellt und mit dem Webserver verknüpft, damit dieser immer die gleiche öffentliche IP-Adresse behält.

  ![](https://github.com/finndomeisen/M346/blob/main/KN05/img/elastic_ip.png)
  
* Anschliessend wurden zwei **EC2-Instanzen** erstellt:

   ![](https://github.com/finndomeisen/M346/blob/main/KN05/img/instancess.png)

  * **Web-KN05** im Subnetz *Sub-KN05* mit privater IP `172.31.0.10`

 ![](https://github.com/finndomeisen/M346/blob/main/KN05/img/sg-webserver.png)
    
  * **DB-KN05** im gleichen Subnetz mit privater IP `172.31.0.20`

     ![](https://github.com/finndomeisen/M346/blob/main/KN05/img/sg-database.png)
    

* Jede Instanz erhielt die passende **Sicherheitsgruppe**.

 ![](https://github.com/finndomeisen/M346/blob/main/KN05/img/sicherheitsgruppen.png)

  Der Webserver hat zusätzlich die statische IP **Elastic IP – IP-Web** zugewiesen bekommen.

* Nach einem Neustart blieben alle privaten und öffentlichen IPs gleich – die Konfiguration funktioniert also korrekt.

* Zum Schluss wurden die Seiten **index.html**, **info.php** und **db.php** erfolgreich getestet – alle konnten ohne Fehler aufgerufen werden.

   ![](https://github.com/finndomeisen/M346/blob/main/KN05/img/index.png)


