Ich habe für diese Aufgabe VMware Workstation verwendet. Da diese Software auf meinem Windows Host installiert ist und wie ein normales Programm läuft, habe ich vermutet, dass es sich um einen Hypervisor Typ 2 handelt.

#### Überprüfung des Host Systems
Zuerst habe ich die Ressourcen meines Host Systems geprüft. Im Task-Manager konnte ich sehen, wie viele logische Prozessoren und wie viel RAM mein Rechner hat.  

#### CPU Test
Danach habe ich in den Einstellungen der virtuellen Maschine versucht, mehr Prozessoren zuzuweisen, als mein Host System besitzt. VMware Workstation hat diese Einstellung zwar übernommen, aber beim Starten der VM wurde sofort eine Fehlermeldung angezeigt und der Start abgebrochen.  


#### RAM Test
Im nächsten Schritt habe ich dasselbe mit dem Arbeitsspeicher ausprobiert. Ich habe versucht, mehr RAM zuzuweisen, als mein Host System zur Verfügung hat. Auch hier konnte die VM nicht gestartet werden, da VMware Workstation sofort eine Fehlermeldung ausgegeben hat.  


#### Erklärung
Die Ursache dafür ist, dass VMware Workstation keine Überbuchung von Ressourcen zulässt. Es ist also nicht möglich, mehr CPUs oder mehr RAM zu vergeben, als das Host System physisch besitzt. Auf diese Weise wird sichergestellt, dass der Rechner stabil bleibt und die virtuellen Maschinen nicht das gesamte System blockieren. Bei einigen Hypervisoren vom Typ 1 wäre sogenanntes Overcommitment möglich, was bedeutet, dass man mehr virtuelle Ressourcen zuteilen kann, als physisch vorhanden sind. Dies führt dann aber meist zu Leistungseinbussen.

#### Fazit
Meine ursprüngliche Vermutung hat sich bestätigt: VMware Workstation ist ein Hypervisor Typ 2. Er läuft auf einem bestehenden Host Betriebssystem und verhindert, dass man virtuelle Maschinen mit mehr Ressourcen startet, als tatsächlich vorhanden sind.
