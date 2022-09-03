Modul "kompendien-vorlage-v10" (Vorlage für eigene Kompendien) für Foundry VTT **Version 10**
Die ältere Version 9 Fassung des Moduls ist hier zu finden: [https://gitlab.com/KarstenW76/kompendien-vorlage](https://gitlab.com/KarstenW76/kompendien-vorlage) (Manifest-URL: [https://gitlab.com/KarstenW76/kompendien-vorlage/-/raw/master/module.json](https://gitlab.com/KarstenW76/kompendien-vorlage/-/raw/master/module.json))

Das Modul "kompendien-vorlage-v10" ist eine universelle Vorlage für eigen-erstellte Kompendien in Foundry VTT Version 10.
Ziel ist, schnell und einfach eigene Kompendien zu erstellen und in verschiedenen Welten einzusetzen.

**Installation:** 
Das Modul ist veröffentlich. Die Installation der Vorlage kann schnell und einfach über die Modulsuche in Foundry erfolgen. 
Ebenso kann der folgende Manifest-Link in der Admin-Oberfläche von Foundry VTT über den Modul-Installer installieren einkopiert werden: [https://gitlab.com/KarstenW76/kompendien-vorlage-v10/-/raw/master/module.json](https://gitlab.com/KarstenW76/kompendien-vorlage-v10/-/raw/master/module.json)
Die dritte Variante ist der Direkt-Download, z.B. als zip: [https://gitlab.com/KarstenW76/kompendien-vorlage/-/archive/master/kompendien-vorlage-master.zip](https://gitlab.com/KarstenW76/kompendien-vorlage/-/archive/master/kompendien-vorlage-master.zip) 
In diesem Fall die zip-Datei so in den Ordner DATA\modules von Foundry VTT entpacken, dass sich hierin dann der Ordner "kompendien-vorlage-v10" befindet, mit der Datei "module.json" und dem Unterorder "packs" (dieser wiederum enthält die 11 *.db-Dateien).

**Anpassung für eigenen Nutzen:** 
Um das Modul für eigene Zwecke zu nutzen einfach den folgenden Schritten folgen:

1. Eine Kopie vom Ordner kompendien-vorlagen-v10 erstellen und einen für das Vorhaben passenden eigenen Namen geben (ohne Freizeichen, alles klein), z.B. deadlands-kompendien

2. Die Datei module.json im neuen Ordner mit einem Texteditor öffnen und folgende Änderungen vornehmen:

    a) **id** muss der neue eigene Ordnername sein, z.B. deadlands-kompendien

    b) **title** ist der Name Deines Moduls, unter der Dein Modul dann nachher in Foundry VTT zu finden ist (unter Modulen wie in den Welten, wo Du es aktivieren willst)

    c) Bei **description** kannst Du ein paar weitere Informationen angeben, die Du dann auch als Beschreibung zum Modul nachher siehst

    d) **authors** gerne ändern, das ist nur meine Vorlage, ich erhebe aber keine Benennungsansprüche, trag Dich hier bitte ein

    e) **compatibility** ist die Foundry Version, die mindestens vorhanden sein muss, um das Modul nutzen zu können, die positiv verifiziert wurde, und die maximal funktional ist. I.d.R. genügt es, wenn hier jeweils "10" enthalten ist (mit Version 9 oder früher ist dieses Modul nicht kompatibel, s.o.)
    
    f) in jedem der db-Kompendien-Dateien folgende Änderungen vornehmen:
    
       - **label** ist der Titel, den dieses Kompendium nachher in Deiner Welt unter Kompendien haben soll, also der Anzeigetitel

       - **name** ist der Name der .db-Datei, aber ohne .db

       - **system** muss bei jedem Actor und item jetzt gepflegt werden, hier trägst Du das System ein, für das diese sein sollen (die Voreintragung dnd5e auf das gewünschte System ändern)

       - **entity** ist der Typ des Kompendiums. Meine Vorlage sollte i.d.R. hier keine Änderung erfordern, da ich das schon zur universellen Nutzung durchdacht habe, ich liste aber unten die Typen und Inhalte der Vorlage noch einmal für Übersicht und Verständnis (bzw. falls du andere benötigst, z.B. ein drittes bis zehntes item-Kompendium um nicht mit Ordnern hierin arbeiten zu müssen)

       - **path** ist der relative Pfad zur passenden .db-Datei, dieser ist immer packs/dateiname.db

       - **module** ist immer der name des dieses Moduls, siehe 2.a
    Wenn Du keine zusätzlichen Kompendien benötigst, solltest Du das **label** aus der Vorgabe ändern (Stichwort auf System / Setting), Du musst aber auf jeden Fall **module** immer auf identisch zu **name** (s. 2a) ändern

    h) Die Einträge in den Klammern ganz unten zu url, manifest und download bitte in deinem Modul dann auch löschen, es soll ja nicht mehr zu meiner Vorlage verweisen und auch nicht bei Update meinerseits wieder überschrieben werden -> hierzu einfach die Einträge https... löschen so dass hinter dem Doppelpunkt nur  **""**, steht

3. Sollte Foundry gerade aktiv sein schließe es jetzt einmal komplett und starte es neu. Wenn Du keinen Fehler eingebaut hast, ist dein Kompendien-Modul jetzt zu finden und in Deinen Welten verwendbar, denk dran, es in Deiner/n Welt/en unter "Manage Modules" zu aktivieren.

**Welche Vorlagen sind denn jetzt hier eigentlich dabei?** 

- 2x Actor: Für den GM (für NPC, Kreaturen etc, zum unsichtbar schalten) sowie für Spieler (z.B. für Archetypen, fertige Charaktere etc)

- 1x Cards: Für eventuell selbst erstellte Spielkartendecks etc.

- 2x Item: Für den GM (für was die Spieler nicht sehen sollen, zum unsichtbar schalten) sowie für Spieler (z.B. Gegenstände, Waffen, Rüstungen, Zauber, Fähigkeiten etc)

- 2x Journal: Für den GM (für alles was die Spieler nicht sehen sollen wie Abenteuer, Handouts, zum unsichtbar schalten) sowie für Spieler (z.B. Regeln, Charakterinfos, Cheatsheets etc)

- 1x Macro: Erfordert i.d.R. keine Differenzierung zwischen GM + Spieler

- 1x Playlist: Für Spieler irrelevant, steuert eh der GM

- 1x Rolltable, da es i.d.R. eh Sinn macht oder gar erforderlich ist, diese zur Nutzung ins Spiel zu importieren, muss hier nicht zwischen GM + Spieler differenziert werden

- 1x Scene: Szenen sind nur für den GM relevant (bei Nutzung einer Landkarte oder Battlemap schaltest Du als GM einfach die Szene den Spielern frei, nicht aber das Kompendium, dies gehört unsichtbar)

**Wie heissen die möglichen Kompendium-Typen? **
Es gibt die folgenden 8 (genau so einzutragen bei entity, s. 2.f): **Actor, Cards, Item, JournalEntry, Macro, Playlist, RollTable, Scene**

**Was wenn ich weitere Kompendien benötige?** 
Das ist gar kein Problem: Wenn Du z.B. noch ein 3. Item-Kompendium brauchst, duplizierst Du eines der beiden Item-Kompendien (item-gm.db oder item-player.db) und gibst der Datei einen passenden neuen Namen (z.B. item-faehigkeiten). Beachte unbedingt, dass Du keine Umlaute, Sonderzeichen oder Großschreibung verwendest nur auch in Englisch existente Buchstaben und Bindestriche.
Dann gehst Du in die module.json und kopierst in dem Fall den ganzen folgenden Bereich und fügst ihn direkt danach wieder ein (quasi auch ein dupliziert). Dann nimmst Du die oben unter 2.g beschriebenen Anpassungen vor.
    {
      "label": "Items GM",
      "name": "item-gm",
      "entity": "Item",
      "path": "packs/item-gm.db",
      "module": "kompendien-vorlage"
    },
    
**Ein paar Tipps** 
Auf jeden Fall: 

1. Der Fehler, der hierbei am schnellsten passiert ist, das löschen eines Anführungszeichens oder Kommas, also genau arbeiten, dann läuft nachher auch alles (die Suche dauert länger). Und insbesondere auf das Komma hinter dem Schluss der geschweiften Klammern der packs achten, alle müssen eins haben, nur das letzte ganz unten nicht.

2. Wenn Du in einer Welt mit Deinem eingeladenen Kompendium auf "Unlock" klickst um es bearbeiten / befüllen zu können, wird Dir eine Warnung angezeigt, die darauf zielt, aufzupassen, dass eine Änderung von Dir bei einem Update überschrieben wird. Da dies Dein Modul ist und kein DEV sein Update pusht (als wenn Du an einem System rumbastelst), passiert hier auch nichts.

3. Ordner in Kompendien: Leider taucht der Button "Ordner erstellen" in einem Kompendium erst auf, wenn mindestens ein Ordner enthalten ist. Daher empfiehlt es sich, bspw. alle Archetypen oder fertigen Charaktere erst zu erstellen in der Welt (in den normalen Menüs), und dann mit der gewünschten Ordnerstruktur in Dein Kompendium zum exportieren (das steht Dir zur Wahl wenn es nicht schreibgeschützt ist).

4. Perfekte Verlinkungen: Um nachher tote Links zu umgehen, ist diese Kompendium-Lösung über ein Modul perfekt. Um bspw. eine Übersicht der Zauber mit Verlinkungen zu erstellen, empfehle ich folgendes Vorgehen:

    1. Alle Zauber als Items in der Welt erstellen

    2. Alle Zauber in ein Item-Kompendium (entweder ein eigenes oder ein Ordner im item-player Kompendium) exportieren, das wiederum in deinem Modul liegt

    3. Journal erstellen und dann aus Deinem Modul-Kompendium die Zauber auf das Sheet ziehen (nicht aus der Welt selbst!). Davor oder danach kannst Du auch Deine Notiz in das JournalEntry-Kompendium exportieren (wichtig ist immer, das die Eintäge, die Du verlinken willst, bereits in Deinem Modul-Kompendium liegen, wenn Du sie zur Verknüpfung irgendwo hinziehst, da sich beim Verschieben danach die Links ändern würde; ein Link zu einem Item, das in Welt A liegt, lässt sich in Welt B nicht mehr aufrufen)

So, genug geschrieben ... ich hoffe, das Modul und diese Anleitung hilft Dir, viel Spaß beim Bauen von weltenumspannenden Kompendien in Foundry V10!
