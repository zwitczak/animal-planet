Konfiguracja brokera lokalnego:

https://blog-techniczny.pl/2021/01/02/instalacja-i-konfiguracja-mosquitto-na-raspberry-pi/

1. Instalacja pakietów w Linux

```
sudo apt install mosquitto -y
```

2. Edycja pliku mosquitto.conf w /etc/mosquitto
    default ustawienia: MQTT broker nasłuchuje na porcie 1883 (do połączenia nie wymaga haseł)

3. Ustawienia hasla
    password_file   <file>
    allow_anonymous False

4. Uruchomienie Mosquitto

```
sudo systemctl start mosquitto
```
Mozna rozważyć uruchamianie nazego brokera razem ze startem systemu:
```
sudo systemctl enable mosquitto
```

5. Sprawdzamy czy Mosquitto nasłuchuje na porcie 
```
netstat -lnt | grep :1883
```

6. Jeżeli coś jest nie tak to sprawdzamy w pliku:
/var/log/mosquitto/mosquitto.log
