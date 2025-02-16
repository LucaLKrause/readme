# README

## Projektname
*Behind The Bar*

## Projektziel
*Behind The Bar ist ein VR-Lernspiel, in dem der Spieler die Rolle des Barkeepers einnimmt und Erfahrungen mit dem Mixen von Getränken sammelt.*

## Credits
*Phillip Trompetter & Luca-Leon Krause*

## Installation & Voraussetzungen
*!!!Link zum Ordner einfügen!!!*

*!!!Wie installiere ich die Datei: git clone <repo-url>!!!*

*Hardware:*

*Oculus Rift S und ihre Controller*

*!!!Was muss der PC können!!!*

*Software: Windows 11, !!!APP!!!*

## Benutzung
*Vor dem Start der .exe musst du sicherstellen, dass die Oculus angeschlossen und die Oculus-App gestartet ist, damit die Brille und die Controller erkannt werden.*

*Insgesamt gibt es drei Modi: Tutorial, Anfänger und Experte.*

*Das Ziel des Spiels ist es, die Rezepte im Anfängermodus zu verinnerlichen und sie im Expertenmodus ohne Hilfe umsetzen zu können.*

## Contribution / Entwicklung

### Aufsetzen der Entwicklungsumgebung
*Die verwendete Unity-Version lautet "Unity (2022.3.45f1)".*

*Verwendete Unity-Packages:*

*Burst*  
*Core RP Library*  
*Custom NUnit*  
*Input System* 
*JetBrains Rider Editor*  
*Mathematics*  
*Oculus XR Plugin*  
*OpenXR Plugin*  
*Post Processing*  
*ProBuilder*  
*Searcher*  
*Settings Manager*  
*Shader Graph*  
*Test Framework* 
*TextMeshPro*  
*Timeline*  
*Unity UI*  
*Universal RP*  
*Universal RP Config*  
*Version Control*  
*Visual Scripting*  
*Visual Studio Code Editor*  
*Visual Studio Editor*  
*XR Core Utilities*  
*XR Interaction Toolkit*  
*XR Legacy Input Helpers*  
*XR Plugin Management*

### Dokumentation der Software
*Hinweise zur Dokumentation der Software.*

### Ordnerstruktur
- **Assets/** → Enthält alle projektbezogenen Ressourcen und Assets.
  - **Notwendige Pakete/** → Beinhaltet die erforderlichen Pakete für das Projekt.
  - **Projekt/** → Hauptordner für projektspezifische Einstellungen und Daten.
    - **Affordance Theme/** → Thematische Assets und Einstellungen.
    - **Farben/** → Farbpaletten und Farbschemata.
    - **Images/** → Bilder, Icons und Grafiken.
    - **Menu Assets/** → Assets für Menüs und Benutzeroberflächen.
    - **NPC/** → Enthält Assets für nicht-spielbare Charaktere.
    - **Prefabs/** → Vorgefertigte Objektvorlagen.
      - **Materials für Prefabs/** → Materialien, die speziell für die Prefabs erstellt wurden.
      - **Prefab für Tablet/** → Spezielles Prefab für Tablet-Objekte.
      - **3D Modelle Asset/** → 3D-Modelle, die im Projekt verwendet werden.
      - **Checkliste/** → Checklisten und ToDo-Listen für das Projektmanagement.
      - **Deko/** → Dekorative Elemente.
      - **Deko für Gläser/** → Dekor für Glasobjekte.
      - **Flaschen/** → Assets für Flaschen-Objekte.
      - **Flüssigkeit/** → Enthält Flüssigkeitseffekte oder -simulationen.
      - **Gläser/** → Modelle oder Assets von Gläsern.
    - **Shader Flüssigkeit/** → Shader für Flüssigkeitseffekte.
    - **Skripte/** → Alle Skripte und Code-Dateien.
    - **Sounds/** → Audio-Dateien, Musik und Soundeffekte.
    - **Tablet Asset/** → Assets, die speziell für Tablet-Anwendungen vorgesehen sind.
  - **Scenes/** → Beinhaltet alle Spiel-Level und Menü-Szenen.
  - **Umgebung/** → Enthält Umgebungsdaten und Szeneneinstellungen.
  - **Unity, VisualScripting, Generated/** → Automatisch generierte Dateien (Unity, Visual Scripting etc.).
  - **XR/** → Assets für erweiterte Realität (AR/VR) und XR-Anwendungen.
- **Packages/** → Alle Pakete, die für die Ausführung des Projekts relevant sind.

## Eigenleistung

###Eigene Werke (von Phillip Trompetter und Luca-Leon Krause)
  | Kategorie         |     Name           |     
  |-------------------|--------------------|
  | **Eigene 3D-Modelle** |                |                     
  |                  |      3D Modelle Asset (Ordner)|                      
  |                  |      Deko (Ordner)            |    
  |                  |  Deko für Gläser (Ordner)     | 
  |                  |    Fluessigkeit (Ordner)      |  
  |                  |    Gläser (Ordner)            | 
  |                  |  SalzPfeffer (Ordner)         |
  |                  |                               | 
  | **Skripte**      |                               | 
  |                  |  BarlöffelAudio.cs            |
  |                  | Behälter.cs                   |
  |                  |  DeckelSocketInteraction.cs   |
  |                  |  DrinkDisplayUI.cs            |
  |                  |  DrinkRecepies.cs             |
  |                  |  DrinkRecipeModel.cs          |
  |                  |  FillAnimation.cs             |
  |                  |  Fillspices.cs                |
  |                  |  FillstandHUD.cs              |
  |                  |  FillstandHUDJigger.cs        |
  |                  |  FillistundHUDShaker.cs       |
  |                  |  HoverTextController.cs       |
  |                  |  HUDFollowCamara.cs           |
  |                  |  Jigger.cs                    |
  |                  | JiggerAttachPoints.cs         |
  |                  |LeaveScene.cs                  |
  |                  |  Mülleimer.cs                 |
  |                  |  ObjektAnvisieren.cs          |
  |                  |  RespawnObject.cs             |
  |                  |  RespawnObjectForMülleimer.cs |
  |                  |  SelectDrink.cs               |
  |                  |  Shaker.cs                    |
  |                  |  Spülbecken.cs                |
  |                  |  StößelAudio.cs               |
  |                  |  TabletNavigation.cs          |
  |                  |  TestDetecter.cs              |
  |                  |  TestDetecterExpert.cs        |
  |                  |  Tutorial Sprechblasen.cs     |  
  |                  | Zuckerl.öffel.cs              | 
  |                  | MenuManager.cs                |
  | **Bilder**       |                               |                
  |                  |Barlöffel                      |                
  |                  | Shaker                        |               
  |                  | Jigger                        |
  |                  |  Stößel                       |
  |                  |  Teelöffel                    |
  |                  | Tumbler Glas                  |
  |                  |Longdrink Glas                 |
  |                  | Hurricane Glas                |
  |                  | Coupette Glas                 |
  |                  | Cocktail Glas                 | 
  
  
###Fremde Werke
  | Kategorie                       |      Name          | Autor          | Link |
  |---------------------------------|--------------------|----------------|------|
  | **Animationen**                 |                    | Keine Autoren Bekannt               | Alle Animationen sind von https://www.mixamo.com/#/. Einzelne Links nicht möglich|  
  |                                 | Drinking           |                |      |
  |                                 | standing Idel      |                |      |
  |                                 | daumen hoch, sitzen|                |      |
  |                                 | letzte talk        |                |      |
  |                                 | nod                |                |      |
  |                                 | Normal Sitzen      |                |      |
  |                                 | Pointing           |                |      |
  |                                 | SCHACH             |                |      |
  |                                 | sit                |                |      |
  |                                 | Sitzen hand bewegung    |           |      |
  |                                 | Sitzen und Arm Kratzen  |           |      |
  |                                 | Sitzen und reden        |           |      |
  |                                 | stand talk              |           |      |
  |                                 | talking            |                |      |
  |                                 |                    |                |      |
  | **Bilder**                      |                    |                |      |
  |                                 | Space UI pack      | 	Deketele Creations   | https://dante-deketele.itch.io/simple-space-ui-pack|
  |                                 | Freie notebook Mockup Vektor| freepick  |https://de.freepik.com/vektoren-kostenlos/freie-notebook-mockup-vektor_726387.htm|
  |                                 | Koko Caramel       |      ---       |https://uigradients.com/#NeonLife|
  |                                 |chat bubbles, to chat with, chat bubbles png |    ---    |https://www.pngegg.com/en/png-ddmoy |
  |                                 |Vodka-E             |spirituosenworld|https://spirituosenworld.de/cocktails/vodka-e?srsltid=AfmBOoraustO-ehZ3amfooxdJafK3KScgGFk14qS_jG6URC7A68_yxqR|
  |                                 |Long Island Iced Tea|      ---       |https://www.bargpt.app/ai-cocktail-recipe/long-island-iced-tea7506 |
  |                                 |Manhattan Cocktail  |Slawomir Fajer  |https://www.essen-und-trinken.de/rezepte/59761-rzpt-manhattan-cocktail|
  |                                 |Negroni             |Evgeny Karandae |https://www.essen-und-trinken.de/rezepte/59764-rzpt-negroni|
  |                                 |Cola Korn           |     ---        |https://www.echter-nordhaeuser.de/cocktails-co/longdrinks/korn-doppelkorn/korn-cola/|
  |                                 |Cola Rum            |     ---        |https://www.schweppes.de/mixen/cocktails/rum-cola|
  |                                 |Whiskey Cola        |Lukas           |https://www.maltwhisky.de/whiskey-cola/|
  |                                 |Wodka Sou           |     ---        |https://www.schweppes.de/mixen/cocktails/wodka-sour|
  |                                 |Daiquiri            |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |
  | **Sounds**                      |                    |                |      |
  |                                 | glug glug glug     | IwanPlays      |https://pixabay.com/de/sound-effects/glug-glug-glug-39140/ |
  |                                 | martini_shake_pour | philberts      |https://pixabay.com/de/sound-effects/martini-shake-pour-34765/|
  |                                 | Stirring a cup of coffee | greatnessdon |https://pixabay.com/de/sound-effects/stirring-a-cup-of-coffee-193831/|
  |                                 | Squeezing Lemon    | PhilllChabbb   |https://pixabay.com/de/sound-effects/squeezing-lemon-72629/|
  |                                 | Drink pour         | mfearnley      |https://pixabay.com/de/sound-effects/drink-pour-7169/|
  |                                 | Water Pour and Drink     | joeboarder14    |https://pixabay.com/de/sound-effects/water-pour-and-drink-73447/|
  |                                 | Podcast Jazz Waltz Cozy Relaxing Vibes  | Denis-Pavlov-Music |https://pixabay.com/music/traditional-jazz-podcast-jazz-waltz-cozy-relaxing-vibes-233733/|
  |                                 |Daiquiri            | ---            |https://www.bacardi.com/de/de/rum-cocktails/daiquiri/|
  |                                 |Mojito              | Gutekueche     |https://www.gutekueche.at/mojito-cocktail-rezept-17926|
  |                                 |Caipirinha          | Gutekueche     |https://www.gutekueche.at/caipirinha-cocktail-rezept-17919|
  |                                 |Sex on the Beach    | Gutekueche     |https://www.gutekueche.at/sex-on-the-beach-cocktail-rezept-18119|
  |                                 |Bloody Mary         | Gutekueche     |https://www.gutekueche.at/sex-on-the-beach-cocktail-rezept-18119|
  | **3D-Modelle und Materialien**  |                    |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |
  | **Skripte**                     |                    |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |
  | **Shader-Graph**                |                    |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |

