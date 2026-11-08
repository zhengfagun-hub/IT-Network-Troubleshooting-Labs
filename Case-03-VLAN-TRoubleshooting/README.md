Case 03 – VLAN-Trunk-Troubleshooting

Projekt: IT Network Troubleshooting Labs
Software: Cisco Packet Tracer
Bereich: Netzwerktechnik / IT-Support
Art: Eigenständige Trainingssimulation

1. Ziel des Projekts

In diesem Projekt habe ich ein kleines Unternehmensnetzwerk mit zwei VLANs aufgebaut und die Kommunikation zwischen ihnen konfiguriert.

Anschließend habe ich einen Fehler in der Trunk-Konfiguration simuliert, die Auswirkungen untersucht und die Netzwerkverbindung wiederhergestellt.

2. Netzwerkaufbau

Das Netzwerk besteht aus einem Cisco-2911-Router, zwei Cisco-2960-Switches und drei PCs.

Gerät	IP-Adresse	VLAN
PC0 – Marketing	192.168.10.10	10
PC1 – Finanzen	192.168.20.50	20
PC2 – Testgerät	192.168.20.100	20

Die Standardgateways sind:

* VLAN 10: 192.168.10.1
* VLAN 20: 192.168.20.1

Der Router verwendet zwei Subinterfaces mit IEEE 802.1Q, um die Kommunikation zwischen den VLANs zu ermöglichen (Router-on-a-Stick).

3. Fehlerbeschreibung

Im Normalzustand konnten die Geräte innerhalb eines VLANs sowie zwischen VLAN 10 und VLAN 20 kommunizieren.

Für die Fehlersimulation wurde VLAN 20 auf dem Trunk-Port Fa0/1 von SW-02 aus der Liste der erlaubten VLANs entfernt.

Der Trunk-Port blieb aktiv, konnte aber keine Frames aus VLAN 20 mehr über diese Verbindung weiterleiten.

4. Fehlerdiagnose

Zuerst habe ich die Netzwerkverbindung mit Ping-Tests überprüft.

Die Geräte innerhalb von VLAN 20 konnten weiterhin miteinander kommunizieren.

Allerdings konnte PC1 das Standardgateway 192.168.20.1 nicht mehr erreichen. Auch die Verbindung von PC0 zu PC2 funktionierte nicht.

Anschließend habe ich die Trunk-Konfiguration auf SW-02 mit dem Befehl show interfaces trunk untersucht.

Dabei habe ich festgestellt, dass VLAN 20 nicht mehr in der Liste der erlaubten VLANs enthalten war.

5. Fehlerbehebung

Um das Problem zu beheben, habe ich VLAN 20 wieder zur Liste der erlaubten VLANs hinzugefügt.

Verwendeter Cisco-CLI-Befehl:

switchport trunk allowed vlan add 20

Danach habe ich die Trunk-Konfiguration erneut überprüft.

6. Funktionsprüfung

Nach der Korrektur habe ich die Kommunikation innerhalb von VLAN 20 und zwischen den beiden VLANs erneut getestet.

Die Verbindung zum Standardgateway sowie die VLAN-übergreifende Kommunikation funktionierten wieder.

7. Erkenntnisse

Bei diesem Versuch habe ich gelernt, dass eine aktive physische Netzwerkverbindung nicht automatisch bedeutet, dass alle VLANs über einen Trunk erreichbar sind.

Besonders wichtig waren:

* Die Unterscheidung zwischen Access- und Trunk-Ports
* Die Zuordnung von Switchports zu VLANs
* Die Überprüfung der erlaubten VLANs
* Die Funktionsweise von Router-on-a-Stick
* Die systematische Fehlersuche mit Ping und Cisco-CLI-Befehlen

8. Projektdateien

* 03-VLAN-Normal.pkt – Funktionsfähiges Netzwerk
* 03-VLAN-Failure.pkt – Simulierte Trunk-Störung
* 03-VLAN-Recovered.pkt – Wiederhergestellte Netzwerkkonfiguration

⸻

Dieses Projekt wurde mit Cisco Packet Tracer zu Lern- und Bewerbungszwecken durchgeführt. Es handelt sich um eine simulierte Netzwerkstörung und nicht um einen realen Unternehmensvorfall.
