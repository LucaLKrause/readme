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

@startuml
' ---------- Klassen mit Assoziationen ----------

class Behälter {
    - Dictionary<string, int> tagCounters
    - int füllMengeMax = 350
    - int füllMenge = 0
    - GameObject flüssigkeitInhalt
    - float startFill
    - float currentFill
    - float maxFill
    - bool nurEinmal = false
    - HashSet<string> booleanTags
    - HashSet<string> füllMengeTags
    - Verschiedene Booleans für Zutaten (z.B. istBraunerZucker, istEiswürfel, ...)
    - GameObject eisPrefab
    - GameObject crushedIcePrefab
    - Transform spawnPoint
    - GameObject Prefabs für Dekorationen (z.B. zitronePrefab, minzblattPrefab, ...)
    - Transform Spawnpunkte für Dekorationen (z.B. scheibenSpawnPoint, minzblattSpawnPoint, ...)
    - HashSet<GameObject> pendingObjects
    - Dictionary<GameObject, Coroutine> activeCoroutines
    
    + void Start()
    + void OnTriggerEnter(Collider other)
    + void OnTriggerExit(Collider other)
    + IEnumerator WaitBeforeSetBoolean(string tag, GameObject obj)
    + void SpawnPrefab(GameObject prefab, Transform spawnPoint)
    + void Update()
    + void UpdateFill()
    + void SetBooleanForTag(string tag)
    + Dictionary<string, int> GetTagCounters()
    + void SetzeBooleans(bool eiswürfel, bool crushedIce)
    + void ErhalteInhalt(string tag, int menge)
    + void SetIstMixer(bool mixerStatus)
    + void SetIstBraunerZucker(bool value)
    + void SetIstWeißerZucker(bool value)
    + void SetIstSalz(bool value)
    + void SetIstPfeffer(bool value)
    + void SetIstTabasco(bool value)
    + void SetIstWorcestersauce(bool value)
}

class FillAnimation {
    +GameObject tropfenPrefab
    +GameObject[] tropfenPrefabs
    +Transform parentObject
    +float tiltThreshold
    +float spawnRate
    +float tropfenSpeed
    +float tropfenSize
    +string flüssigkeitTag
    +Vector3 spawnPoint
    -float spawnTimer
    +AudioSource audioSource
    +AudioClip tropfenSound
    -bool isSpawning
    +void Start()
    +void Update()
    +void SpawnTropfen()
    +bool IsTilted()
    +float GetTiltAngle()
    +void StartTropfenSound()
    +void StopTropfenSound()
}

class TestDetecter {
    + string currentDrink
    + TabletNavigation tabletNavigation
    + DrinkDisplayUI drinkDisplayUI
    + Animator animator
    + string boolParameterName
    + bool toggleBool
    - GameObject clonedObject
    + Transform targetParent
    + AudioSource audioSource
    + AudioClip audioClip
  
    + void Start()
    + void Update()
    + void OnTriggerEnter(Collider other)
    - IEnumerator ResetToggleBool()
    - IEnumerator PlaySoundAfterDelay(float delay)
    - void EvaluateDrink(Behälter objScript, Collider other)
    - string EvaluateQuantities(DrinkRecipeModell recipe, Dictionary<string, int> tagCounters)
    - bool EvaluateSpecialIngredients(DrinkRecipeModell recipe, Behälter objScript)
    - bool EvaluateTools(DrinkRecipeModell recipe, Behälter objScript)
    - bool EvaluateDecorations(DrinkRecipeModell recipe, Behälter objScript)
    - bool CheckSpecialIngredient(string special, Behälter objScript)
    - bool CheckTool(string tool, Behälter objScript)
    - bool CheckDecoration(string garnish, Behälter objScript)
    - bool IsCorrectGlass(Collider other)
    - string GetExpectedGlass()
}

class DrinkDisplayUI {
    + GameObject drinkCanvas
  + Transform checklistContainer
  + GameObject checklistItemPrefab
  - Coroutine hideCanvasCoroutine
  + GameObject coinPrefab
  + Transform[] coinSpawnPositions
  - List<GameObject> spawnedCoins

  + void ShowDrinkChecklist(DrinkRecipeModell recipe, Dictionary<string, int> tagCounters, Behälter objScript, Collider other)
  - void AddChecklistItems(Dictionary<string, int> requiredItems, Dictionary<string, int> actualItems)
  - void AddChecklistItems(List<string> requiredItems, Behälter objScript)
  - void AddGlassChecklistItem(string requiredGlass, Collider other)
  - void AddChecklistItem(string itemName, bool isChecked)
  - IEnumerator FixChecklistPosition()
  - bool CheckItemPresence(string item, Behälter objScript)
  + void HideDrinkFacts()
  - IEnumerator HideCanvasAfterDelay(float delay)
  + void SpawnCoins(string rating)
  + void ResetCoins()
}

class Shaker {
    - Dictionary<string, int> tagCounters
  + int füllMengeMax
  + int füllMenge
  + GameObject flüssigkeitObject
  + float startFill
  + float currentFill
  + float maxFill

  + bool istBraunerZucker
  + bool istWeißerZucker
  + bool istSalz
  + bool istPfeffer
  + bool istTabasco
  + bool istWorcestersauce
  + bool istBarlöffel
  + bool istMixer

  - HashSet<string> booleanTags
  - HashSet<string> füllMengeTags

  - GameObject zielBehälter
  - Transform parentTransform
  - Vector3 lastParentPosition
  - Vector3 lastVelocity

  - float shakeSensitivity
  - float shakeTimer
  - float requiredShakeTime

  + DeckelSocketInteraction deckelSocketInteraction

  - AudioSource shakeSound
  + AudioClip shakingClip

  - AudioSource umfüllenSound
  + AudioClip umfüllenClip
  - bool umfüllenSoundAbgespielt

  + void Start()
  + void Update()
  - bool IsShaking()
  + void OnTriggerEnter(Collider other)
  + void ErhalteInhalt(string inhaltTag, int menge)
  + void UpdateFill()
  - void SetBooleanForTag(string tag)
  + Dictionary<string, int> GetTagCounters()
  - void ÜbertrageInhaltAnBehälter(Behälter behälterScript)
}

class Jigger {
    + int füllMengeMax
  + int füllMenge
  + string aktuelleFlüssigkeit
  + GameObject flüssigkeitObject
  + float startFill
  + float currentFill
  + float maxFill
  + DeckelSocketInteraction deckelSocketInteraction
  + AudioSource audioSource
  + AudioClip soundClip
  
  - bool soundAbgespielt
  - readonly HashSet<string> erlaubteFlüssigkeiten

  + void Start()
  + void OnTriggerEnter(Collider other)
  + void Update()
  + void UpdateFill()
}

class TabletNavigation {
    + GameObject mainScreen
  + GameObject[] pages
  + Button[] pageButtons
  + Button[] backButtons
  + Button[] selectButtons
  + string[] drinkNames
  + GameObject shieldPrefab
  + string selectedDrink
  - Button lastSelectedButton
  - GameObject lastShield
  - Button lastSelectedPageButton

  + void Start()
  + void ShowMainScreen()
  + void ShowPage(int index)
  + void SelectDrink(int index)
}

class DrinkRecipeModell {
     - ingredients: Dictionary<string, int>
  - specialItems: List<string>
  - tools: List<string>
  - deko: List<string>
  - glasBehälter: string
  + DrinkRecipeModell(ingredients: Dictionary<string, int>, specialItems: List<string>, tools: List<string>, deko: List<string>, glasBehälter: string)
}

' ---------- Assoziationen ----------

TestDetecter --> DrinkDisplayUI 
TestDetecter --> Behälter 
TestDetecter --> TabletNavigation 

DrinkDisplayUI --> Behälter 
DrinkDisplayUI --> DrinkRecipeModell 

Shaker --> Behälter 
Shaker --> FillAnimation

Jigger --> Behälter 
Jigger --> FillAnimation 

Behälter --> FillAnimation 
Behälter --> DrinkRecipeModell 

TabletNavigation --> DrinkRecipeModell



@enduml


### Ordnerstruktur
- **Assets/** → Enthält alle projektbezogenen Ressourcen und Assets.
  - **Notwendige Pakete/** → Bwinhaltet Unity-Pakete wie z.B. XR.
  - **Projekt/** → Hauptordner für projektspezifische Einstellungen und Daten.
    - **Affordance Theme/** → Visuelle Feedback-Elemente für interaktive Objekte.
    - **Farben/** → Farbpaletten und Farbschemata.
    - **Images/** → Texturen und Bilder (z. B. für Tablet-UI).
    - **Menu Assets/** → Skripte, Fonts und Audio für Menü Szene.
    - **NPC/** → Animationen des Getränke-testenden NPCs.
    - **Prefabs/** → Wiederverwendbare Objekte und Komponenten.
      - **Materials für Prefabs/** → Materialien für Prefab-Objekte (z. B. Glas, Metall).
      - **Prefab für Tablet/** → Spezielles Prefab für Tablet-Objekte.
      - **3D Modelle Asset/** → 3D-Modelle, die im Projekt verwendet werden.
      - **Checkliste/** → UI-Prefabs für die interaktive Aufgabenliste.
      - **Deko/** → Dekorative Elemente.
      - **Deko für Gläser/** → Dekor für Glasobjekte.
      - **Flaschen/** → Vordefinierte Flaschen-Prefabs mit Flüssigkeitslogik.
      - **Flüssigkeit/** → Effekte für Tropfen und Flüssigkeitsbewegung.
      - **Gläser/** → Modelle oder Assets von Gläsern.
    - **Shader Flüssigkeit/** → Custom Shader für realistische Flüssigkeitssimulation in Gläsern.
    - **Skripte/** → Alle Skripte und Code-Dateien.
    - **Sounds/** → Audio-Dateien, Musik und Soundeffekte.
    - **Tablet Asset/** → Externes 3D-Tablet-Modell (aus dem Asset Store).
  - **Scenes/** → Beinhaltet alle Spiel-Level und Menü-Szenen.
    - **Menu** → Hauptmenü.
    - **Tutorial** → Lernmodus.
    - **Anfänger** → Modus mit Anleitung.
    - **Experte** → Modus ohne Hilfe.
    - **Basic/Tutorial** → Entwicklertests.
  - **Umgebung/** → 3D-Modelle und Texturen für die Barumgebung (z.B. Tische, Theke, Wände etc.).
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
  |                  |                               |
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
  | **Animationen**                 |                    | Keine Autoren Bekannt | Alle Animationen sind von https://www.mixamo.com/#/. Einzelne Links nicht möglich|  
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
  |                                 |                    |                |      |
  | **3D-Modelle und Materialien**  |                    |                |      |
  |                                 |VR-Game-Jam-Template|Valem Tutorials |https://github.com/ValemVR/VR-Game-Jam-Template|
  |                                 |Stylized NPC - Peasant Nolant (DEMO) |WINGED BOOTS STUDIO|https://assetstore.unity.com/packages/3d/characters/humanoids/fantasy/stylized-npc-peasant-nolant-demo-252440|
  |                                 |Real Stars Skybox Lite|GEOFF DALLIMORE|https://assetstore.unity.com/packages/3d/environments/sci-fi/real-stars-skybox-lite-116333|
  |                                 |Low Poly Chess Pack |BROKEN VECTOR   |https://assetstore.unity.com/packages/3d/props/low-poly-chess-pack-50405|
  |                                 |Low-Poly Simple Nature Pack|JUSTCREATE|https://assetstore.unity.com/packages/3d/environments/landscapes/low-poly-simple-nature-pack-162153|
  |                                 |3D Low Poly Tools, Weapons & Containers|NEXUSARCADESTUDIO|https://assetstore.unity.com/packages/3d/environments/landscapes/low-poly-simple-nature-pack-162153|
  |                                 |WasteOvergrowth - Comprehensive Trash and Waste Pack|SENTE-ASSEMBLY|https://assetstore.unity.com/packages/3d/environments/wasteovergrowth-comprehensive-trash-and-waste-pack-290387|
  |                                 |Gold Coins          |DEVTOID         |https://assetstore.unity.com/packages/3d/props/gold-coins-1810|
  |                                 |Cabin Environment   |GREGORY SEGURU  |https://assetstore.unity.com/packages/3d/environments/cabin-environment-98014|
  |                                 |Free Wood Door Pack |BIOSTART        |https://assetstore.unity.com/packages/3d/props/interior/free-wood-door-pack-280509|
  |                                 |PBR Materials Sampler Pack|INTEGRITY SPFTWARE & GAMES|https://assetstore.unity.com/packages/2d/textures-materials/pbr-materials-sampler-pack-40112|
  |                                 |World Materials Free|AVIONX          |https://assetstore.unity.com/packages/2d/textures-materials/world-materials-free-150182|
  |                                 |Kitchen Furniture Starterpack|MAVI3D |https://assetstore.unity.com/packages/3d/props/furniture/kitchen-furniture-starterpack-209331|
  |                                 |Bar / Interior - Functional Low Poly assets|FRIES and SEAGULL|https://assetstore.unity.com/packages/3d/props/interior/bar-interior-functional-low-poly-assets-306976|
  |                                 |Bar Props           |SIMPLEMODELSFORME|https://assetstore.unity.com/packages/3d/props/barprops-137130|
  |                                 |Stylized Wood Textures|CAMISADO STUDIOS|https://assetstore.unity.com/packages/2d/textures-materials/wood/stylized-wood-textures-213607|
  |                                 |                    |                |      |
  | **Skripte**                     |                    |                |      |
  |                                 |AudioManager.cs     |Valem Tutorials |https://www.youtube.com/watch?v=apnfGuMI0Dc&list=PLuIdYvsj2nVOyXBFzNaDLoxbA6ecDBr38&index=24|
  |                                 |PlayAudioFromAudioManager.cs | Valem Tutorials |https://www.youtube.com/watch?v=apnfGuMI0Dc&list=PLuIdYvsj2nVOyXBFzNaDLoxbA6ecDBr38&index=24|
  |                                 |UIAudio.cs          | Valem Tutorials|https://www.youtube.com/watch?v=apnfGuMI0Dc&list=PLuIdYvsj2nVOyXBFzNaDLoxbA6ecDBr38&index=24|
  |                                 |Wobble.cs           |Binary Lunar    |https://www.youtube.com/watch?v=eIZgPAZx56s|
  |                                 |                    |                |      |
  |  **Shader-Graph**               |                    |                |      |
  |                                 |LiquidWobbleShader  |Binary Lunar    |https://www.youtube.com/watch?v=eIZgPAZx56s|

