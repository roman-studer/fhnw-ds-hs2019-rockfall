Informationen zum Server steinschlag_01:

Ansprechperson:
	Administrator:
	Roman Janic Studer
	roman.studer1@students.fhnw.ch

Server:
	Provider: SWITCHengines
	Name: steinschlag_01
	ID: e967d0b6-415f-433f-a252-4d05bc9fa7b0
	Betriebssystem: Ubuntu Bionic 18.04 (SWITCHengines)
	Abbild ID: 05568608-b3b9-442c-88d7-d96af31db185
	Achtung! Kein education-Project (muss bei nichtgebrauch heruntergefahren werden)

Kosten: 
	m1.small: 1.0358‬CHF/Tag, 31.074CHF/Monat, 372.888‬CHF/Jahr
	(mit 1 CPU, 2 GB RAM, 20 GB Disk, 1 IPv4)
	Siehe: https://www.switch.ch/export/sites/default/engines/.galleries/files/SWITCHengines-Pricing-Flyer-2018.pdf

	
Spezifikationen:
	Variante: m1.small
	Variante ID: 2
	RAM: 2GB
	VCPUs: 1 VCPU
	Festplatte: 20GB

IP-Adressen:
	Private: 10.0.2.177  
	MAC-Adresse: 2001:620:5ca1:1f0:f816:3eff:fe0d:2fb2
	Floating IP: 86.119.38.186

Sicherheitsgruppen:
	steinschlag_01
		Erlaube IPv4 22/tcp from 0.0.0.0/0
		Erlaube IPv4 80/tcp from 0.0.0.0/0
		Erlaube IPv6 to ::/0
		Erlaube IPv4 icmp from 0.0.0.0/0
		Erlaube IPv4 21/tcp from 0.0.0.0/0
		Erlaube IPv4 to 0.0.0.0/0
	default
		Erlaube IPv6 to ::/0
		Erlaube IPv6 from default
		Erlaube IPv4 from default
		Erlaube IPv4 to 0.0.0.0/0

Services:
	LAMP-Stack:
		Linux: Ubuntu 18.04.3 LTS (GNU/Linux 4.15.0-72-generic x86_64) (SWITCHengines)
			User: ubuntu
			PW: Auf Anfrage
		Apache 2: Apache/2.4.29 (Ubuntu)
			User: ubuntu
			PW: Auf Anfrage
		MySQL (MariaDB): MariaDB 10.1.43-MariaDB-0ubuntu0.18.04.1 Ubuntu 18.04
			User: root
			PW: Auf Anfrage
		PHP: PHP 7.2.24-0ubuntu0.18.04.1 (cli)
	Wordpress: Version 5.3.2
		User: wordpress
		PW: Auf Anfrage

	FTP vsftp

Wordpress:
	User_1: Roman Studer (admin)
	PW: Auf Anfrage
	User_2: Lukas Gehrig (admin)
	PW: Auf Anfrage
	Login auf: http://86.119.38.186/wordpress/wp-login.php?redirect_to=http://86.119.38.186/wordpress/wp-admin/post.php?post=39&action=edit&reauth=1

SSH: 
Verbindung durch SSH (benötigt Private-Key, Auf Anfrage von Admin erhältlich)
	Terminal: ssh -i ~/.ssh/{PRIVATE_KEY} ubuntu@86.119.38.186


Transfer der Website auf einen anderen Server:

Schritt 1: Backup aller Files (Best Practice)
- Download aller Wordpress-Files durch FTP verbindung

Schritt 2: Exportieren der WordPress Datenbank
- Exportieren der Datenbank auf MariaDB

Schritt 3: Neue Datenbank auf neuem Server erstellen
- Öffnen der MySQL Datenbank und neue Datenbank mit passendem Namen zur Website erstellen
- Neuer MySQL User mit sicherem Passwort erstellen
- User zur Datenbank hinzufügen und alle Privilegien zuweisen

Schritt 4: wp-config.php Datei editieren
- Kopie des Files erstell und an sicherer Stelle ablegen
- Original öffnen und folgende Änderungen vornehmen:
	- Datenbankname anpassen: define('DB_NAME', 'db_name');
	- Username anpassen: define('DB_USER', 'db_user');
	- Passwort anpassen: define('DB_PASSWORD', 'db_pass');
- Datei speichern und schliessen

Schritt 5: Datenbank importieren
- Zuvor heruntergeladene Datenbank mit dem angepassten wp-config.php-File in die neu erstellte Datenbank laden

Schritt 6: WordPress-Files hochladen
- Mittels FTP alle Wordpress-Files in ein dafür bestimmtes Folder hochladen


Geschrieben von Roman Janic Studer

