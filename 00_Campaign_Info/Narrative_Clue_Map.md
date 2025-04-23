---
tags: clue-flow, visualization, campaign-overview, narrative-map
aliases: [Narrative Hinweis-Karte]
---

# Ghroths Asche - Narrative Hinweis-Karte (Übersicht)

Dieses Diagramm zeigt die Verbindungen zwischen den zentralen Mysterien, Fraktionen und Konzepten der Kampagne. Pfeile deuten auf Beziehungen oder Entdeckungspfade hin. Hinweise in Klammern geben an, in welchen Abenteuern (Axx) oder Phasen (P2, P3) diese Verbindungen typischerweise aufgedeckt werden könnten.

```mermaid
graph TD
    subgraph Kern-Mysterium
        Ghroth["[[Ghroth]] (Die Quelle)"];
        DieAsche["[[Die Asche]] (Manifestation/Einfluss)"];
        Ghroth --"Verursacht"--> DieAsche;
    end

    subgraph Bedrohungen & Effekte
        DieAsche --"Verstärkt Emotionen"--> Gewalt["Gewalt/Wahnsinn (A01)"];
        DieAsche --"Kontaminiert Orte"--> Kontamination["Psychische Kontamination (A02)"];
        DieAsche --"Ermöglicht"--> Transformation["[[Die Transformierten]] (A03)"];
        DieAsche --"Verursacht"--> Verfall["Verfall/Withering (A06)"];
        DieAsche --"Verzerrt Realität"--> Raumverzerrung["Raum-/Zeitverzerrung (A05)"];
        Ghroth --"Erweckt/Lockt an"--> Schrecken["[[Erwachte Schrecken]] (A07+)"];
    end

    subgraph Fraktionen
        AscheChor["[[Der Asche-Chor]] (Kult)"];
        Widerstand["[[Der sterbende Widerstandskult]]"];
        Thorne["[[Dr. Aris Thorne]] (Wissenschaftler)"];

        DieAsche --"Verehrt von"--> AscheChor;
        Transformation --"Genutzt/Beschützt von"--> AscheChor;
        AscheChor --"Bekämpft"--> Widerstand;
        AscheChor --"Bekämpft"--> Spieler((Spieler));
        Spieler --"Suchen/Bekämpfen"--> AscheChor;
        Spieler --"Suchen Hilfe/Wissen"--> Widerstand;
        Spieler --"Suchen Hilfe/Wissen"--> Thorne;
        Widerstand --"Besitzt Wissen über"--> Ritual["[[Das Abschirmungsritual]]"];
        Thorne --"Erforscht/Theorien zu"--> DieAsche;
        Thorne --"Erforscht/Theorien zu"--> Ghroth;
        Thorne --"Erforscht/Theorien zu"--> Fokuspunkt["[[Der Fokuspunkt]]"];
    end

    subgraph Die Lösung
        Ritual --"Benötigt"--> Komponente["[[Die Komponente]]"];
        Ritual --"Benötigt"--> Fokuspunkt;
        Ritual --"Benötigt"--> WissenRitual["Ritual-Wissen"];
        Ritual --"Benötigt"--> Ausführende((Spieler));

        %% Fundorte für Lösungselemente
        Widerstand --"Liefert Wissen (A06, A07, A11)"--> WissenRitual;
        subgraph Fundorte_Komponente["Suche nach Komponente (A09)"]
             Ort_Komponente["[[Ort der Komponente]]"];
             ShellEntitaet["[[Die Shell Entität]] (Wächter)"];
             Ort_Komponente --"Beherbergt"--> Komponente;
             Ort_Komponente --"Bewacht von"--> ShellEntitaet;
             Spieler --"Suchen in A09"--> Ort_Komponente;
             Spieler --"Konfrontieren in A09"--> ShellEntitaet;
        end
        Komponente --"Preis/Opfer (A09)"--> Spieler;

        %% Fundorte für Fokuspunkt-Wissen
        subgraph Fundorte_Fokuspunkt["Identifikation Fokuspunkt (A04, A05, A06 -> CP)"]
             SignalDaten["Signal-Daten (A04)"];
             NexusDaten["Nexus-Daten (A05)"];
             VerfallQuelle["Quelle d. Verfalls (A06)"];
             SignalDaten --> Fokuspunkt;
             NexusDaten --> Fokuspunkt;
             VerfallQuelle --> Fokuspunkt;
             Thorne --"Hilft bei Synthese (CP nach A07)"--> Fokuspunkt;
             Widerstand --"Kann Wissen haben (A07+)"--> Fokuspunkt;
        end
        Spieler --"Reisen zu (A10)"--> Fokuspunkt;
        Spieler --"Bereiten vor (A11)"--> Fokuspunkt;
        Spieler --"Führen Ritual durch (A12)"--> Ritual;
    end

    %% Verbindungen zwischen Konzepten
    Fokuspunkt --"Ort für"--> Ritual;
    Komponente --"Benötigt für"--> Ritual;
    WissenRitual --"Benötigt für"--> Ritual;

    %% Styling
    classDef concept fill:#eee,stroke:#333;
    classDef faction fill:#ccf,stroke:#333;
    classDef solution fill:#cfc,stroke:#333;
    classDef player fill:#f9d,stroke:#333;
    classDef location fill:#fec,stroke:#333;

    class Ghroth,DieAsche,Gewalt,Kontamination,Transformation,Verfall,Raumverzerrung,Schrecken concept;
    class AscheChor,Widerstand,Thorne faction;
    class Ritual,Komponente,Fokuspunkt,WissenRitual,Ort_Komponente,ShellEntitaet solution;
    class Spieler player;
    class SignalDaten,NexusDaten,VerfallQuelle location;

```

**Hinweis:** Dieses Diagramm stellt die *konzeptionellen Verbindungen* dar. Ein Pfeil von "DieAsche" zu "Gewalt" bedeutet, dass die Asche Gewalt verursacht, was in A01 entdeckt wird. Ein Pfeil von "Spieler" zu "Widerstand" bedeutet, dass die Spieler den Widerstand suchen, was primär über Hinweise aus A06 oder nach A07 geschieht. Es ist eine Karte des *Wissens*, nicht des *Spielablaufs*.
