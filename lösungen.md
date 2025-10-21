# Lösungen zu den Prüfungsfragen (kompakt, aber fachlich begründet)

Unten findest du zu jeder der 22 Prüfungsfragen eine fundierte Lösung / Musterantwort. Wo nötig gebe ich Annahmen an (z. B. Kostenschätzung) und rechne Schritt-für-Schritt.

---

### 1) Wie beeinflussen Unternehmensziele den Betrieb einer Cloud-Applikation?

**Antwort:** Unternehmensziele (z. B. Kostenminimierung, Wachstum, regulatorische Vorgaben, hohe Verfügbarkeit, Time-to-Market) bestimmen nicht-funktionale Anforderungen und damit Architektur-, Betriebs- und Betriebsmodell-Entscheidungen. Beispiele:

* **Hohe Verfügbarkeit** → Multi-AZ/Region, Load Balancer, Auto-Scaling, ausgefeilte Backup-/Restore-Prozesse.
* **Kostenreduktion** → Nutzung von Reserved/Spot-Instanzen, horizontale Skalierung mit Downscaling, Serverless-Funktionen, Automatisierung.
* **Sicherheit/Compliance** → Private Cloud oder On-Premise, Verschlüsselung, IAM-Policies, Auditing.
  In Kurzform: Geschäftsziele setzen Prioritäten für SLA, Architektur, Kostenmodell und Sicherheitsmassnahmen.

---

### 2) Betriebsstrategie für ein wachsendes Start-up mit begrenztem Budget

**Antwort (Muster):**

* **Grundprinzip:** Start in Public Cloud mit pay-as-you-go, später hybride Strategie wenn nötig.
* **Technische Maßnahmen:** Containerisierte Microservices (Schnelldeploy, effiziente Ressourcennutzung), Auto-Scaling, Managed DB (reduziert Betriebskosten), CI/CD für schnelle Releases.
* **Kostensteuerung:** Monitoring + Alerts für Kosten, Nutzung von Spot/Reserved für stabile Last, automatisches Abschalten nicht benötigter Ressourcen.
* **Betrieb & Sicherheit:** Baseline-Sicherheitskonfiguration (IAM-Prinzip „least privilege“), Backups, einfache Observability (Logs/Metriken).
  Begründung: Public Cloud erlaubt schnelle Skalierung ohne hohe Anfangsinvestitionen; Automatisierung reduziert Opex.

---

### 3) Vergleich On-Premise / Private Cloud / Public Cloud (Kontrolle, Kosten, Sicherheit)

**Antwort (Kurz):**

* **On-Premise:** maximale Kontrolle, hohe CAPEX, volle physische Kontrolle → hohe Sicherheit in physischem Sinne, aber hoher Betriebsaufwand.
* **Private Cloud:** guter Kompromiss: mehr Kontrolle als Public, geringere Multi-Tenant-Risiken; CAPEX oder dedizierter Managed-Service; Sicherheit durch Isolation, aber Kosten und Betriebsaufwand verbleiben.
* **Public Cloud:** geringere Kontrolle, sehr gute Skalierbarkeit, OPEX-Modell, oft starke eingebaute Sicherheitsservices; Sicherheits-Verantwortung ist geteilte Verantwortung (Shared Responsibility).
  **Wann sinnvoll:** On-Premise für extrem sensible Daten/regulatorische Anforderungen; Private Cloud bei Compliance + Mittel; Public Cloud für Agilität und variable Kosten.

---

### 4) Empfehlung für KMU mit sensiblen Kundendaten

**Antwort (Musterempfehlung):** Hybrid oder Private Cloud mit folgenden Argumenten:

1. **Datenschutz/Compliance:** Datenhaltung in kontrollierter Umgebung (On-Premise oder dedizierter Tenant) reduziert Risiko.
2. **Kontrolle & Audit:** Volle Kontrolle über physische/virtuelle Infrastruktur erleichtert Audits.
3. **Skalierbarkeit:** Nicht-kritische Komponenten können in Public Cloud ausgelagert werden (Kostenoptimierung).
   Zusätzlich organisatorische Massnahmen: Verschlüsselung at-rest/in-transit, IAM, regelmäßige Audits, DSGVO-konforme Verträge.

---

### 5) Beispielrechnung: Fremdkosten für 4 VMs, 100 GB Storage, 2 TB Traffic/Monat

**Annahmen (klar angeben):** Preise fiktiv zur Illustration, Währung: CHF.

* VM-Preis pro VM/Monat: **CHF 25**
* Storage pro GB/Monat: **CHF 0.10**
* Outbound Data pro GB: **CHF 0.09**
  Rechnung, **Ziffern-für-Ziffern**:
* VMs: 4 × CHF 25 = CHF 100.
  *Rechnung: 4 mal 25 = 100.*
* Storage: 100 GB × CHF 0.10 = CHF 10.
  *Rechnung: 100 × 0.10 = 10.*
* Data: 2 TB = 2 × 1024 GB = 2048 GB → 2048 × CHF 0.09 = CHF 184.32.
  *Rechnung: 2048 mal 0.09 = 184.32 (weil 2048×9=18432, dann Komma zwei Stellen nach links → 184.32).*
* **Subtotal Fremdkosten/Monat:** CHF 100 + CHF 10 + CHF 184.32 = CHF 294.32.
  *Rechnung: 100 + 10 = 110; 110 + 184.32 = 294.32.*
  **Zusätzlich (nicht-technisch):** Migrationskosten (einmalig) z. B. 40 Std × CHF 80 = CHF 3'200 (Annahme), Betriebs-Personal pro Monat (z. B. 10 Std × CHF 80 = CHF 800).
  **Ergebnis (Monat + einmalig):** Monatliche Fremdkosten ~**CHF 294.32** + Personalkosten laufend; einmalige Migration ~**CHF 3'200** (Beispiel).

> Hinweis: Das ist ein Beispiel; echte Cloud-Preise variieren stark. Für genaue Schätzung Anbieter-Preise, Latenz, IOPS, SLA berücksichtigen.

---

### 6) Drei Faktoren, die Personalaufwand beeinflussen

**Antwort:**

1. **Komplexität der Architektur** (Microservices vs Monolith, Multi-Region).
2. **Grad der Automatisierung** (IaC, CI/CD, automatisiertes Monitoring reduziert manuellen Aufwand).
3. **Anforderungen an Sicherheit & Compliance** (Audits, Logging, Zertifizierungen erhöhen Aufwand).

---

### 7) Evaluation zweier Hyperscaler — Vorgehen

**Antwort (systematisch):** Erstelle eine Bewertungsmatrix mit gewichteten Kriterien, z. B.: Preis (total cost of ownership), SLA/Verfügbarkeit, Performance (Regionen/Latency), angebotene Services (Managed DB, KMS, IAM), Compliance/Datenschutz, Support & SLAs, Ökosystem/Integrationen, Exit-Strategie (Lock-in), TCO. Sammle Messwerte, teste Proof-of-Concepts für kritische Workloads und bewerte Risiken (Vendor-Lock-in, Datenübertragungs-Kosten).

---

### 8) Drei wichtige Kriterien zur Anbieterwahl

**Antwort:**

1. **Compliance & Datacenter-Standorte:** Relevanz für Datenschutz.
2. **Service-Portfolio & Managed Services:** Reduziert Betriebsaufwand (z. B. Managed DB, KMS).
3. **Kostenstruktur & Preise für Datenverkehr:** Daten-egress kann teuer werden; wichtig für TCO.

---

### 9) Skizze einfache Cloud-Betriebsarchitektur + Schutzziele

**Antwort (Komponenten):**

* Load Balancer → Web-VMs/Container (Auto-Scaling) → Application Layer → Managed Database (private Subnet) → Object Storage für Assets.
* Monitoring + Logging + Backup + IAM + Firewall/Security Groups.
  **Schutzziele:** Verfügbarkeit, Integrität, Vertraulichkeit, Authentizität, Nachvollziehbarkeit (Audit-Logs).

---

### 10) Architektur erweitern für Hochverfügbarkeit & Resilienz

**Antwort:** Maßnahmen: Multi-AZ / Multi-Region Deployments, Load Balancer mit Health-Checks, Auto-Scaling (horizontales Scaling), Replikation der DB (Read-Replicas, Failover), asynchrone Warteschlangen/Message Queue, Chaos-Testing / Recovery-Pläne, regelmäßige Backups, Cross-Region Snapshots.

---

### 11) Zweck von *cloud-init*

**Antwort:** *cloud-init* ist ein Standardtool zum Initialisieren von VM-Instanzen beim ersten Boot. Es ermöglicht automatisches Provisioning: Nutzer/SSH-Keys anlegen, Pakete installieren, Services starten, Konfigurationsdateien schreiben. Es wird beim Deployment für wiederholbare, idempotente Initialkonfiguration verwendet.

---

### 12) Script anpassen, damit Webapp nach Neustart weiterläuft

**Antwort:** Lösungsmöglichkeiten:

* Systemdienst erstellen (systemd Unit) und aktivieren (`systemctl enable meinservice`), damit autostart beim Boot.
* Supervisor (z. B. systemd, supervisord) nutzen, um Prozess zu überwachen und bei Absturz neu zu starten (`Restart=always`).
* Containerisieren (Docker) und Container-Orchestrator (k8s) verwenden, die Pod-Restarts und Self-Healing bieten.

---

### 13) Default-Policies vs individuelle Sicherheitsrichtlinien

**Antwort:**

* **Default-Policies:** Standard-Einstellungen eines Systems/Providers; oft generisch und nicht hart genug. Können Sicherheitslücken belassen.
* **Individuelle Policies:** Spezifisch für Organisation/Applikation (Least Privilege, Roles, MFA, Netzwerksegmentation). Individuelle Policies sind nötig, um Compliance und Risikoanforderungen zu erfüllen.

---

### 14) Hardening einer Cloud-VM — konkrete Massnahmen

**Antwort (konkret):**

* SSH: Key-Auth only, Port einschränken, Disable root login, Fail2ban.
* Updates: Automatische Sicherheits-Patching oder regelmäßiges Patch-Management.
* Dienste: Nicht benötigte Dienste deinstallieren/abschalten.
* Firewall: Security Groups / iptables mit restriktiven Regeln.
* Logging & Monitoring: Aktivieren, zentral sammeln, Integritätschecks.
* File-System: Verschlüsselung at-rest, Härtung von Konfigurationsdateien, Minimale Benutzerrechte.

---

### 15) Empfohlene Backup-Strategie für kritische Daten

**Antwort:** 3-2-1-Prinzip: mindestens **3 Kopien**, auf **2 verschiedenen Medientypen**, **1 Kopie Offsite** (z. B. Cloud Object Storage in anderer Region). Zusätzlich: inkrementelle Backups, regelmäßige Vollbackups, Prüfsummen, Verschlüsselung, Backup-Retention/Rolling-Backups, und automatisierte Restore-Tests.

---

### 16) Ablauf eines Restore-Tests

**Antwort (Schritte):**

1. Auswahl des Backups und Testumgebung vorbereiten.
2. Durchführung des Restore gemäß Dokumentation.
3. Validierung der Datenintegrität (Checksums, Anzahl Datensätze).
4. Funktionstests der Applikation (Smoke Tests).
5. Dokumentation: Dauer des Restores, auftretende Fehler, Lessons Learned.
   **Ziel:** Nachweis, dass Backups verlässlich sind und Restore innerhalb akzeptabler RTO/RPO möglich ist.

---

### 17) Lasttest — welche Kennzahlen beobachten?

**Antwort:**

* **Antwortzeit (Latency)** (p95/p99), **Durchsatz** (Requests/s), **Fehlerrate** (HTTP 5xx/4xx), **CPU/RAM-Auslastung** von Hosts, **IOPS/Datenträgerlatenz**, Netzwerkauslastung, Skalierungs-Verhalten (Auto-Scaling Reaktionszeit). Diese Werte zeigen Engpässe und Grenzen.

---

### 18) Schwachstellen erkennen & dokumentieren nach Tests

**Antwort:** Vorgehen: Aus Testergebnissen Bottlenecks ableiten (z. B. hoher p99 Latency → DB-IOPS Problem). Priorisieren nach Impact & Wahrscheinlichkeit. Dokumentation enthält: Beschreibung, Reproduktionsschritte, Logs/Metriken, mögliche Gegenmassnahmen, geschätzter Aufwand, Verantwortlicher. Ticketing/Tracking (z. B. Jira) verwenden.

---

### 19) Tools & Methoden zur Systemüberwachung

**Antwort:** Beispiele: Prometheus + Grafana (Metriken), ELK/EFK (Logs), Datadog/NewRelic (SaaS), Cloud-native Monitoring (CloudWatch, Azure Monitor), Alerting (PagerDuty), Synthetische Tests, Health-Checks, Tracing (Jaeger/Zipkin). Wichtig: Metriken, Logs und Traces kombinieren (Observability-Trifecta).

---

### 20) Monitoring-Konzept mit Alerts bei Ressourcenengpässen

**Antwort (einfaches Konzept):**

* **Metriken:** CPU, RAM, Disk I/O, Netzwerk, Request Latency, Error Rate.
* **Tools:** Prometheus sammelt, Grafana visualisiert, Alertmanager/PagerDuty benachrichtigt.
* **Alerts:** z. B. CPU > 85% für 5 Minuten → Warnung; CPU > 95% für 2 Minuten → Pager (on-call); freie Disk < 10% → Warnung; Error Rate > X% → Pager.
* **Runbook:** Für jeden Alert ein Playbook mit Erstmaßnahmen und Eskalationsstufen.

---

### 21) Vertikale vs horizontale Skalierung (mit Beispiel)

**Antwort:**

* **Vertikale Skalierung:** Erhöhen der Kapazität einer einzelnen Instanz (mehr CPU/RAM). Beispiel: VM von 2 vCPU auf 8 vCPU. Vorteil: einfach; Nachteil: obere Grenze, Single Point of Failure.
* **Horizontale Skalierung:** Mehrere gleichartige Instanzen hinzufügen (Load Balancer verteilt). Beispiel: 2 → 6 Applikations-VMs. Vorteil: bessere Ausfallsicherheit, nahezu unbegrenzte Skalierung; erfordert meist zustandslose Architektur oder Session-Management.

---

### 22) Auto-Scaling-Strategie für steigende Nutzerzahlen

**Antwort (Strategie):**

* **Metrikbasiertes Auto-Scaling:** Scale-Out, wenn CPU > 70% oder Request Latency p95 > Zielwert; Scale-In bei CPU < 30% über längeren Zeitraum.
* **Cooldowns & Mindestanzahl:** Min-Instances = 2, Max-Instances = 20, Cooldown 180s, Skalierung schrittweise (z. B. +2 Instanzen).
* **Kostenkontrolle:** Verwende Scheduled Scaling (erwartete Lastspitzen), Spot/Preemptible-Instanzen für stateless Worker, Limits setzen, Monitoring der Kosten.
* **Test & Safety:** Lasttests vor Produktivschaltung, Alarm bei ungewöhnlichen Skalierungsmustern.

---

Wenn du möchtest, kann ich jetzt:

* diese Antworten in ein **PDF-Übungsblatt** exportieren,
* die Fragen mit Antworten als **Karteikarten (Anki-Format)** aufbereiten,
* oder die Antworten noch ausführlicher mit **Beispielen/Code** (z. B. cloud-init snippet, systemd unit, Beispiel-Alert Regeln) ausarbeiten.

Was hättest du gern als Nächstes?
