# Tasmota Pump Rules

See [Tasmota rules documentation](https://tasmota.github.io/docs/Rules/) for more info (rules can also be set via MQTT).

## Rule for Aeroponic Cloner Pump
* `Rule1 ON Power1#Boot DO backlog Power1 ON; RuleTimer1 60 ENDON ON Rules#Timer=1 DO backlog Power1 OFF; RuleTimer2 240 ENDON ON Rules#Timer=2 DO backlog Power1 ON; RuleTimer1 60 ENDON
Rule1 1
`

## Rule for Aeroponic Main Setup Pump
* `Rule1 ON Power1#Boot DO backlog Power1 ON; RuleTimer1 60 ENDON ON Rules#Timer=1 DO backlog Power1 OFF; RuleTimer2 240 ENDON ON Rules#Timer=2 DO backlog Power1 ON; RuleTimer1 60 ENDON
Rule1 1
`