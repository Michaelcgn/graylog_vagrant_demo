# graylog_vagrant_demo
Dieses Repo beinhaltet die Konfiguration einer VM, wie ich sie in meinem SEOday-Vortrag vorgestellt habe.

Achtung:
> Diese Anleitung setzt ein paar Dinge voraus, zum Beispiel das du Git installiert hast. Wenn du nicht wei�t, was Git ist, ist es gut m�glich, dass diese Anleitung nichts f�r dich ist.

Damit du die Konfiguration nutzen kannst, ben�tigst Du erstmal alles f�r Vagrant:
https://docs.vagrantup.com/v2/installation/index.html

Anschliessend holst du dir meine Dateien mit:
```
git clone https://github.com/Michaelcgn/graylog_vagrant_demo.git
```

Du wechselst in den "vagrant"-Ordner und f�hrst auf deinem CLi folgendes aus:
```
vagrant up
```

Jetzt startet die Maschine und wird "zusammengebaut".

Dateien, die du in den Ordner "work" legst, werden automatisch in die VM gemounted.
Logfiles geh�ren als reine Text-Dateien (kein gz, tar oder sonstiges) in den Ordner logs.

Bevor du den Import der Logfiles startest, rufst du die Graylog-Oberfl�che (http://localhost:9000)  auf (admin/admin) und launchst einen neuen Input unter System ==> Input:
GELF UDP

Anschliessend kannst du den Import auf der virtuellen Maschine mit 
```
/opt/logstash/bin/logstash -f /var/work/config/logstash.conf
```
starten

**Hinweise**
Support nur hier �ber Github unter Issues
Verbesserungen gerne als Pull-Request
