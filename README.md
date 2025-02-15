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
  
###Fremde Werke
  | Kategorie                       |      Name          | Autor (Dritter) | Link |
  |---------------------------------|--------------------|----------------|------|
  | **Animationen**                 |                    |                |      |
  |                                 | Drinking           |                |      |
  |                                 | standing Idel      |                |      |
  |                                 | daumen hoch, sitzen|                |      |
  |                                 | letzte talk        |                |      |
  |                                 | nod                |                |      |
  |                                 | Normal Sitzen      |                |      |
  |                                 | Pointing           |                |      |
  |                                 | SCHACH             |                |      |
  |                                 | sit                |                |      |
  |                                 | Sitzen hand bewegung    |                |      |
  |                                 | Sitzen und Arm Kratzen  |                |      |
  |                                 | Sitzen und reden        |                |      |
  |                                 | stand talk              |                |      |
  |                                 | talking            |                |      |
  | **Bilder**                      |                    |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |
  | **Sounds**                      |                    |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |
  | **3D-Modelle und Materialien**  |                    |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |
  | **Skripte**                     |                    |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |
  | **Shader-Graph**                |                    |                |      |
  |                                 |                    |                |      |
  |                                 |                    |                |      |

