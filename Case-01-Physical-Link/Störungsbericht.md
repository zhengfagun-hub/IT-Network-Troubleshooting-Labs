Störungsbericht – Ticket #001

Thema: Keine Netzwerkverbindung nach einem Büroumzug
Bereich: IT-Support / Netzwerktechnik
Art: Simulierte Fehlerdiagnose (Übungsprojekt)
Status: Arbeitsplatz wieder funktionsfähig; Hardware-Reparatur ausstehend

1. Problembeschreibung

Nach einem Büroumzug konnte ein Mitarbeiter weder auf das Internet noch auf interne Netzwerkfreigaben zugreifen.

Der Computer verwendete Windows 11. Andere Mitarbeiter im selben Büro hatten keine Netzwerkprobleme.

2. Fehlersuche

Schritt 1 – Netzwerkkabel überprüfen

Zuerst wurde das Netzwerkkabel kontrolliert und durch ein funktionierendes Kabel ersetzt. Das Problem bestand weiterhin. Die Link-LED am Netzwerkanschluss leuchtete nicht.

Schritt 2 – Switchport überprüfen

Der ursprüngliche Switchport war aktiviert, zeigte aber keinen Link. Die Verbindung wurde mit Genehmigung des Administrators testweise auf einen anderen, funktionierenden und passend konfigurierten Switchport umgesteckt. Es wurde weiterhin kein Link hergestellt.

Schritt 3 – Netzwerkanschluss an der Wand testen

Ein anderer Computer wurde mit derselben Netzwerkdose verbunden. Er konnte eine IP-Adresse über DHCP beziehen und sowohl das Internet als auch die internen Dateien erreichen.

Schritt 4 – Netzwerkkarte überprüfen

Mit PowerShell (Get-NetAdapter) wurde festgestellt, dass die eingebaute Netzwerkkarte den Status Disconnected hatte. Im Geräte-Manager wurden keine Gerätefehler angezeigt.

Schritt 5 – USB-Ethernet-Adapter testen

Mit einem USB-Ethernet-Adapter konnte der betroffene Computer wieder eine Netzwerkverbindung herstellen. Internet und interne Netzwerkfreigaben waren erreichbar.

3. Wahrscheinliche Fehlerursache

Bei der Sichtprüfung wurde ein verbogener Kontakt im RJ45-Anschluss der eingebauten Netzwerkkarte entdeckt.

Vermutlich wurde der Anschluss beim Abziehen des Netzwerkkabels während des Umzugs beschädigt.

4. Lösung

Als vorübergehende Lösung erhielt der Mitarbeiter einen USB-Ethernet-Adapter.

Anschließend wurde überprüft, ob er seine Arbeitsaufgaben wieder ausführen konnte. Der Mitarbeiter bestätigte, dass Internet und interne Dateien wieder erreichbar waren.

Eine dauerhafte Reparatur oder der Austausch der defekten Hardware muss noch organisiert werden.

5. Fazit

In diesem Fall wurde die Fehlerursache durch systematische Prüfungen und den Vergleich mit funktionierenden Geräten eingegrenzt.

Die einzelnen Tests halfen dabei, das Netzwerkkabel, den Switchport und die Netzwerkverkabelung als Hauptursachen weitgehend auszuschließen.

Das wichtigste Ergebnis: Die Arbeitsfähigkeit konnte schnell wiederhergestellt werden, ohne sofort die gesamte Hardware ersetzen zu müssen.

⸻

Dieses Dokument beschreibt eine simulierte IT-Support-Aufgabe zu Lern- und Bewerbungszwecken. Die Prüfungen und Ergebnisse wurden in einer Trainingssimulation durchgeführt.
