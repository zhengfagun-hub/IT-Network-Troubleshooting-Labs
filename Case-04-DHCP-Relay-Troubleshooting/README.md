Case 04 – DHCP-Relay-Troubleshooting

1. Projektziel

In diesem Projekt habe ich mit Cisco Packet Tracer ein Firmennetzwerk mit zwei VLANs und einem zentralen DHCP-Server simuliert.

Das Ziel war, ein Problem bei der automatischen IP-Adressvergabe zu untersuchen und zu beheben.

2. Netzwerkaufbau

Das Netzwerk besteht aus zwei Abteilungen:

* Marketing (VLAN 10): 192.168.10.0/24
* Finance (VLAN 20): 192.168.20.0/24

Ein Router verbindet die beiden VLANs. Der DHCP-Server befindet sich im VLAN 20 und verwendet die IP-Adresse 192.168.20.200.

3. Fehlerbeschreibung

Ein Computer in der Marketingabteilung konnte keine IP-Adresse über DHCP beziehen.

Die physische Netzwerkverbindung war vorhanden, aber die automatische IP-Konfiguration funktionierte nicht.

4. Fehlersuche

Zuerst überprüfte ich die VLAN-Konfiguration und die Router-Schnittstellen.

Anschließend konfigurierte ich die DHCP-Weiterleitung auf der Router-Subschnittstelle für VLAN 10:

interface GigabitEthernet0/0.10
ip helper-address 192.168.20.200

Trotzdem konnte der Computer zunächst keine IP-Adresse beziehen.

Durch weitere Ping-Tests stellte ich fest, dass der DHCP-Server nicht erreichbar war.

Bei der Überprüfung der Switch-Konfiguration stellte ich fest, dass der Server-Port nicht dem richtigen VLAN zugeordnet war.

5. Fehlerbehebung

Ich korrigierte die VLAN-Zuordnung des Server-Ports und überprüfte die Trunk-Verbindung zwischen den Switches.

Danach konnte der Router den DHCP-Server erreichen.

Anschließend stellte ich den Computer wieder auf automatische IP-Adressvergabe um.

6. Ergebnis

Der Computer konnte erfolgreich eine IP-Adresse aus dem Marketing-Subnetz über DHCP beziehen.

Die Kommunikation zwischen den VLANs funktionierte ebenfalls.

7. Erkenntnisse

Bei DHCP-Problemen sollte man nicht nur den DHCP-Server und die Adresspools überprüfen, sondern auch die Erreichbarkeit des Servers, die VLAN-Zuordnung und die DHCP-Relay-Konfiguration.

Dieses Projekt hat mir geholfen, den Zusammenhang zwischen VLANs, Routing und DHCP besser zu verstehen.
