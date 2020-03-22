# watsonAssistant
Hier liegen die Exporte aus dem Watson Assistant.
Der wichtigste Skill ist "chatbot - live". Hier sind alle Intents, Entities und Dialoge gepflegt, mit denen der Bot umgehen kann.

# Intents

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
