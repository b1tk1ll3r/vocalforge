# Datenschutzerklärung für den Discord-Bot „VocalForge“

*Stand: 10. August 2025*

## 1. Verantwortlicher
**Betreiber:** Jan Bergner  
**Kontakt:** b1tsblog@send.nrw 

> Hinweis: Wenn dieser Bot von einer Guild/Community selbst gehostet wird, ist die jeweilige betreibende Person/Organisation Verantwortliche im Sinne der DSGVO.

## 2. Zweck und Funktionsweise
Der Bot ermöglicht das Erstellen privater Sprachkanäle („Voice Channels“) inkl. Auto-Cleanup sowie Admin-Konfiguration (Lobby-Name, Kategorie, Timeout) und eines `/adduser`-Befehls, um gezielt Mitgliedern Zugriff zu gewähren.  
Die Verarbeitung erfolgt ausschließlich zur Bereitstellung dieser Funktionen, zum sicheren Betrieb und zur Fehlerdiagnose.

## 3. Verarbeitete Daten (Kategorien)
**Laufzeit-/Nutzungsdaten (flüchtig in RAM, via Discord-API):**
- Discord User-ID, Benutzername, Global Name, Server-Nickname (nur zur Anzeige des Kanalnamens/Antworten).
- Guild-ID/-Name, Channel-IDs/-Namen, Voice-States (insb. aktueller Voice-Channel, Join/Leave).
- Rollen/Permissions (zur Prüfung „Admin“/„Manage Server/Channels“).
- Slash-Command-Eingaben (`/makevc` Name, `user_limit`, `timeout_min`; `/setlobby`, `/setcategory`, `/settimeout`; `/adduser user`).

**Vom Bot gesetzte Berechtigungen (bei Discord gespeichert):**
- Channel-Permission-Overwrites für Besitzer: Sichtbarkeit, Verbinden, Sprechen, Streamen, Manage Channels.
- Overwrites für hinzugefügte Nutzer bei `/adduser`.

**Persistente Daten (Datei `guild_config.json`):**
- Pro Guild: `lobby_name`, `category_name`, `timeout_min`.

**Protokolle/Logs (betriebsbedingt):**
- Technische Ereignisse/Fehler inkl. Zeitstempel, Guild-IDs/-Namen, Channel-IDs, ggf. Fehlermeldungen der Discord-API.
- Beispiele aus dem Code: „Bot online“, „Registriere Commands in Guild …“, „Added/Deleted channel for guildID …“.

> Der Bot speichert **keine** Benutzerinhalte (z. B. Sprachdaten) und **keine** personenbezogenen Nutzerdaten dauerhaft, außer den oben genannten Konfigurationswerten pro Guild. Voice-Aktivität wird lediglich als Zustand (belegt/leer) im Speicher ausgewertet, um Auto-Cleanup auszulösen.

## 4. Rechtsgrundlagen (DSGVO)
- **Art. 6 Abs. 1 lit. b DSGVO** (Vertrag/vertragsähnliches Nutzungsverhältnis): Bereitstellung der vom Nutzer angeforderten Funktionen (Slash-Commands, private Voice-Kanäle, Zugriffsverwaltung).
- **Art. 6 Abs. 1 lit. f DSGVO** (berechtigte Interessen): Stabiler, sicherer Betrieb, Missbrauchs-/Fehleranalyse, Minimierung ungenutzter Channels (Auto-Cleanup). Unser Interesse überwiegt, da die Eingriffe gering sind, Transparenz besteht und nur notwendige Daten verarbeitet werden.

## 5. Empfänger und Drittlandtransfer
- **Discord, Inc.** (Plattformanbieter/selbstständiger Verantwortlicher): Der Bot interagiert ausschließlich über die Discord-API; Discord verarbeitet Nutzungsdaten gemäß eigener Datenschutzerklärung und kann Daten außerhalb der EU verarbeiten.
- **Hosting-Provider**: Server4You, Straßburg (Frankreich / France) für Serverbetrieb/Logs.
- **Guild-Administratoren** erhalten Ergebnisse/Statusmeldungen (z. B. Ephemeral Responses) im Rahmen der Bot-Funktion.

## 6. Speicherdauer
- **`guild_config.json`:** Bis zur Löschung durch Admins, Entfernen des Bots von der Guild oder Deinstallation.
- **Logs:** Nur im Arbeitsspeicher; keine dauerhafte Speicherung.
- **Flüchtige Voice-State-Daten:** Nur im Arbeitsspeicher; keine dauerhafte Speicherung.
- **Berechtigungs-Overwrites:** In Discord bis zur manuellen Änderung/Löschung des Channels.

## 7. Erforderlichkeit/Minimierung
Der Bot verarbeitet nur die für die Funktion notwendigen Daten:
- Anzeigename für Kanalbenennung/Antworten.
- Voice-State zur Erkennung von Lobby-Join und Inaktivität (Auto-Cleanup).
- Rollen/Permissions ausschließlich für Admin-Prüfungen und Channel-Verwaltung.

Es findet **kein** Profiling zu Werbe-/Marketingzwecken statt. **Keine** automatisierten Entscheidungen mit Rechtswirkung.

## 8. Sicherheit
- Zugriff auf den Bot-Token via Umgebungsvariable `DISCORD_TOKEN`.
- Prinzip der minimalen erforderlichen Rechte (Manage Channels/Move Members nur, soweit technisch nötig).
- Schutz der Persistenzdatei `guild_config.json` und Logs durch Server-Zugriffskontrollen.  

## 9. Pflichtangaben bei Befehlen
Die Nutzung bestimmter Befehle erfordert Eingaben (z. B. Channel-Name, Timeout, Ziel-User). Diese Angaben sind für die Erfüllung der gewünschten Funktion erforderlich.

## 10. Rechte der betroffenen Personen
Sie haben – sofern anwendbar – folgende Rechte:
- Auskunft (Art. 15), Berichtigung (Art. 16), Löschung (Art. 17), Einschränkung (Art. 18), Datenübertragbarkeit (Art. 20) sowie Widerspruch (Art. 21) gegen Verarbeitungen auf Grundlage berechtigter Interessen.  
Anfragen bitte an: b1tsblog@send.nrw.  
Hinweis: Daten, die bei Discord liegen (z. B. Nachrichten/Overwrites), sind vorrangig bei Discord bzw. den jeweiligen Guild-Admins geltend zu machen.

## 11. Beschwerderecht
Sie können sich bei einer Datenschutzaufsichtsbehörde beschweren, z. B. in Ihrem EU-Mitgliedstaat oder am Sitz des Verantwortlichen.

## 12. Kinder/Jugendliche
Der Bot richtet sich nicht gezielt an Kinder. Die Nutzung folgt den Discord-Nutzungsbedingungen/Altersgrenzen.

## 13. Internationale Datenübermittlungen
Soweit Daten durch Discord außerhalb des EWR verarbeitet werden, stützt sich Discord auf geeignete Garantien (nach deren eigener Privacy Policy). Der Bot-Betreiber selbst übermittelt außer den API-Aufrufen an Discord keine personenbezogenen Daten in Drittländer, es sei denn, das Hosting befindet sich dort ([Hosting-Standort einsetzen]).

## 14. Änderungen dieser Datenschutzerklärung
Wir können diese Erklärung anpassen, wenn der Funktionsumfang oder die Rechtslage sich ändert. Es gilt die jeweils aktuelle Fassung mit Datum oben.

---

### Transparenzhinweise speziell zu Code-Details
- **Persistenz:** Nur `GuildConfig` (Lobby/Kategorie/Timeout) wird in `guild_config.json` gespeichert.  
- **Auto-Cleanup:** Überwachung, ob der Channel belegt ist (Poll alle 15 Sekunden); Löschung nach konfiguriertem Timeout ohne Nutzertracking darüber hinaus.  
- **Logs:** Enthalten v. a. Guild-/Channel-IDs und technische Meldungen; keine Inhaltsdaten.  
- **Berechtigungen:** Owner erhält `Manage Channels`; `/adduser` setzt Sicht-/Beitritts-/Sprechrechte für einen Ziel-User am aktuellen privaten VC.  
- **Keine Audioverarbeitung:** Es werden **keine** Sprachdaten aufgezeichnet, transkribiert oder gespeichert.  
