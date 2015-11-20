# Repo clonen
```
git clone https://www.github.com/alfredbez/radiorecorder-server "~/radiorecorder-server"
```

# unnötige Pakete deinstallieren
```
sudo cp /etc/network/interfaces /etc/network/interfaces.bak
sh ~/radiorecorder-server/Slim-Raspbian.sh | sudo sh
```
aus diesem [Gist](https://gist.github.com/samatjain/4dda24e14a5b73481e2a)

# update

```
sudo apt-get update
sudo apt-get dist-upgrade
sudo apt-get pi-upgrade #@TODO nachsehen
```

# folgende Pakete installieren
```
sudo apt-get install streamripper postfix ntp ntpdate nginx php5-fpm php-apc vim fail2ban
```

# symlink auf record-Skript erzeugen
```
ln -s ~/radiorecorder-server/record ~/record
```

# radio.conf aus Vorlage erzeugen
```
cp ~/radiorecorder-server/record.conf.example ~/record.conf
your_favorite_editor ~/record.conf # e.g. 'vim ~/record.conf' or 'subl ~/record.conf'
```

# cronjob einrichten
```
crontab -e
```
und folgendes ganz unten eintragen:
```
50 * * * * /home/USERNAME/record
```
