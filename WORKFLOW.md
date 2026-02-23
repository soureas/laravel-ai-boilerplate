# 🔄 End-to-End AI Development Workflow

Dieser Prozess definiert den exakten Lebenszyklus deiner Softwareentwicklung – vom leeren Projekt bis zum archivierten Feature.

## 📋 Übersicht der Agenten-Rollen

| Befehl / Modus    | Rolle                 | Einsatzzweck                                     | Output-Ziel                       |
| ----------------- | --------------------- | ------------------------------------------------ | --------------------------------- |
| **`/interview`**  | Requirements Engineer | Neues Feature planen & abgrenzen.                | `REQUIREMENTS.md`                 |
| **`/promote`**    | Requirements Engineer | Backlog-Idee in aktiven Use Case wandeln.        | `REQUIREMENTS.md`                 |
| **Standard Chat** | Full Stack Architect  | Aktiven Use Case in Code umwandeln.              | Echter Code & `MEMORY.md` Trigger |
| **`/debug`**      | Debugging Expert      | Stack Traces logisch analysieren.                | Chat (Analyse & Fix-Befehl)       |
| **`/fix`**        | Full Stack Architect  | Isolierte Bugs beheben (ohne Architektur-Bruch). | Echter Code (Snippet)             |
| **`/archive`**    | Software Architect    | Abgeschlossene UCs destillieren.                 | `MEMORY.md` & `ARCHIVE.md`        |

---

## 🚀 Phase 1: Projektvorbereitung (Setup)

Bevor die KI zum Einsatz kommt, wird das Fundament gelegt.

1. **Boilerplate clonen:**
   Ziehe dir dein sauberes Laravel-Tailwind-Setup.

```bash
git clone <DEINE_GITHUB_REPO_URL> mein-projekt
cd mein-projekt

```

2. **Historie bereinigen & Setup:**
   Lösche die alte Git-Historie und installiere die Abhängigkeiten.

```bash
rm -rf .git && git init
composer install && npm install
cp .env.example .env && php artisan key:generate

```

3. **Vision definieren:**
   Öffne die leere `REQUIREMENTS.md` und trage oben unter **# 🌍 PROJEKT-VISION** manuell in 2-3 Sätzen ein, was das System ist und wer die Zielgruppe ist.

---

## 📝 Phase 2: Anforderungsanalyse (Planning)

Hier wird definiert, _was_ gebaut wird. Es wird strikt kein Code geschrieben.

1. **Neuen Chat öffnen.**
2. **Befehl ausführen:**
   `/interview Lass uns das Kern-Feature X planen.`
3. **Dialog führen:**
   Die KI stellt maximal 3 Fragen zu Edge Cases, Security und Scope. Beantworte diese.
4. **Dokumentation:**
   Kopiere den generierten Markdown-Block (z. B. `[UC-01]`) in deine `REQUIREMENTS.md`.

---

## 🛠️ Phase 3: Entwicklung (Execution)

Hier wird der Use Case in echten Laravel- und Tailwind-Code umgewandelt.

1. **Neuen Chat öffnen (Zwingend!).** Dadurch wird der Planungs-Kontext zurückgesetzt und die harten Execution-Regeln (`techstack-laravel.md`) greifen.
2. **Ausführungs-Prompt senden:**

```text
Setze jetzt [UC-01] aus der REQUIREMENTS.md vollständig um.

Gehe in dieser exakten Reihenfolge vor:
1. Datenbank (Artisan-Befehle, Migration & Model)
2. Backend (Controller, Form Requests, Policies)
3. Frontend (Blade-Views mit Tailwind CSS)

Liefere mir den Code schrittweise und frage mich nach jedem Schritt, ob alles funktioniert hat, bevor du den nächsten generierst.
Erinnere dich zwingend an deine Workspace-Rules bezüglich des Post-Execution Checks am Ende der Aufgabe.

```

3. **Code implementieren:** Kopiere den Code schrittweise in deine IDE.
4. **Memory Update (Der Trigger):** Am Ende der Umsetzung schlägt der Architektur-Alarm der KI an. Bestätige das Update und kopiere den neuen Architektur-Stand in die `MEMORY.md`.

---

## 🐛 Phase 4: Wartung & Fehlerbehebung (Debugging)

Wenn während oder nach der Entwicklung Fehler auftreten.

- **Bei großen Fehlern (z. B. Laravel 500 Error, dicke Stack Traces):**
  Nutze `/debug [Füge den Error-Log hier ein]`. Die KI analysiert den Fehler gegen die `MEMORY.md` und liefert die exakte Ursache.
- **Bei kleinen Fehlern (z. B. falsche Tailwind-Farbe, Tippfehler):**
  Nutze `/fix [Beschreibe das genaue Problem]`. Die KI liefert nur das minimal invasive Code-Snippet.

---

## 🗄️ Phase 5: Abschluss (Archivierung)

Wenn ein Feature komplett fertig und fehlerfrei ist, wird der Workspace aufgeräumt, damit der KI-Kontext für den nächsten Sprint schnell und präzise bleibt.

1. **Neuen Chat öffnen.**
2. **Befehl ausführen:**
   `/archive Analysiere [UC-01]`
3. **Systemregeln mergen:**
   Kopiere den generierten Block "Globale Business-Regeln & Policies" und überschreibe damit den alten Block in deiner `MEMORY.md`.
4. **Use Case verschieben:**
   Schneide den kompletten `[UC-01]` Block aus der `REQUIREMENTS.md` aus und füge ihn in die `ARCHIVE.md` ein.

---

Möchtest du diese Übersicht als `WORKFLOW.md` in dein lokales Projekt speichern, oder sollen wir direkt mit Phase 1 für dein neues Test-Projekt beginnen?
