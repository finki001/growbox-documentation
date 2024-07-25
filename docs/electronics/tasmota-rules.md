# Tasmota Rules

See [Tasmota rules documentation](https://tasmota.github.io/docs/Rules/) for more info (rules can also be set via
`MQTT`).

[//]: # (TODO: rewrite this)

[//]: # (## Rule1 for Aeroponic Cloner Pump &#40;conntcted to `POWER1`&#41;)

[//]: # (uses Timer1 and Timer2 - 1min on - 4min off:)

[//]: # ()

[//]: # (`Rule1 ON Power1#Boot DO backlog Power1 ON; RuleTimer1 60 ENDON ON Rules#Timer=1 DO backlog Power1 OFF; RuleTimer2 240 ENDON ON Rules#Timer=2 DO backlog Power1 ON; RuleTimer1 60 ENDON`)

[//]: # ()

[//]: # (## Rule2 for Aeroponic Main Setup Pump &#40;connected to `POWER10`&#41;)

[//]: # (uses Timer3 and Timer4 - 1min on - 4min off:)

[//]: # ()

[//]: # (`Rule2 ON Power10#Boot DO backlog Power10 ON; RuleTimer3 60 ENDON ON Rules#Timer=3 DO backlog Power10 OFF; RuleTimer4 240 ENDON ON Rules#Timer=4 DO backlog Power10 ON; RuleTimer3 60 ENDON`)

## Current Lighting Ruleset (`Rule1`)

```
ON Time#Minute=600 DO POWER4 ON ENDON
ON Time#Minute=240 DO POWER4 OFF ENDON
ON Time#Minute=600 DO POWER9 ON ENDON
ON Time#Minute=240 DO POWER9 OFF ENDON
ON Time#Minute=585 DO POWER7 ON ENDON
ON Time#Minute=600 DO POWER7 OFF ENDON
ON Time#Minute=210 DO POWER7 ON ENDON
ON Time#Minute=220 DO POWER7 OFF ENDON
ON Time#Minute=230 DO POWER7 ON ENDON
ON Time#Minute=255 DO POWER7 OFF ENDON
ON Time#Minute=585 DO POWER8 ON ENDON
ON Time#Minute=600 DO POWER8 OFF ENDON
ON Time#Minute=210 DO POWER8 ON ENDON
ON Time#Minute=220 DO POWER8 OFF ENDON
ON Time#Minute=230 DO POWER8 ON ENDON
ON Time#Minute=255 DO POWER8 OFF ENDON
```
## Current Pump Ruleset (`Rule2`)
```
ON POWER10#Boot DO backlog POWER10 ON; RuleTimer1 60 ENDON ON Rules#Timer=1 DO backlog POWER10 OFF; RuleTimer2 240 ENDON ON Rules#Timer=2 DO backlog POWER10 ON; RuleTimer1 60 ENDON
```
| Relay  | Purpose            | Turned on at minute / time            | Turned off at minute / time            |
|--------|--------------------|---------------------------------------|----------------------------------------|
| POWER2 | Mother Plant Light | 600 / 10:00                           | 240 / 04:00                            |
| POWER4 | Main Light         | 600 / 10:00                           | 240 / 04:00                            |
| POWER9 | Cutlings Light     | 600 / 10:00                           | 240 / 04:00                            |
| POWER7 | IR Bloom           | 210 / 03:30 , 230 / 03:50, 585 / 9:45 | 220 / 03: 40, 255 / 04:15, 600 / 10:00 |
| POWER8 | IR Mother Plant    | 585 / 9:45                            | 240 / 04:00                            |
