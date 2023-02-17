## File system
Belangrijkste mappen

/root: Home directory van de root user
/etc: Linux config files 
/home: user home directory
/mnt: waar andere filesystems worden gemount aan het filesystem
/media: waar cd's en usb worden gemount aan het filesystem
/bin: locatie waar alle binaries (executables) staan
/sbin:  nog meer binaries
/lib: de libraries vergelijkbaar met win DLL

---

## Basic commands

pwd: huidige locatie
whoami: huidige gebruiker
cd: change dir
ls: list
	*-l longlist -a hidden*
-h of --help: help file
man: manual

---

## Zoeken

locate:  vind  alles
whereis: specifieker
find (directory opties  soort)
```bash
find / -type f -name apache
```

grep: filteren van output met behulp van piping
|: piping caracter

>ps aux voor een compleet overzicht van draaiende processen.
>Deze is met grep te filteren.

>Het gebruik van wildcards om zoeken makkelijker en sneller te maken.
>Hiervoor te gebruiken:
>[ ] met daarin de te gebruiken letters (bijv: [c,b]at)
>* om alles te zoeken wat daarvoor kan. (bijv index.\*)

---

## Bewerken files en dirs

Een bestand aanmaken: 
```bash
cat > filenaam
touch filenaam
```
\>Tekst toevoegen aan betand, maar overschrijft oude info.
\>> om tekst toe te voegen aan een bestand

Een directory aanmaken:
```bash
mkdir new_dir
```
cp: om een bestand te kopieren

Een bestand hernoemen:
```bash
mv oudenaam nieuwenaam
```
rm: een bestand verwijderen
rmdir: eem dir verwijderen
	Met de switch -r recursive verwijder je dir ook al is deze niet leeg

---

## Tekst manipulatie
cat: volledige inhoud bestand
head: bovenste 10 regels
```bash
#Wil je meer regels
head -n 20 bestandnaam.txt
```
tail: onderste 10 regels
nl: lijnnummers
filteren met grep:
```bash
# alle regels weergeven met de inhoud apache
nl bestandnaam.txt | grep apache
```
sed: om text te vinden en vervangen
```bash
sed s/mysql/MySQL/g bestandnaam.txt > nieuwenaam.txt

# s voor substitute, dus aanpassen mysql naar MySQL
# g voor global, dus alle regels die mysql bevatten
```
more: bestanden bekijken een pagina per keer
less: meer mogelijkheden om te zoeken met /... en n is next

---

## Netwerk analyse & beheer
ifconfig: voor  het opvragen van eigen actieve netwerkconnecties
>eth0: ethernet0 wired network connection
>lo: loopback address / localhost
>wlan0: wireless ethernet connection

***iwconfig: om belangrijke info over de adapter te verzamelen voor wireless hacking 

Ip adres veranderen:
```bash
ifconfig wlan0 192.168.0.1

#Om ook subnet en/of broadcast teveranderen
ifconfig wlan0 192.168.0.1 netmask 255.255.255.0 broadcast 192.168.0.255
```

Mac adres spoofen:
```bash
ifconfig wlan0 down
ifconfig wlan0 hw ether "nieuwe macadress"
ifconfig wlan0 up
```

Nieuw ip adres van DHCP server ontvangen
```bash
dhclient wlan0
```

DNS informatie bestuderen:
```bash
dig (url) [option]
#zoals bijvoorbeel ns voor nameserver en mx voor mail exchange server
```

Om van DNS server te veranderen bewerk je het bestand /etc/resolv.conf
Om IP adressen te mappen bewerk je het bestand /etc/hosts

---

## Add / remove software
Apt staat voor Advanced Packaging Tool

```bash
#search for package
apt-cache search [keyword]

#installation
apt-get install [packagename]

#remove package
apt-get remove [packagename]
#config files blijven op het systeem 

#Package verwijderen tezamen met de config files
apt-get purge [packagename]

#to remove the package and additional installed packages use
apt autoremove [packagename]

#update repositorie
apt-get update

#update packages tot latest version in repo
apt-get upgrade
```

Github is de plek voor software die niet in de repo staat

``` bash
# installing from github
git clone https:\\link van github.git
```

---

## File en directory permissions

Soorten permissies:
>r : Read geeft toestemming te openen en lezen
>w : Write geeft toestemming te openen en wijzigen
>x : Execute geeft toestemming tot uitvoeren, maar niet perse lezen of schrijven.

```bash
#Een andere gebruiker owner maken van een bestand
chown username /path/to/file

#Een groep eigenaar maken van een bestand of map.
chgrp groupname /path

#Permissies controleren
ls -la
```

Octal and binary vertaling van permissies:
| Binary | Octal | rwx |
|--------|------|------|
| 000 | 0 | --- |
| 001 | 1 | --x |
| 010 | 2 | -w- |
| 011 | 3 | -wx |
| 100 | 4 | r-- |
| 101 | 5 | r-x |
| 110 | 6 | rw- |
| 111 | 7 | rwx |

Checking permissons with ls -la:
>d rwx -wx r-- waarbij de eerste letter staat voor directory, vervolgens rwx  opeenvolgend voor owner, groups en users.

```bash
#Permissies van een bestand wijzigen voor user, group en "all users"
chmod 777 /path/to/file
#uitkomst is rwx permissies voor zowel user, group en all.
```

Setting default permissions with umask:
```bash
# check current default permissions for user
umask
```

| Voorbeeld: | |
| ---- | ----- |
| file permission | 666 |
|Default umask value | -022 |
|resulting permission | 644 |

Special permissions:

**SUID**
>Basicly the SUID bit says that any user can execute te file with the permissions of the owner, but those permissions dont extend beyond the use of that file.

```bash
# to set the suid bit enter a 4 before the regular permissions
chmod 4644 filename
```

**SGID**
>When the bit is set on a directory, ownership of a new file goes to the directory creator group instead of the file creator group.

```bash
# to set the sgid bit enter a 2 before the regular permissions
chmod 2644 filename
```

Special permissions and privalege escalation:

> User password file at /etc/shadow

```bash
# find files with suid bit set.
# / for start searching at top of file system
find / -user root -perm -4000
```

>De SUID bit is als volgt herkenbaar in de permissies. -rwsr-xr-x. In plaats van x voor execute staat er een s voor de owner.

---

## Process Management

---

## Mounting to  server

```bash
# used to mount container to NAS
mount -t cifs //172.100.100.10/Films /media/films -o user=username 
```

