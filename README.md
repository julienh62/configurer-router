
---

## Étapes de configuration du routeur

1. **Accéder au CLI**

show ip interface brief

Vérifie l’état des interfaces
Vérifie que le port connecté au modem est up/up.

Si c’est administratively down, active-le avec :



Router> enable
Router# configure terminal
2. Configurer l’interface LANRouter(config)# interface GigabitEthernet0/0/1
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Un pool DHCP (ou DHCP pool) est un ensemble d’adresses IP que le routeur peut distribuer automatiquement aux appareils d’un réseau.
3.Créer un pool DHCP pour le LAN
Router(config)# ip dhcp pool LAN
Router(dhcp-config)# network 192.168.1.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.1.1
Router(dhcp-config)# exit

## Connexion du routeur au Cable Modem et à Internet

### 4 Configurer l’interface WAN du routeur
```plaintext
Router> enable
Router# configure terminal
Router(config)# interface GigabitEthernet0/0/0
je veux configurer l'interface GigabitEthernet0/0/0
if signifie interface
Router(config-if)# ip address dhcp
Router(config-if)# no shutdown
Router(config-if)# exit
ip address dhcp : le routeur obtient automatiquement une IP du modem.

no shutdown : active le port WAN.
5 Connecter le Cable Modem au Cloud Internet

Dans Packet Tracer, utiliser un câble coaxial :

Cable Modem : Port0 → Cloud Internet : Coaxial7

