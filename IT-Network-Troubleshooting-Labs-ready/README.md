# IT Network Troubleshooting Labs

**Praxisorientierte Netzwerkdiagnose mit Cisco Packet Tracer**  
*Eigenständiges Lernprojekt zur Vorbereitung auf eine Ausbildung als Fachinformatiker für Systemintegration (FISI) bzw. IT-System-Elektroniker.*

In diesem Repository dokumentiere ich selbst durchgeführte Netzwerksimulationen. Mein Fokus liegt auf **systematischer Fehlereingrenzung**, nachvollziehbaren Tests, der Bewertung von Ergebnissen und klaren technischen Berichten auf Deutsch.

## Fallstudien

| Fall | Störung | Nachweise |
|---|---|---|
| [02 – DNS-Störung](Case-02-DNS-Troubleshooting/README.md) | Interne Webseite ist über den Domainnamen nicht erreichbar | Netzwerktopologie, DNS-Konfiguration, Ping-Tests, Webbrowser-Test |

![Netzwerktopologie der Fallstudie 02](Case-02-DNS-Troubleshooting/images/01-network-topology.png)

## Vorgehensweise

1. Ausgangssituation erfassen
2. Vermutungen formulieren und priorisieren
3. Mit Tests zwischen IP-Erreichbarkeit und Namensauflösung unterscheiden
4. Fehler in einer kontrollierten Simulation auslösen und untersuchen
5. Zugriff nach der Korrektur überprüfen und die Grenzen der Nachweise dokumentieren

## Hinweise

- **Dies ist eine Trainingssimulation, keine tatsächliche Kundenstörung.** Die Namen und IP-Adressen gehören zu einem isolierten Packet-Tracer-Labor.
- Die Screenshots stammen aus dem selbst aufgebauten Labor und sind als Originalaufnahmen gespeichert.
- Bei Fall 02 sind die Tests mittels `ping` dokumentiert. **Eine erfolgreiche Ausführung von `nslookup` ist nicht nachgewiesen.**
- Die Projektdateien (`.pkt`) können ergänzt werden, damit andere das Labor öffnen und nachvollziehen können.
