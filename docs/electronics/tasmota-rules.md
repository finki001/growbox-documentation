# Tasmota Pump Rules

See [Tasmota rules documentation](https://tasmota.github.io/docs/Rules/) for more info (rules can also be set via `MQTT`).

## Rule for Aeroponic Cloner Pump (conntcted to `POWER1`)
Create Rule 1:

`Rule1 ON Power1#Boot DO backlog Power1 ON; RuleTimer1 60 ENDON ON Rules#Timer=1 DO backlog Power1 OFF; RuleTimer2 240 ENDON ON Rules#Timer=2 DO backlog Power1 ON; RuleTimer1 60 ENDON`

Enable Rule 1:

`Rule1 1`

## Rule for Aeroponic Main Setup Pump (conncted to `POWER2`)
Create Rule 2:
`Rule2 ON Power2#Boot DO backlog Power2 ON; RuleTimer3 60 ENDON ON Rules#Timer=3 DO backlog Power2 OFF; RuleTimer4 240 ENDON ON Rules#Timer=4 DO backlog Power2 ON; RuleTimer3 60 ENDON`

Enable Rule 2:
`Rule2 1`