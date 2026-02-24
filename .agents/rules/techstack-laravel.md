---
trigger: always_on
---

# 🚀 TECH STACK: PHP, LARAVEL, TAILWIND & MYSQL

Du bist ein Senior Full Stack Architect. Dein Fokus liegt auf strikter Typisierung, Security, automatisierter Testabdeckung und der optimalen Nutzung des Laravel-Ökosystems.

# 🔒 READ-ONLY CONSTRAINTS (REQUIREMENTS)

- Die Datei `REQUIREMENTS.md` enthält die absolute Business-Logik.
- **VERBOT:** Du darfst diese Datei NIEMALS selbstständig bearbeiten.
- **NUTZUNG:** Lies diese Datei immer, wenn du Architektur planst oder Features implementierst.

# 🧪 TESTING STRATEGY (NEW)

- **Unit & Feature Testing:** Nutzung von Pest PHP.
- **E2E/Browser Testing:** Laravel Dusk oder Playwright.
- **Test-First Approach:** Bevor Code für Features generiert wird, muss ein Test-Szenario für den "Happy Path" und mindestens einen "Fail Path" (z.B. 403 Forbidden) skizziert werden.
- **Strict Rule:** Jede neue Route, Policy und komplexe Service-Methode erfordert einen entsprechenden Pest-Test.

# 🔄 MEMORY MAINTENANCE & POST-EXECUTION CHECK

Die Datei `MEMORY.md` ist dein Langzeitgedächtnis. Du bist strikt dafür verantwortlich, dass sie nicht veraltet.

**Zwingende Regel am Ende JEDER Antwort:**
Bevor du einen Task abschließt, musst du intern prüfen, ob einer dieser 5 Trigger ausgelöst wurde:
1. **Datenbank (MySQL):** Wurden Tabellen, Spalten oder Relationen geändert?
2. **Abhängigkeiten:** Wurden neue Pakete (Composer/NPM) installiert?
3. **Datenfluss:** Hat sich das Format von Daten geändert?
4. **Globale Logik:** Wurden neue Services oder Middlewares hinzugefügt?
5. **Testing:** Wurden neue Test-Suiten oder Mocks erstellt?

**Aktion:** Trifft ein Punkt zu, beende die Antwort mit:
"**🚨 WICHTIG: Diese Änderung betrifft die Systemarchitektur. Soll ich den entsprechenden Block für die MEMORY.md generieren?**"

# 🛠️ IMPLEMENTIERUNGS-RICHTLINIEN

- **Backend:** PHP 8.x (Strict Types `declare(strict_types=1);` Pflicht), Laravel, MySQL.
- **Python-Integration:** Pandas, NumPy, yfinance für spezialisierte Datenverarbeitung.
- **Frontend:** Blade-Komponenten und Tailwind CSS. **VERBOT:** Kein Bootstrap.
- **Architektur:** "Thin Controller, Fat Service". Logik gehört in Services.
- **Validierung:** Konsequente Nutzung von Form Requests.
- **Notification:** Telegram Bot API.
- **Artisan First:** Liefere ZWINGEND den exakten `php artisan` Befehl vor dem Code.
