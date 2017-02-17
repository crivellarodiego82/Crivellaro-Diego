# Crivellaro-Diego

Rapberry AI Project 2016

--------------------------------------------------------------------------------------------
Velocizzare Raspberry PI 3 da shell root
echo "performance" |sudo tee /sys/devices/system/cpu/cpu0/cpufreq/scaling_governor
--------------------------------------------------------------------------------------------
Aggiornameto PIP

Lista Pacchetti Obsoleti
pip list --outdated
sudo pip freeze --local | grep -v '^\-e' | cut -d = -f 1  | xargs -n1 sudo pip install -U
--------------------------------------------------------------------------------------------
Installare pacchetto senza utilizzo cache
sudo pip --no-cache-dir install (pacchetto) --upgrade
--------------------------------------------------------------------------------------------
Disattivazione Led Picamera
sudo nano /boot/config.txt
disable_camera_led=1
sudo reboot
--------------------------------------------------------------------------------------------
Sintesi Vocale
espeak "Ciao a tutti" -v it -p 70 -s 155 > /dev/null 2> /dev /null
--------------------------------------------------------------------------------------------
Registarzione Audio
arecord -d 5 -t wav test.wav
aplay test.wav
--------------------------------------------------------------------------------------------
Creazione script avvio automatico:

sudo nano /etc/systemd/system/(nome file).service

*//
[Unit]
Description=My Script Service
After=multi-user.target

[Service]
Type=idle
ExecStart=/usr/bin/python /(posizione e nome file).py

[Install]
WantedBy=multi-user.target

//*

sudo chmod 644 (nome file).service
sudo systemctl enable (nome file).service
--------------------------------------------------------------------------------------------

Avviare applicazioni con LXDE

cd ~/.config/autostart/
sudo nano app.desktop

-----Esempio VNC-------

[Desktop Entry]
Encoding=UTF-8
Type=Application
Name=X11VNC
Exec=x11vnc -forever -usepw -display :0 -ultrafilexfer
StartupNotify=false
Terminal=false
Hidden=false
--------------------------------------------------------------------------------------------

Gestiore Relè con Raspberry

gpio mode 0 out (Settaggio Uscita BCM come uscita)

sudo gpio write 0 0 (Disattivo)
sudo gpio write 0 1 (Attivo)
--------------------------------------------------------------------------------------------
