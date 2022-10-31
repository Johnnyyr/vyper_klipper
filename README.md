# Vyper Klipper
Anycubic Vyper Klipper installieren u. kalibrieren, funktioniert auch für viele andere Drucker

Da ich doch einige Probleme hatte mir alle Daten zusammen zu suchen, hier meine Erfahrungen, Links und Tipps. 
Ich verlinke imnmer auf die Original-Doku in english, ist gibt aber auch eine [Übersetzung](https://crydteam.gitbook.io/crydteam-wiki/3d-druck/faq/deutsch-uebersetzung-klipper-dokumentation) von J. Müller auf deutsch, danke dafür. Die meisten Erklärungen beziehen sich auf den Vyper und Mainsail.

Kein anspruch auf vollständigkeit.


## 1. Hardware

* Raspberry Pi ab Zero 2 W
* SD-Karte 16 G+
* Pi-Netzteil mit ausreichend Power (kein Handyladegeraet)
* gutes USB-Kabel um den Drucker zu verbinden
* optional Webcam, Pi-Touchscreen
  
## 2. Software

* Firmware
    * Klipper (Firmware für den Drucker)
* Oberflaeche/Benutzerschnittstelle
    * [Mainsail](https://github.com/mainsail-crew/mainsail)
    * [Fluidd](https://github.com/fluidd-core/fluidd)
    * [DWC2](https://github.com/Stephan3/dwc2-for-klipper) 
    * [Octoprint](https://github.com/OctoPrint/OctoPrint)
* Pakete und Images
    * [Raspbian Pi OS](https://www.raspberrypi.com/software/)
    * [KIAUH](https://github.com/th33xitus/kiauh) - Skriptsammlung (quasi die All-in-One Lösung) -Empfehlung-
* Tools
    * [SD-Card Formater ](https://www.sdcard.org/downloads/formatter/) (SD-Karte sauber formatieren)
    * [Raspberry Pi Imager](https://www.raspberrypi.com/software/) (AIO-Tool zum Pi-OS flashen)
    * [Cyberduck](https://cyberduck.io/) (SFTP-Tool um die Firmware vom Pi abzuholen, geht auch mit dem Terminal)

## 3. Installation (schnell variatante) und Empfehlung 

Ihr habt meherer möglichkeiten um den ganzen Kram auf den Pi zu kommen. 

### 3.1 Varianten: 

1. [KIAUH](https://github.com/th33xitus/kiauh) image runterladen und mit dem Raspberry Pi Imager](https://www.raspberrypi.com/software/) flashen und der Anleitung von KIUHA auf GIT folgen.
2.  Raspberry Pi Imager](https://www.raspberrypi.com/software/) öffnen, auf "OS WAEHLEN" klicken -> "Other specific-purpose OS" -> "3D printing" -> "Mainsail OS" auswählen und     flashen. 

3.  Raspberry Pi Imager](https://www.raspberrypi.com/software/) öffnen und ein "Raspberry PI OS" auswählen, flashen und die den rest per hand installieren. 

zu 2. u. 3. weiter mit Offizielle Anleitung von [Klipper](https://www.klipper3d.org/Installation.html) lesen da sind alle weitern Schritte erklärt. 

Firmware auf den Drucker flashen fertig. Weiter zu Schritt 7. Drucker kalibrieren.

### 3.2 Links zu ausführlichen Installations Anleitungen

Text:
* Offizielle Anleitung von [Klipper](https://www.klipper3d.org/Installation.html)
* Anleitung von [Stone-Time](https://stone-time.de/docs/allgemeine-anleitung-zum-erzeugen-der-firmware/)
Video:
* Sehr gutes Video vom [Cryd-Team](https://youtu.be/S_K7iB3jYMs) (Teil 1 und 2)

  
## 4. Tipps zur Installation die einem ein paar Probleme ersparen

* Pi Benutzername nicht ändern
* nicht nervös werden die installation dauert je nach Variante 
* Variante 1. geht am schnellsten und ist eher die klicky bunte variante für die nicht Hardcore-Nerds
* [Vorlagen](https://github.com/Klipper3d/klipper/tree/master/config) für eure Firmware je nach Drucker, liegen aber auch schon auf dem Pi und können kopiert werden
* Fertige Firmware Vorlagen findet ihr haufenweise im Netz z.B. für Vyper oder Ender 3 mit oder ohne Bltouch
* Schaut vorher nach welches Mainboard in eurem Drucker verbaut ist. 
* mit Shift+Command+X könnt ihr im Raspberry Pi Imager](https://www.raspberrypi.com/software/) das WLAN einstellen und weiter optionen einstellen - Uername auf "pi" lassen.
* wenn es nicht gleich klappt bekommt ihr bestimmt hilfe auf diversen Discord-Servern oder Foren. (links ganz unten)

## 5. Benutzeroberfläche, Vorlagen und Macros einrichten

* Am besten ihr schaut diese Video vom Cryd-Team an, besser kann man es nicht erklären https://youtu.be/6RBNRVgC2Go?t=549

## 6. Sensor testen und einrichten

Falls ihr in eurer Vorlage der printer.cfg noch nicht euren richtigen Sensor drin stehen habt, dann macht das jetzt. Für den Vyper braucht ihr mit der printer.cfg vom "Cryd-Team" nichts weiter machen.

* [BL-Touch](https://www.klipper3d.org/BLTouch.html) und [hier](https://www.klipper3d.org/Config_Reference.html?h=probe#probe)

## 7. Kalibration

Wenn alles installiert ist "müsst" ihr euren Drucker noch kalibrieren, was für den einen oder anderen eine herausforderung ist. Nicht weil es mega kompliziert ist, eher weil man erstmal nicht weiß wo man anfängt und was man wirklich braucht. Ich habe mich da durch gekämpft und bin akutell soweit das er nicht perfekt aber passabel druckt. Ich habe viele Infos aus den Videos vom Cryd-Team, aber der perfekte Rotefaden habe ich da auch nicht gefunden. Deswegen hier nochmal eine Zusammenfassung und Reihenfolge die bei mir am Ende zu einem stimmigen Ergebniss geführt hat. 

Was ihr am besten vorher zurechtlegt:

### Hardware
* Messschieber z.B. [Digital](https://amzn.to/3DHoyH9) 
* genaues Lineal z.B. [Edelstahl Lineal](https://amzn.to/3fiuEFu)(*1)
* Bügelmessschraube z.B. [Analog ](https://amzn.to/3h121Nq)(*1) o. [Digital](https://amzn.to/3sMI7su)
* Klebeband zum einstellen vom Bltouch offset
* Edding
* Taschenlampe um während dem Druck den ersten Layer besser bewerten zu können
* Druckerpapier oder [Fühlerlehre](https://amzn.to/3zuj5C5) für den "Papertest"

### Software

* [SuperSlicer](https://github.com/supermerill/SuperSlicer) - Fork von der beliebten 3D-Druck-Software PrusaSlicer mit einigen Hilfreichen optionen zum Drucker kalibrieren
* Editor für Notizen z.B. [VCS ](https://code.visualstudio.com/)


### Vorbereitung: 

1. Druckbett sauber machen und grob per Hand levelen wenn ihr einen Drucker mit verstellbaren Bett habt. 
2. Nozzel reinigen
3. gleichmässige Temperatur im Raum schaffen (also nicht bei -15 °C und offenem Fenster)
4. Sensor prüfen nicht das euch die Nozzel ins Bett fährt - Bl-Touch
5. Prüfen ob der Drucker auf die Befehl reagiert, einfach z.B. in Mainsail Drucker auf Heizen, Homen und XYZ-Achsen in alle richtungen fahren ob sie richtig rum laufen ***finger am Ausschalter*** :-) Tipp: Wenn ihr kein Display habt, wohl so sein wird wenn ihr das noch nicht mit Klipperscreen eingerichtet habt, nutz das Smartphone. Einfach die lokale IP in den Browser
6. am besten ihr entfernt erst mal bereits geladenes Filament, das müsst ihr eh gleich abschneiden

### Sensor Offset einstellen (Bett u. Extruder kalt)

Falls ihr einen Sensor wie den Bltouch nutzt stellt ihr erstmal den Offset ein.  

Anleitung: [Calibrating probe X and Y offsets](https://www.klipper3d.org/Probe_Calibrate.html#calibrating-probe-x-and-y-offsets)

***Speichern oben Rechts in Mainsail nicht vergessen, Mainsail durchstarten.***

### Extruder Kalibrieren 

    Hier stellt ihr ein die "rotation_distance" ein, das ist die Strecke, die die Achse bei einer vollen Umdrehung des Schrittmotors zurücklegt. Macht das genau, hier braucht ihr ein Lineal.
    Anleitung: [Calibrating rotation_distance on extruders](https://www.klipper3d.org/Rotation_Distance.html) oder hier eine [Video](https://youtu.be/8h9hYSACWhc?t=82)

### PID Tuning 

    Hiermit kalioriert ihr die Temperaturen vom Extruder und vom Bett, dabei fährt er die eingestellte Temperatur öfters an und misst die Werte. 

    Anleitung: [Calibrate PID settings](https://www.klipper3d.org/Config_checks.html?h=pid+tuning#calibrate-pid-settings) einfacher mit den Macros von Cryd-Team siehe [Video](https://youtu.be/8h9hYSACWhc?t=229). 


### Z-Offest - Bed leveling (Bett u. Extruder kalt)

    Hier wird mit hilfe des "paper test" der perfekt abstand von der Nozzel zum Bett eingestellt, macht das sehr genau und lasst euch Zeit und macht es bei bedaf auch mehrmals. 

    Anleitung: [Bed leveling](https://www.klipper3d.org/Bed_Level.html)

    Für Bl-Touch macht ihr hier PROBE_CALIBRATE und für den Vyper ohne Z_ENDSTOP_CALIBRATE
    


