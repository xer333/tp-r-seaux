

🌞 Adresses IP de ta machine

```
PS C:\Users\weber> ipconfig /all
Carte réseau sans fil Wi-Fi :

   
   Adresse IPv6 de liaison locale. . . . .: fe80::c6c5:dded:9b7:bd83%12(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.77.163(préféré)
```

🌞 Si t'as un accès internet normal, d'autres infos sont forcément dispos...

```
PS C:\Users\weber> ipconfig /all

    Passerelle par défaut. . . . . . . . . : 10.33.79.254
    Serveur DHCP . . . . . . . . . . . . . : 10.33.79.254
    Serveurs DNS. . .  . . . . . . . . . . : 8.8.8.8
                                       1.1.1.1
```

🌞 Envoi un ping vers...

```
PS C:\Users\weber> ping 10.33.77.163

Envoi d’une requête 'Ping'  10.33.77.163 avec 32 octets de données :
Réponse de 10.33.77.163 : octets=32 temps<1ms TTL=128
Réponse de 10.33.77.163 : octets=32 temps<1ms TTL=128
Réponse de 10.33.77.163 : octets=32 temps<1ms TTL=128
Réponse de 10.33.77.163 : octets=32 temps=1 ms TTL=128

Statistiques Ping pour 10.33.77.163:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 1ms, Moyenne = 0ms

PS C:\Users\weber> ping 127.0.0.1

Envoi d’une requête 'Ping'  127.0.0.1 avec 32 octets de données :
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 127.0.0.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms
```

🌞 On continue avec ping. Envoie un ping vers...

```
PS C:\Users\weber> ping 10.33.79.254

Envoi d’une requête 'Ping'  10.33.79.254 avec 32 octets de données :
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.

Statistiques Ping pour 10.33.79.254:
    Paquets : envoyés = 4, reçus = 0, perdus = 4 (perte 100%),

PS C:\Users\weber> ping 77.206.10.33

Envoi d’une requête 'Ping'  77.206.10.33 avec 32 octets de données :
Réponse de 77.206.10.33 : octets=32 temps=44 ms TTL=59
Réponse de 77.206.10.33 : octets=32 temps=39 ms TTL=59
Réponse de 77.206.10.33 : octets=32 temps=35 ms TTL=59
Réponse de 77.206.10.33 : octets=32 temps=53 ms TTL=59

Statistiques Ping pour 77.206.10.33:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 35ms, Maximum = 53ms, Moyenne = 42ms

PS C:\Users\weber> ping www.thinkerview.com

Envoi d’une requête 'ping' sur www.thinkerview.com [188.114.97.7] avec 32 octets de données :
Réponse de 188.114.97.7 : octets=32 temps=14 ms TTL=55
Réponse de 188.114.97.7 : octets=32 temps=28 ms TTL=55
Réponse de 188.114.97.7 : octets=32 temps=14 ms TTL=55
Réponse de 188.114.97.7 : octets=32 temps=15 ms TTL=55

Statistiques Ping pour 188.114.97.7:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 14ms, Maximum = 28ms, Moyenne = 17ms
```

🌞 Faire une requête DNS à la main

```
PS C:\Users\weber> Resolve-DnsName www.thinkerview.com

Name                                           Type   TTL   Section    IPAddress
----                                           ----   ---   -------    ---------
www.thinkerview.com                            AAAA   300   Answer     2a06:98c1:3120::7
www.thinkerview.com                            AAAA   300   Answer     2a06:98c1:3121::7
www.thinkerview.com                            A      300   Answer     188.114.96.7
www.thinkerview.com                            A      300   Answer     188.114.97.7

PS C:\Users\weber> Resolve-DnsName www.wikileaks.org

Name                           Type   TTL   Section    NameHost
----                           ----   ---   -------    --------
www.wikileaks.org              CNAME  1611  Answer     wikileaks.org

Name       : wikileaks.org
QueryType  : A
TTL        : 1800
Section    : Answer
IP4Address : 51.159.197.136


Name       : wikileaks.org
QueryType  : A
TTL        : 1800
Section    : Answer
IP4Address : 80.81.248.21


Name                   : wikileaks.org
QueryType              : SOA
TTL                    : 1611
Section                : Authority
NameAdministrator      : root.wlinfra.org
SerialNumber           : 2022082502
TimeToZoneRefresh      : 21600
TimeToZoneFailureRetry : 3600
TimeToExpiration       : 604800
DefaultTTL             : 1800

PS C:\Users\weber> Resolve-DnsName www.torproject.org

Name                                           Type   TTL   Section    IPAddress
----                                           ----   ---   -------    ---------
www.torproject.org                             AAAA   150   Answer     2620:7:6002:0:466:39ff:fe32:e3dd
www.torproject.org                             AAAA   150   Answer     2a01:4f8:fff0:4f:266:37ff:fe2c:5d19
www.torproject.org                             AAAA   150   Answer     2a01:4f8:fff0:4f:266:37ff:feae:3bbc
www.torproject.org                             AAAA   150   Answer     2a01:4f9:c010:19eb::1
www.torproject.org                             AAAA   150   Answer     2620:7:6002:0:466:39ff:fe7f:1826
www.torproject.org                             A      42    Answer     116.202.120.165
www.torproject.org                             A      42    Answer     204.8.99.144
www.torproject.org                             A      42    Answer     204.8.99.146
www.torproject.org                             A      42    Answer     116.202.120.166
www.torproject.org                             A      42    Answer     95.216.163.36

```
🌞 J'attends dans le dépôt git de rendu un fichier

```

[capture](./ping.pcap)

```

🌞 Livrez un deuxième fichier

```

[capture](./dns.pcap)

```

🌞 Effectue un scan du réseau auquel tu es connecté

```

je suis conncté a mon partage de connexion  

PS C:\Windows\system32> nmap -sn -PR 192.168.11.13
Starting Nmap 7.92 ( https://nmap.org ) at 2024-10-14 14:27 Paris, Madrid (heure dÆÚtÚ)
mass_dns: warning: Unable to determine any DNS servers. Reverse DNS is disabled. Try using --system-dns or specify valid servers with --dns-servers
Nmap scan report for 192.168.11.13
Host is up.
Nmap done: 1 IP address (1 host up) scanned in 0.26 seconds

```

🌞 Changer d'adresse IP

```

PS C:\Windows\system32> ipconfig /all
Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : MediaTek Wi-Fi 6E MT7922 (RZ616) 160MHz Wireless LAN Card
   Adresse physique . . . . . . . . . . . : 58-CD-C9-60-E5-FB
   DHCP activé. . . . . . . . . . . . . . : Non
   Configuration automatique activée. . . : Oui
   Adresse IPv6. . . . . . . . . . . . . .: 2a01:cb1a:57:4094:5249:464f:daa7:9211(préféré)
   Adresse IPv6 temporaire . . . . . . . .: 2a01:cb1a:57:4094:85aa:1e6d:d872:e473(préféré)
   Adresse IPv6 de liaison locale. . . . .: fe80::7a2d:2097:3849:2e56%13(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 192.168.11.15(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . : fe80::fc9c:a7ff:fe3d:e64%13
                                       192.168.11.46
   IAID DHCPv6 . . . . . . . . . . . : 140037577
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2E-0B-BE-3F-00-FD-6B-09-14-AA
   Serveurs DNS. . .  . . . . . . . . . . : fe80::fc9c:a7ff:fe3d:e64%13
                                       192.168.11.46
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé

