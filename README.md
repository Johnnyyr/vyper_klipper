# Vyper Klipper

# Anycubic Vyper Klipper installieren u. kalibrieren

Da ich doch einige Probleme hatte mir alle Daten zusammen zu suchen, hier meine Erfahrungen, Links und Tipps.

Kurz zu Klipper: 

Im Gegensatz zur Marlin Firmware läuft die Berechnung der Bewegungsdaten auf dem Pi und nicht auf dem Mainboard. Das ermöglicht schnelleres Drucken bei gleichbleibenden oder sogar besseren Ergebnis. Der wohl größte Vorteil ist die Änderung der Firmware ohne lästiges Flashen.


> Ich verlinke immer auf die Original-Doku in Englisch, ist gibt aber auch eine [Übersetzung](https://crydteam.gitbook.io/crydteam-wiki/3d-druck/faq/deutsch-uebersetzung-klipper-dokumentation) von J. Müller auf Deutsch, danke dafür. Die meisten Erklärungen beziehen sich auf den Vyper und Mainsail.
> 

Kein Anspruch auf Vollständigkeit.


## 1. Hardware

- Raspberry Pi ab Zero 2 W
  
- SD-Karte 16 G+
  
- Pi-Netzteil mit ausreichend Power (kein Smartphone ladegeräte)
  
- gutes USB-Kabel um den Drucker zu verbinden
  
- optional Webcam, Pi-Touchscreen
  

## 2. Software

- Firmware
  
  - [Klipper](https://www.klipper3d.org/) (Firmware für den Drucker)
  
- OS/Oberfläche/Benutzerschnittstelle
  
  - [MainsailOS](https://github.com/mainsail-crew/mainsail)
    
  - [Fluidd](https://github.com/fluidd-core/fluidd)
    
  - [DWC2](https://github.com/Stephan3/dwc2-for-klipper)
    
  - [Octoprint](https://github.com/OctoPrint/OctoPrint)
    
- Pakete und Images
  
  - [Raspbian Pi OS](https://www.raspberrypi.com/software/)
    
  - [KIAUH](https://github.com/th33xitus/kiauh) - Skriptsammlung (quasi die All-in-one-Lösung) *Empfehlung*
    
- Tools
  
  - [SD-Card Formater ](https://www.sdcard.org/downloads/formatter/) (SD-Karte sauber formatieren)
    
  - [Raspberry Pi Imager](https://www.raspberrypi.com/software/) (AIO-Tool zum Pi-OS flashen)
    
  - [Cyberduck](https://cyberduck.io/) (SFTP-Tool um die Firmware vom Pi abzuholen, geht auch mit dem Terminal)
    

---

## 3. Installation (Speed Variante) und Empfehlung

#### 3.1 Varianten

1. [KIAUH](https://github.com/th33xitus/kiauh) Image herunterladen, mit dem [Raspberry Pi Imager](https://www.raspberrypi.com/software/) flashen und der Anleitung von [KIAUH](https://github.com/th33xitus/kiauh) auf GIT folgen.
  
2. [Raspberry Pi Imager](https://www.raspberrypi.com/software/) öffnen, auf "OS WAEHLEN" klicken -> "Other specific-purpose OS" -> "3D printing" -> "Mainsail OS" auswählen und flashen. Anleitung von [Klipper](https://www.klipper3d.org/Installation.html) lesen, da sind alle weiteren Schritte erklärt.
  
3. [Raspberry Pi Imager](https://www.raspberrypi.com/software/) öffnen und ein "Raspberry PI OS" auswählen, flashen und die den Rest per Hand installieren. Anleitung von [Klipper](https://www.klipper3d.org/Installation.html) lesen, da sind alle weiteren Schritte erklärt.
  

###### Firmware auf den Drucker flashen fertig. Weiter zu Schritt 7. Drucker Kalibrieren.

#### 3.2 Links zu ausführlichen Installations-Anleitungen

- Webseiten
  
  - Offizielle Anleitung von [Klipper](https://www.klipper3d.org/Installation.html)
    
  - Anleitung von [Stone-Time](https://stone-time.de/docs/allgemeine-anleitung-zum-erzeugen-der-firmware/)
    
- Video:
  
  - Sehr gutes Video vom [Cryd-Team](https://youtu.be/S_K7iB3jYMs) (Teil 1 und 2)

## 4. Tipps zur Installation, die einem ein paar Probleme ersparen

- Pi Benutzername nicht ändern
- nicht nervös werden, die Installation dauert je nach Variante
- Variante 1. geht am schnellsten und ist eher die klicky bunte variante für die nicht Hardcore-Nerds
- [Vorlagen](https://github.com/Klipper3d/klipper/tree/master/config) für eure Firmware je nach Drucker, liegen aber auch schon auf dem Pi und können kopiert werden
- Fertige Firmware Vorlagen findet ihr haufenweise im Netz z.B. für Vyper oder Ender 3, mit oder ohne Bltouch
- Schaut vorher nach, welches Mainboard in eurem Drucker verbaut ist.
- mit Shift+Command+X könnt ihr im [Raspberry Pi Imager](https://www.raspberrypi.com/software/) das WLAN einstellen und weiter Optionen einstellen - Username auf "pi" lassen.
- wenn es nicht gleich klappt, bekommt ihr bestimmt Hilfe auf diversen Discord-Servern oder Foren. (links ganz unten)

## 5. Benutzeroberfläche, Vorlagen und Makros einrichten

Am besten ihr schaut ihr dieses Video vom [„Cryd-Team“](https://youtu.be/6RBNRVgC2Go?t=549) an, besser kann man es nicht erklären 

Macros etc. bekommt auf dem Git vom „Cryd-Team“ oder direkt bei [Klipper](https://github.com/Klipper3d/klipper/blob/master/config/sample-macros.cfg)

## 6. Sensor testen und einrichten

Falls ihr in eurer Vorlage der printer.cfg noch nicht euren richtigen Sensor drin stehen habt, dann macht das jetzt. Für den Vyper braucht ihr mit der printer.cfg vom "Cryd-Team" nichts weiter machen. Für den [BL-Touch](https://www.klipper3d.org/BLTouch.html) und [hier](https://www.klipper3d.org/Config_Reference.html?h=probe#probe)

## 7. Kalibration

Wenn alles installiert ist, "müsst" ihr euren Drucker noch kalibrieren. Ich habe mich dadurch gekämpft und bin aktuell so weit, dass er nicht perfekt, aber passabel druckt. Ich habe viele Informationen aus den Videos vom „Cryd-Team“, aber der perfekte rote Faden habe ich da auch nicht gefunden. Deswegen hier nochmal eine Zusammenfassung und Reihenfolge, die bei mir am Ende zu einem stimmigen Ergebnis geführt hat.

Was ihr am besten vorher zurechtlegt:

### Hardware

- Messschieber, z.B. [Digital](https://amzn.to/3DHoyH9)
  
- genaues Lineal, z.B. [Edelstahl Lineal](https://amzn.to/3fiuEFu)*
  
- Bügelmessschraube z.B. [Analog](https://amzn.to/3h121Nq)* o. [Digital](https://amzn.to/3sMI7su)*
  
- Klebeband zum Einstellen vom BL-Touch offset
  
- Edding
  
- Taschenlampe, um während dem Druck den ersten Layer besser bewerten zu können
  
- Druckerpapier oder [Fühlerlehre](https://amzn.to/3zuj5C5)* für den "Papertest"
  

### Software

- [SuperSlicer](https://github.com/supermerill/SuperSlicer) - Fork von der beliebten 3D-Druck-Software PrusaSlicer mit einigen Hilfreichen Optionen zum Drucker Kalibrieren
  
- Editor für Notizen, z.B. [VCS ](https://code.visualstudio.com/)
  

### Vorbereitung:

1. Druckbett sauber machen und grob per Hand leveln, wenn ihr einen Drucker mit verstellbaren Bett habt.
  
2. Nozzel reinigen
  
3. Gleichmäßige Temperatur im Raum schaffen (-15 °C und offenes Fenster, häm nein)
  
4. Sensor prüfen nicht das euch die Nozzel ins Bett fährt - BL-Touch
  
5. Prüfen, ob der Drucker auf die Befehle reagiert, einfach z.B. in Mainsail Drucker auf Heizen, Homen und XYZ-Achsen in alle Richtungen fahren, ob sie richtig rumlaufen ***Finger am Ausschalter*** :-)
  
  *Tipp: Wenn ihr kein Display habt, was wohl so sein wird, wenn ihr das noch nicht mit Klipperscreen eingerichtet habt, nutzt das Smartphone. Einfach die lokale IP in den Browser*
  
6. Am besten ihr entfernt erst mal bereits geladenes Filament, das müsst ihr eh gleich abschneiden
  
7. Im Mainsail "Update Mange" checken, ob es updates gibt und die durchführen.
  

### Sensor Offset einstellen (Bett u. Extruder kalt)

Falls ihr einen Sensor wie den BL-Touch nutzt, stellt ihr erstmal den Offset ein.

- Anleitung: [Calibrating probe X and Y offsets](https://www.klipper3d.org/Probe_Calibrate.html#calibrating-probe-x-and-y-offsets)

***Speichern oben Rechts in Mainsail nicht vergessen, Mainsail durchstarten.***

### Extruder Kalibrieren

Hier stellt ihr ein die "rotation_distance" ein, das ist die Strecke, die die Achse bei einer vollen Umdrehung des Schrittmotors zurücklegt. Macht das genau, hier braucht ihr ein Lineal.

- Anleitung: [Calibrating rotation_distance on extruders](https://www.klipper3d.org/Rotation_Distance.html) oder hier eine [Video](https://youtu.be/8h9hYSACWhc?t=82)

***Speichern oben Rechts in Mainsail nicht vergessen, Mainsail durchstarten.***

### PID Tuning

Hiermit kalioriert ihr die Temperaturen vom Extruder und vom Bett, dabei fährt er die eingestellte Temperatur öfters an und misst die Werte.

- Anleitung: [Calibrate PID settings](https://www.klipper3d.org/Config_checks.html?h=pid+tuning#calibrate-pid-settings) einfacher mit den Macros von Cryd-Team siehe [Video](https://youtu.be/8h9hYSACWhc?t=229).

***Speichern oben Rechts in Mainsail nicht vergessen, Mainsail durchstarten.***

### Z-Offest - Bed leveling (Bett u. Extruder kalt)

Hier wird mithilfe des "paper test" der perfekt abstand von der Nozzel zum Bett eingestellt, macht das sehr genau und lasst euch Zeit und macht es bei bedaf auch mehrmals.

Anleitung: [Bed leveling](https://www.klipper3d.org/Bed_Level.html)

Für Bl-Touch macht ihr hier PROBE_CALIBRATE und für den Vyper ohne Z_ENDSTOP_CALIBRATE

***Speichern oben Rechts in Mainsail nicht vergessen, Mainsail durchstarten.***

### Heigtmap in Mainsail erstellen

Rechts im Menü auf heigthmap klicken und dann auf calibration, den default namen nicht ändern.

***Speichern oben Rechts in Mainsail nicht vergessen, Mainsail durchstarten.***

## 8. SuperSlicer

- [SuperSlicer](https://github.com/supermerill/SuperSlicer/releases) downloaden, installieren, den Assitanten abbrechen oder durch klicken(Vyper ist nicht dabei) und z.B. das [Profi-Bundel](https://github.com/cryd-s/Vyper_extended/tree/main/SuperSlicer) vom "Cryd-Team" laden (File-Import).
  
- Startcode unter Printer Settings - Costum G-Code folgendes eintragen
  
  Start G-Code
  

```gcode
 `START_PRINT BED={first_layer_bed_temperature} EXTRUDER={first_layer_temperature}`
```

    End G-code

```gcode
M117 Print End
END_PRINT
```

- Playlist [SuperSlicer Grundlagen - Cryd-Team](https://www.youtube.com/watch?v=PoiEC6XshnQ&list=PLWqnUinimMN08AzrfPVVr-v3swkEkcgob) anschauen um die Grundlagen von SuperSlicer zu lernen.

## 9. Kalibrierungs-Drucke

Klipper ist installiert und die Grundkonfigurationen sind eingetragen und kalibriert. Jetzt müssen noch ein paar Einstellungen im SuperSlicer gemacht werden, um dafür die richtigen Werte zu finden, bietet euch SuperSlicer eine Menge Kalibrierungstools, die euch das Leben echt einfacher machen. Natürlich gibt es auch wieder ein Video vom "Cryd-Team" dazu schaut euch mal die [Playlist](https://www.youtube.com/watch?v=DN3v1cmLSM8&list=PLWqnUinimMN3Upj3a3BzVFsixutHB0ZP5&index=4) an, wir sind jetzt beim Teil 4.

Wenn ihr das alles gemacht habt und die Drucke halbwegs sauber aussehen, Glückwunsch! Falls ihr nicht zum Ziel kommt, fragt im Discord oder z.B. im Forum der [3D Druck Community](https://www.3d-druck-community.de), da kannst du einen Einstellfahrplan machen und bekommst sehr professionellen Support. 

Für alle Neuling, keine Angst das Kalibrieren, verbessern geht immer weiter. Ein anderes Filament und vieles geht von vorne los. Man gewöhnt sich dran und lernt nie aus. Viel Erfolg!


## Danksagung

Vielen Dank für die tollen Videos und den Support über [Discord](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbkkzTHFHa1I3VExHOGVydVdXTG1sTVV3MVA3QXxBQ3Jtc0tsYzR2VTcyUTUzM1YxMnhGbzh0ZVhBRWgyYnR5U0lYUGZiRGFRQklaZTQ5ZzhPa2lSLVFkcENfXzRqYjhYTG1ya0pSeDZ4MU9GY3Y0YzdIbkc3ZHlwVDZERFh0ZkZWM3lBd1p5Qk9JTEl1V3BHVkUyZw&q=https%3A%2F%2Fdiscord.gg%2F2vEVdejeBZ&v=DN3v1cmLSM8) an das "Cryd-Team"

Danke auch an den Entwickler von Klipper, Mainsail usw. ihr leistet eine Mega Arbeit.
