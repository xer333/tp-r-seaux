## I. ARP basics

```

☀️ Avant de continuer...

```
Adresse physique . . . . . . . . . . . : 58-CD-C9-60-E5-FB

```

☀️ Affichez votre table ARP

```

PS C:\Windows\system32> arp -a

Interface : 192.168.56.1 --- 0x7
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique

Interface : 10.33.71.65 --- 0xd
  Adresse Internet      Adresse physique      Type
  10.33.65.63           44-af-28-c3-6a-9f     dynamique
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.2             01-00-5e-00-00-02     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique

  ```

☀️ Déterminez l'adresse MAC de la passerelle du réseau de l'école

  ```

PS C:\Windows\system32> arp -a
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique

```
☀️ Supprimez la ligne qui concerne la passerelle

```

PS C:\Windows\system32> arp -d 10.33.79.254

```

☀️ Prouvez que vous avez supprimé la ligne dans la table ARP

```

☀️ Wireshark

```

[capture](./arp1.pcap)

```

☀️ Déterminer

```

Adresse IP:'192.168.11.47'
Adresse Mac:'58-CD-C9-60-E5-FB'

```

☀️ DIY

```

PS C:\Windows\system32> ipconfig /all

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : MediaTek Wi-Fi 6E MT7922 (RZ616) 160MHz Wireless LAN Card
   Adresse physique . . . . . . . . . . . : 58-CD-C9-60-E5-FB
   DHCP activé. . . . . . . . . . . . . . : Non
   Configuration automatique activée. . . : Oui
   Adresse IPv6. . . . . . . . . . . . . .: 2a02:8440:6440:373b:da14:2cec:2218:38d7(préféré)
   Adresse IPv6 temporaire . . . . . . . .: 2a02:8440:6440:373b:597:5505:b11e:54b7(préféré)
   Adresse IPv6 de liaison locale. . . . .: fe80::7a2d:2097:3849:2e56%13(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 192.168.11.13(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . : fe80::9424:c9ff:fe47:eedc%13
                                       192.168.11.46
   IAID DHCPv6 . . . . . . . . . . . : 140037577
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2E-0B-BE-3F-00-FD-6B-09-14-AA
   Serveurs DNS. . .  . . . . . . . . . . : 192.168.11.46
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé
```

☀️ Pingz !

```

PS C:\Windows\system32> ping 192.168.11.69

Envoi d’une requête 'Ping'  192.168.11.69 avec 32 octets de données :
Réponse de 192.168.11.69 : octets=32 temps=614 ms TTL=64
Réponse de 192.168.11.69 : octets=32 temps=36 ms TTL=64

Statistiques Ping pour 192.168.11.69:
    Paquets : envoyés = 2, reçus = 2, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 36ms, Maximum = 614ms, Moyenne = 325ms

```

☀️ Affichez votre table ARP !

```

PS C:\Windows\system32> arp -a

Interface : 192.168.56.1 --- 0x7
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique

Interface : 192.168.11.13 --- 0xd
  Adresse Internet      Adresse physique      Type
  192.168.11.30         14-5a-fc-7f-13-93     dynamique
  192.168.11.46         96-24-c9-47-ee-dc     dynamique
  192.168.11.69         90-e8-68-15-ac-43     dynamique
  192.168.11.143        14-5a-fc-7f-13-93     dynamique
  192.168.11.211        b8-1e-a4-6c-56-97     dynamique
  192.168.11.228        90-e8-68-15-ac-43     dynamique
  192.168.11.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique

```

☀️ Capture arp2.pcap

```

[capture](./arp2.pcap)
