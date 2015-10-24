# graylog_vagrant_demo
Dieses Repo beinhaltet die Konfiguration einer VM, wie ich sie in meinem SEOday-Vortrag vorgestellt habe.

Achtung:
> Diese Anleitung setzt ein paar Dinge voraus, zum Beispiel das du Git installiert hast. Wenn du nicht weißt, was Git ist, ist es gut möglich, dass diese Anleitung nichts für dich ist.

Damit du die Konfiguration nutzen kannst, benötigst Du erstmal alles für Vagrant:
https://docs.vagrantup.com/v2/installation/index.html

Anschliessend holst du dir meine Dateien mit:
```
git clone https://github.com/Michaelcgn/graylog_vagrant_demo.git
```

Du wechselst in den "vagrant"-Ordner und führst auf deinem CLi folgendes aus:
```
vagrant up
```

Jetzt startet die Maschine und wird "zusammengebaut".

Dateien, die du in den Ordner "work" legst, werden automatisch in die VM gemounted.
Logfiles gehören als reine Text-Dateien (kein gz, tar oder sonstiges) in den Ordner logs.

Bevor du den Import der Logfiles startest, rufst du die Graylog-Oberfläche (http://localhost:9000)  auf (admin/admin) und launchst einen neuen Input unter System ==> Input:
GELF UDP

Anschliessend kannst du den Import auf der virtuellen Maschine mit 
```
/opt/logstash/bin/logstash -f /var/work/config/logstash.conf
```
starten

**Hinweise**
Support nur hier über Github unter Issues
Verbesserungen gerne als Pull-Request
