🌞 Prouvez que votre configuration est effective
```
PS C:\Windows\system32> Get-NetIPAddress -InterfaceAlias "Ethernet 2"


IPAddress         : fe80::e81e:d9d3:bd6f:6b7a%7
InterfaceIndex    : 7
InterfaceAlias    : Ethernet 2
AddressFamily     : IPv6
Type              : Unicast
PrefixLength      : 64
PrefixOrigin      : WellKnown
SuffixOrigin      : Link
AddressState      : Preferred
ValidLifetime     :
PreferredLifetime :
SkipAsSource      : False
PolicyStore       : ActiveStore

IPAddress         : 192.168.56.1
InterfaceIndex    : 7
InterfaceAlias    : Ethernet 2
AddressFamily     : IPv4
Type              : Unicast
PrefixLength      : 24
PrefixOrigin      : Manual
SuffixOrigin      : Manual
AddressState      : Preferred
ValidLifetime     :
PreferredLifetime :
SkipAsSource      : False
PolicyStore       : ActiveStore
```
🌞 Tester que votre LAN + votre adressage IP est fonctionnel
```
PS C:\Users\weber> ping 192.168.56.101

Envoi d’une requête 'Ping'  192.168.56.101 avec 32 octets de données :
Réponse de 192.168.56.101 : octets=32 temps=1 ms TTL=64
Réponse de 192.168.56.101 : octets=32 temps=1 ms TTL=64
Réponse de 192.168.56.101 : octets=32 temps<1ms TTL=64
Réponse de 192.168.56.101 : octets=32 temps=1 ms TTL=64

Statistiques Ping pour 192.168.56.101:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 1ms, Moyenne = 0ms

xeriasevb@demob1:~$ ping 192.168.56.1
PING 192.168.56.1 (192.168.56.1) 56(84) bytes of data.
64 bytes from 192.168.56.1: icmp_seq=1 ttl=128 time=0.915 ms
64 bytes from 192.168.56.1: icmp_seq=2 ttl=128 time=0.652 ms
64 bytes from 192.168.56.1: icmp_seq=3 ttl=128 time=0.536 ms
64 bytes from 192.168.56.1: icmp_seq=4 ttl=128 time=2.52 ms
64 bytes from 192.168.56.1: icmp_seq=5 ttl=128 time=0.892 ms
64 bytes from 192.168.56.1: icmp_seq=6 ttl=128 time=0.858 ms
64 bytes from 192.168.56.1: icmp_seq=7 ttl=128 time=0.958 ms
^C64 bytes from 192.168.56.1: icmp_seq=8 ttl=128 time=0.644 ms

--- 192.168.56.1 ping statistics ---
8 packets transmitted, 8 received, 0% packet loss, time 7082ms
rtt min/avg/max/mdev = 0.536/0.997/2.524/0.594 ms

```

🌞 Capture de ping

```

[capture](./ping.pcap)

```

**🌞 Sur le PC serveur**

```

PS C:\Users\weber\Documents\netcat-1.11> .\nc.exe -l -p 1234
.\nc.exe : Le terme «.\nc.exe» n'est pas reconnu comme nom d'applet de
commande, fonction, fichier de script ou programme exécutable.
Vérifiez l'orthographe du nom, ou si un chemin d'accès existe,
vérifiez que le chemin d'accès est correct et réessayez.
Au caractère Ligne:1 : 1
+ .\nc.exe -l -p 1234
+ ~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (.\nc.exe:String) [], Co
   mmandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

MARCHE PAS :(

```

