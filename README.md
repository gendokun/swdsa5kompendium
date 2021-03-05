Das Modul "_kompendien" ist eine universelle Vorlage für eigen erstellte Kompendien in Foundry VTT.
Ziel ist, schnell und einfach eigene Kompendien zu erstellen und in verschiedenen Welten einzusetzen.

**Installation:** 
Die Installation der Vorlage kann über das Manifest erfolgen (hierfür den Manifest-Link in der Admin-Oberfläche von Foundry VTT über den Modul-Installer installieren, ganz unten kann die Manifest-URL einkopiert werden: https://gitlab.com/KarstenW76/kompendien-vorlage/-/raw/master/module.json). 
Ebenso ist aber der Direkt-Download (z.B. als zip: https://gitlab.com/KarstenW76/kompendien-vorlage/-/archive/master/kompendien-vorlage-master.zip) möglich. In diesem Fall die zip-Datei so in den Ordner DATA\modules von Foundry VTT entpacken, dass sich hierin dann der Ordner "kompendien-vorlage" befindet, mit der Datei "module.json" und dem Unterorder "packs" (dieser wiederum enthält die 10 *.db-Dateien).

**Anpassung für eigenen Nutzen:** 
Um das Modul für eigene Zwecke zu nutzen einfach den folgenden Schritten folgen:

1. Eine Kopie vom Ordner kompendien-vorlagen erstellen und einen für das Vorhaben passenden eigenen Namen geben (ohne Freizeichen, alles klein), z.B. deadlands-kompendien

2. Die Datei module.json im neuen Ordner mit einem Texteditor öffnen und folgende Änderungen vornehmen:
    a) **name** muss der neue Ordnername sein, z.B. deadlands-kompendien
    b) **title** ist die Kurzbeschreibung, unter der Dein Modul dann nachher zu finden ist (unter Modulen wie in den Welten, wo Du es aktivieren willst)
    c) Bei **description** kannst Du ein paar weitere Informationen angeben, die Du dann auch als Beschreibung zum Modul nachher siehst
    d) **author** gerne ändern, das ist nur meine Vorlage, ich erhebe aber keine Benennungsansprüche, also trag bitte Dich hier ein
    e) **minimumCoreVersion** ist die Foundry Version, die mindestens vorhanden sein muss, um das Modul nutzen zu können
    f) **compatibleCoreVersion** ist die aktuelle Foundry Version, die Du nutzt (jetzt 0.79, wenn Du das später so belässt, bekommst Du immer den Hinweis, das das Modul möglicherweise nicht mehr kompatibel ist ... wenn das stört und das Modul funktioniert gut, einfach updaten)
    g) in jedem der db-Kompendien-Dateien folgende Änderungen vornehmen:
        - **label** ist der Titel, den dieses Kompendium nachher in Deiner Welt unter Kompendien haben soll, also der Anzeigetitel
        - **name** ist der Name der .db-Datei, aber ohne .db
        - **entity** ist der Typ des Kompendiums. Meine Vorlage sollte i.d.R. hier keine Änderung erfordern, da ich das schon zur universellen Nutzung durchdacht habe, ich liste aber unten die Typen und Inhalte der Vorlage noch einmal für Übersicht und Verständnis (bzw. falls du andere benötigst, z.B. ein drittes item-Kompendium, weil du nicht mit Ordnern im Kompendium arbeiten willst)
        - **path** ist der relative Pfad zur passenden .db-Datei, dieser ist immer packs/dateiname.db
        - **module** ist immer der name des dieses Moduls, siehe 2.a
    D.h. wenn Du keine zusätzlichen Kompendien benötigst, solltest Du in den mitgegebenen das **label** ändern (Stichwort auf System / Setting), musst aber auf jeden Fall **module** immer auf identisch zu **name** (2a) ändern
    h) Die Einträge in den Klammern ganz unten zu url, manifest und download bitte in deinem Modul dann auch löschen, es soll ja nicht mehr zu meiner Vorlage verweisen (hierzu einfach die Einträge https... löschen so dass hinter dem Doppelpunkt nur  "", steht)

3. Sollte Foundry laufen jetzt einmal komplett schließen und neu starten. Wenn Du keinen Fehler eingebaut hast, ist dein Kompendien-Modul jetzt zu finden und verwendbar, denk dran, es in der/den Welt/en unter "Manage Modules" zu aktivieren.

**Welche Vorlagen sind denn jetzt hier eigentlich dabei?** 
- 2x Actor: Für den GM (für NPC, Kreaturen etc, zum unsichtbar schalten) sowie für Spieler (z.B. für Archetypen, fertige Charaktere etc)
- 2x Item: Für den GM (für was die Spieler nicht sehen sollen, zum unsichtbar schalten) sowie für Spieler (z.B. Gegenstände, Waffen, Rüstungen, Zauber, Fähigkeiten etc)
- 2x Journal: Für den GM (für alles was die Spieler nicht sehen sollen wie Abenteuer, Handouts, zum unsichtbar schalten) sowie für Spieler (z.B. Regeln, Charakterinfos, Cheatsheets etc)
- 1x Macro: Erfordert i.d.R. keine Differenzierung zwischen GM + Spieler
- 1x Playlist: Für Spieler irrelevant, steuert eh der GM
- 1x Rolltable, da es i.d.R. eh Sinn macht oder gar erforderlich ist, diese zur Nutzung ins Spiel zu importieren, muss hier nicht zwischen GM + Spieler differenziert werden
- 1x Scene: Szenen sind eh nur für den GM (bei Nutzung, z.B. Landkarte, schaltest Du als GM einfach die Szene den Spielern frei, nicht aber das Kompendium, also eh zum unsichtbar schalten)

**Wie heissen die möglichen Kompendium-Typen? **
Es gibt die folgenden 7 (genau so einzutragen bei entity, s. 2g): **Actor, Item, JournalEntry, Macro, Playlist, RollTable, Scene**

**Was wenn ich weitere Kompendien benötige?** 
Gar kein Problem, wenn Du z.B. noch ein 3. Item-Kompendium brauchst, duplizierst Du eines der beiden Item-Kompendien (item-gm.db oder item-player.db) und gibst der Datei einen passenden neuen Namen (z.B. item-faehigkeiten). Unbedingt beachten, das Du keine Umlaute, Sonderzeichen oder Großschreibung verwendest nur auch in englisch existente Buchstaben und Bindestriche. 
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
    1) Der Fehler, der hierbei am schnellsten passiert ist, das löschen eines Anführungszeichens oder Kommas, also genau arbeiten, dann läuft nachher auch alles (die Suche dauert länger ;)). Und insbesondere auf das Komma hinter dem Schluss der geschweiften Klammern der packs achten, alle müssen eins haben, nur das letzte ganz unten nicht.
    2) Wenn Du in einer Welt mit Deinem eingeladenen Kompendium auf "Unlock" klickst um es bearbeiten / befüllen zu können, bekommst Du eine Fehlermeldung. Also eigentlich ist es keine Fehlermeldung sondern eine Warnung, die darauf zielt, aufzupassen, dass eine Änderung von Dir bei einem Update überschrieben wird. Da dies Dein Modul ist und kein DEV sein Update pusht (als wenn Du an einem System rumbastelst), passiert hier auch nichts.
    3) Ordner in Kompendien: Leider taucht der Button "Ordner erstellen" in einem Kompendium erst auf, wenn mindestens ein Ordner enthalten ist. Daher empfiehlt es sich, bspw. alle Archetypen oder fertigen Charaktere erst zu erstellen in der Welt (in den normalen Menüs), und dann mit der gewünschten Ordnerstruktur in Dein Kompendium zum exportieren (das steht Dir zur Wahl wenn es nicht schreibgeschützt ist).
    4) Perfekte Verlinkungen: Um nachher tote Links zu umgehen, ist diese Kompendium-Lösung über ein Modul perfekt. Um bspw. eine Übersicht der Zauber mit Verlinkungen zu erstellen, empfehle ich folgendes Vorgehen:
        1. alle Zauber als Items in der Welt erstellen
        2. alle Zauber in ein Item-Kompendium (entweder ein eigenes oder ein Ordner im item-player Kompendium) exportieren, das wiederum in deinem Modul liegt
        3. Journal erstellen und dann aus Deinem Modul-Kompendium die Zauber auf das Sheet ziehen (nicht aus der Welt selbst!). Davor oder danach kannst Du auch Deine Notiz in das JournalEntry-Kompendium exportieren (wichtig ist immer, das die Eintäge, die Du verlinken willst, bereits in Deinem Modul-Kompendium liegen, wenn Du sie zur Verknüpfung irgendwo hinziehst, da sich beim Verschieben danach die Link ändern würde und ein Link zu einem Item, das in Welt A liegt, lässt sich aus Welt B nicht mehr aufrufen)

So, genug geschrieben ... ich hoffe, das Modul und diese Anleitung hilft Dir, viel Spaß beim Bauen von weltenumspannenden Kompendien!
