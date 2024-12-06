# Tasmota Rules

See [Tasmota rules documentation](https://tasmota.github.io/docs/Rules/) for more info (rules can also be set via `MQTT`).

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

## Current Mother Plant Lighting Ruleset (`Rule1`)
```
ON Time#Minute=210 DO POWER8 ON ENDON
ON Time#Minute=220 DO POWER8 OFF ENDON
ON Time#Minute=230 DO POWER8 ON ENDON
ON Time#Minute=240 DO POWER2 OFF ENDON
ON Time#Minute=255 DO POWER8 OFF ENDON
ON Time#Minute=585 DO POWER8 ON ENDON
ON Time#Minute=600 DO POWER8 OFF ENDON
ON Time#Minute=600 DO POWER2 ON ENDON
```

This rule means the following considering POWER8 is the mother plant IR LED and POWER2 is the mother plant Grow LED:
(`Minute=210` means: 210 minutes from midnight so for this example 3:30)
- 3:30: IR ON
- 3:40: IR OFF
- 3:50: IR ON
- 4:00: Grow OFF
- 4:15: IR OFF
- 9:45: IR ON
- 10:00: IR OFF
- 10:00: Grow ON

Basically turn the light on at 10:00 and off at 04:00 (so 18h on, 6h off). In addition IR light is supplemented 15min before light turns on and 15min after turned off.
With an additional 10min IR light half an hour before the grow light turns off (3:30), then off and on again for 10 mins to hepl the plant sleep.
