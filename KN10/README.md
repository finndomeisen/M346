# KN 10

---

## A) Auswahl der Cloud-Komponenten

**Erklärung zur Auswahl der Komponenten**

Ich habe die Komponenten mit dem Ziel ausgewählt, ein optimales Preis-Leistungs-Verhältnis zu erzielen.  
Dabei war mir wichtig, dass die gewählten Dienste zuverlässig, skalierbar und kosteneffizient sind.

Folgende Kriterien spielten bei der Auswahl eine Rolle:
- **Kosten:** Die monatlichen Gesamtkosten sollten im Rahmen bleiben, ohne auf Leistung zu verzichten.
- **Qualität und Support:** Gute Stabilität und Support durch den Anbieter.
- **Langfristiger Nutzen:** Komponenten, die auch bei zukünftigem Wachstum sinnvoll einsetzbar bleiben.
- **Anforderungen des CEOs:** Preisbewusst, aber mit Fokus auf Effizienz und Skalierbarkeit.

Ich habe sowohl AWS als auch Azure verglichen und mich aufgrund der günstigeren Gesamtkosten und einfachen Integration für die jeweiligen empfohlenen Komponenten entschieden.

### Vergleich der Kosten

![Kosten AWS](https://github.com/finndomeisen/M346/blob/main/KN10/img/kostenberechnung_aws.png)  
![Kosten Azure](https://github.com/finndomeisen/M346/blob/main/KN10/img/kostenberechnung_azure.png)

**Abweichung zur On-Premise-Infrastruktur:**  
Im Gegensatz zur On-Premise-Lösung entfallen hier die Hardwarekosten, Stromverbrauch und Wartungsaufwände.  
Dafür entstehen laufende Cloudkosten, die aber durch automatische Skalierung und geringere Ausfallzeiten kompensiert werden.  
Die Lösung ist dadurch insgesamt flexibler und kostentransparenter.

---

## B) Entscheidung für spezifische Cloud-Dienste

**Erklärung zur Auswahl der Komponenten**

Ich habe mich nach einem Vergleich verschiedener Anbieter und Optionen bewusst für die folgenden Komponenten entschieden, da sie die beste Kombination aus Leistung, Preis und Stabilität bieten.

- **Computing (AWS EC2 / Azure VM):** Hohe Verfügbarkeit, flexible Skalierung und einfache Verwaltung.  
- **Storage (S3 / Azure Blob Storage):** Sicher, redundant und kosteneffizient.  
- **Netzwerk & Sicherheit:** Integrierte Firewalls, Load Balancer und Monitoring-Tools sorgen für Sicherheit und Performance.

![Computing](https://github.com/finndomeisen/M346/blob/main/KN10/img/cumputing.jpg)  
![Performance](https://github.com/finndomeisen/M346/blob/main/KN10/img/performance.jpg)  
![Standard](https://github.com/finndomeisen/M346/blob/main/KN10/img/standard2.jpg)

**Abweichung zur On-Premise-Infrastruktur:**  
On-Premise-Server bieten keine dynamische Skalierung – in der Cloud kann die Leistung automatisch an den Bedarf angepasst werden.  
Ausserdem ist die Wartung deutlich einfacher, und Updates erfolgen automatisch über den Provider.  
Dadurch reduziert sich der interne Aufwand erheblich.

---

## C) CRM-Systemvergleich

**Vergleich zwischen Salesforce und Zoho CRM**

Ich habe die beiden Systeme **Salesforce Professional Suite** und **Zoho CRM Professional** verglichen, um die beste Lösung für das Unternehmen zu finden.

![Salesforce](https://github.com/finndomeisen/M346/blob/main/KN10/img/salesforce_pro_suite.png)  
![Zoho](https://github.com/finndomeisen/M346/blob/main/KN10/img/zoho_professional.png)

| Kriterium | Salesforce Professional | Zoho CRM Professional |
|------------|------------------------|-----------------------|
| Preis       | Deutlich teurer       | Günstiger |
| Funktionsumfang | Sehr gross, aber teilweise überdimensioniert | Alle wichtigen CRM-Funktionen enthalten |
| Benutzerfreundlichkeit | Komplexer Aufbau | Einfache und intuitive Bedienung |
| Automatisierung         | Umfangreich         | Gut, aber einfacher |
| Skalierbarkeit             | Hoch                 | Mittel bis hoch |
| Fazit                         | Für grosse Unternehmen geeignet | Ideal für KMU und Startups |

**Meine Wahl:**  
Ich würde **Zoho CRM Professional** wählen, da es alle grundlegenden Funktionen (Leadmanagement, Reporting, Automatisierung) bietet, aber deutlich günstiger und benutzerfreundlicher ist.  
Für kleinere oder mittelgrosse Unternehmen ist Zoho die wirtschaftlichere und effizientere Option.

---

## D) Fazit

Nach der Analyse von fünf Varianten (AWS, Azure, Heroku, Zoho CRM, Salesforce) lassen sich folgende Schlüsse ziehen:

### Kostenvergleich
- **AWS & Azure (IaaS)**: Flexibel und skalierbar, aber laufende Kosten können bei Dauerbetrieb steigen.  
- **Heroku (PaaS)**: Teurer als IaaS, jedoch mit weniger Administrationsaufwand.  
- **Zoho CRM / Salesforce (SaaS)**: Monatliche Fixkosten, keine IT-Verwaltung nötig, aber eingeschränkte Anpassbarkeit.  

### Aufwand für die Firma
- **IaaS (Rehosting)**: Hoher technischer Aufwand, Migration und Wartung bleiben intern.  
- **PaaS (Replatforming)**: Mittel – weniger Wartung, aber gewisse Anpassungen nötig.  
- **SaaS (Repurchasing)**: Geringster Aufwand – einfach Benutzer einrichten und starten.  

### Bewertung
| Modell | Kosten | Aufwand | Flexibilität | Empfehlung |
|---------|---------|----------|----------------|-------------|
| AWS | Mittel | Hoch | Hoch | ✅ |
| Azure | Mittel | Hoch | Hoch | ✅ |
| Heroku | Mittel-Hoch | Mittel | Mittel | 🔸 |
| Zoho CRM | Tief | Tief | Mittel | ✅ Beste Option für KMU |
| Salesforce | Hoch | Tief | Hoch | 🔸 Für grosse Firmen |

### Schlussfolgerung
Die Cloud-Migration lohnt sich klar.  
Die Variante **SaaS (Zoho CRM)** bietet für diese Firma das **beste Kosten-Nutzen-Verhältnis**, während **AWS oder Azure** eine gute Option wären, falls man die alte Anwendung weiter betreiben möchte.  
Langfristig spart die Firma durch geringeren Wartungsaufwand, höhere Sicherheit und einfache Skalierung.
