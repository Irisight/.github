# Irisight

![Irisight Banner](profile/assets/IrisghtBanner.png)
This organization's primary language is German. For an english transcript of this file, look [here](profile/README.en-US.MD)
### Irisight ist ein Projekt, welches sich zum Ziel setzt, den Alltag für seheingeschränkte und blinde Menschen zu erleichtern. Dabei nutzt Irisight eine handvoll technischer Lösungen, um die Umwelt des Trägers zu verstehen und wichtige Informationen aus der Umgebung zu filtern, um dem Träger maximale Hilfe zu gewährleisten. Irisight ist Teil des Wettkampfes "Jugend Forscht".

## Informationen & Metadaten

* Diese Organisation dient gerade hauptsächlich als zentrales Hub und zentrale Speicherstelle für unseren Code. Es werden in naher Zukunft öffentliche Repositories erstellt, die den Entwicklungsprozess oder Teile des Projektes beinhalten.
* Irisight ist im Rahmen des Wettkampfes ein privates Projekt, weshalb keine Mitbeteiligung möglich ist.
* Mehr Informationen über Jugend Forscht findest du [hier](https://www.jugend-forscht.de/stiftung-jugend-forscht-e-v.html)

## Technische Informationen
Irisight ist aufgeteilt in zwei Teile, On-Device und Backend. On-Device ist der Teil von Irisight, der auf dem Gerät selber läuft
und dafür zuständig ist, die Umwelt zu erfassen, alle wichtigen Daten herauszufiltern und mit dem Träger zu interagieren. Ein Teil der Daten,
wie position oder spezielle Befehle werden an das Backend gesendet. Das Backend kümmert sich um Aufgaben, für die das Gerät selber nicht ausgestattet sind.
Zu diesen Aufgaben gehören z.B. eine exakt interpretierte Bildbeschreibung, welche nur durch Google Vision erzielt werden kann.

### On-Device

* Der Hauptteil des Codes ist in Python geschrieben und kümmert sich um Ressourcenverteilung und Aufgabenbewältigung.
* Eine lokale Datenbank sorgt dafür, das wichtige Log-Daten und Informationen auch ohne Internet abrufbar sind.
* Ein lokales und offline verfügbares Objekterkennungsmodel sorgt dafür, dass Irisight die Umgebung auch ohne Internet interpretieren kann.
* Irisight verfügt über eine handvoll wichtiger Sensoren, die auch offline relevante Umgebungsinformationen ausmessen.

### Backend

* Das Backend selbst ist aufgeteilt in mehrere Abteile, von denen jedes eine spezifische Aufgabe erledigen soll. 
* Der Maincontroller kümmert sich um die Verarbeitung aller Anfragen und die Kommunikation mit dem Gerät. Er leitet Befehle und Aufgaben automatisch an die entsprechenden Dienste weiter.
* Der Rest-Controller kümmert sich um asynchrone Apiaufrufe (z.b. um das Wetter abzufragen), und informiert den Maincontroller über seine Ergebnisse.
* Der UWB-Controller ist ein separater Dienst, der die Navigation in Gebäuden kontrolliert. Er sendet Daten aus dem UWB-Netzwerk an das Gerät zur Navigation.
* Alle Controller schreiben Log-Daten und wichtige Informationen in einen eigenen Table in einer Datenbank.

> [!NOTE]
> Das ist ein vorläufiges Schema und wird sich im Laufe der Entwicklung an die Aufgaben anpassen.


## Fragen oder Kontakt gesucht?

Schreib uns eine E-Mail auf `info-irisght@lucidev.me` oder kontaktiere uns über GitHub. Mehr Informationen auf https://lucidev.me/projects