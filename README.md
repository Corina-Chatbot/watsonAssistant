# watsonAssistant
Hier liegen die Exporte aus dem Watson Assistant.
Der wichtigste Skill ist "chatbot - live". Hier sind alle Intents, Entities und Dialoge gepflegt, mit denen der Bot umgehen kann.

# Intents

Ein Intents repräsentiert die Absicht die ein Nutzer mit seiner Frage hat. Hierfür werden eine Reihe von Beispiel Fragen in Watson eingepfelgt und einer übergeordneten Kategorie zugeordnet. Je feingranularer die Kategoiren (Intents) sind, desto spezifischer kann der Chatbot auf einezelen Fragen reagieren. 

Folgende Intents sind aktuell in Corina implementiert: 
- chatbotkommunikation_kommunikation_bot_begruessung
- chatbotkommunikation_kommunikation_bot_danke
- chatbotkommunikation_kommunikation_bot_funktionalitaet
- chatbotkommunikation_kommunikation_bot_ort
- chatbotkommunikation_kommunikation_bot_persoenlich_allgemein
- chatbotkommunikation_kommunikation_bot_persoenlich_alter
- chatbotkommunikation_kommunikation_bot_persoenlich_bot
- chatbotkommunikation_kommunikation_bot_persoenlich_essen
- chatbotkommunikation_kommunikation_bot_persoenlich_farbe
- chatbotkommunikation_kommunikation_bot_persoenlich_geburtstag
- chatbotkommunikation_kommunikation_bot_persoenlich_geschlecht
- chatbotkommunikation_kommunikation_bot_persoenlich_hass
- chatbotkommunikation_kommunikation_bot_persoenlich_herkunft
- chatbotkommunikation_kommunikation_bot_persoenlich_liebe
- chatbotkommunikation_kommunikation_bot_persoenlich_name
- chatbotkommunikation_kommunikation_bot_persoenlich_test
- chatbotkommunikation_kommunikation_bot_quellen
- chatbotkommunikation_kommunikation_bot_rueckmeldung_negativ
- chatbotkommunikation_kommunikation_bot_rueckmeldung_positiv
- chatbotkommunikation_kommunikation_bot_sonstiges
- chatbotkommunikation_kommunikation_bot_verabschiedung
- diagnostik_corona_bestaetigt_erkrankt
- diagnostik_risiko_kontakt_positiv
- diagnostik_risiko_reise_ausland
- diagnostik_risiko_vorerkrankung_positiv
- diagnostik_symptome_beschreibung_corona
- diagnostik_symptome_beschreibung_notfall
- informationen_arbeit_krankschreibung_allgemein
- informationen_infrastruktur_einkauf_allgemein
- informationen_infrastruktur_einkauf_allgemein_toilettenpapier
- informationen_infrastruktur_nahverkehr_allgemein
- informationen_infrastruktur_quarantaene_allgemein
- informationen_infrastruktur_quarantaene_bedeutung
- informationen_infrastruktur_quarantaene_einsamkeit
- informationen_infrastruktur_quarantaene_lohnfortzahlung
- informationen_infrastruktur_quarantaene_versorgung
- informationen_politisch_ausgangssperre_allgemein
- informationen_politisch_massnahmen_allgemein
- informationen_politisch_massnahmen_prognose
- informationen_politisch_oeffentlichkeitsarbeit_allgemein
- informationen_politisch_oeffentlichkeitsarbeit_planung
- informationen_politisch_sondergruppen_haeftlinge
- informationen_rechtlich_meldepflicht_allgemein
- informationen_rechtlich_unternehmensschliessung_allgemein
- informationen_statistik_info_risikogebiet
- informationen_statistik_info_update
- informationen_virus_infektion_gesichert
- informationen_virus_infektion_verdacht
- informationen_virus_info_allgemein
- informationen_virus_info_ansteckung
- informationen_virus_info_immunitaet
- informationen_virus_info_katrastrophe
- informationen_virus_info_kleinkinder
- informationen_virus_info_langzeitschaeden
- informationen_virus_info_symptome
- informationen_virus_info_tier
- informationen_virus_info_verlauf
- informationen_virus_praevention_allgemein
- informationen_virus_praevention_haendewaschen
- informationen_virus_praevention_haendewaschen_desinfektion
- informationen_virus_praevention_impfung
- informationen_virus_praevention_infektionsschutz
- informationen_virus_praevention_medikament
- informationen_virus_test_ablauf
- informationen_virus_test_kosten
- informationen_virus_test_verfuegbarkeit
- informationen_virus_therapie_behandlung
- informationen_virus_therapie_praxisbesuch
- kontakt_allgemein_bestaetigt_erkrankt
- MenschenSprechen
- nlu
- Risikoeinschätzung

# Entities

Entitäten stellen Informationen in der Benutzereingabe dar, die für die Intention des Benutzers von Bedeutung sind. Zum Beispiel handelt es sich bei einem Symptom um eine Entität die verschiedene Werte haben kann. 
Ebtitäten können genutzt werden um spezifischer auf bestimmte Fragen einzugehen.

Folgene Entitäten sind aktuell definiert: 
- Abfrage
- Beruf
- BOT
- Bundesland
- Kontakt
- Krankschreibung
- Land
- Medikation
- Oeffentlichkeitsarbeit
- Reise
- Schwangerschaft
- Stadt
- Statistik
- Symptom
- Test
- Virus
- Vorerkrankungen
- Wohnsituation

# Dialoge

# Services
## Natural language understanding
Der NLU Service analysiert einen gegebenen Text und liefert kontextabhängige Informationen zurück. Das können z.B. Keywords oder Entities sein. Mit einer Cloud Function als Vermittler haben wir diesen Service auch über den Webhook des Watson Assistant im Skill verfügbar gemacht.
### Webhook
Um die NLU innerhalb eines Dialogs zu benutzen, muss man folgende Parameter setzen.
- type
  Der Typ von Entity, für den man sich interessiert. Z.B. "Location". Siehe [hier](https://cloud.ibm.com/docs/services/natural-language-understanding?topic=natural-language-understanding-entity-types-version-2)
- action
  Die Action, welche von der Cloud Function ausgeführt werden soll. In diesem Fall "NLU"
- text
  Der Text, welcher analysiert werden soll.
