# Tasmota Rules

See [Tasmota rules documentation](https://tasmota.github.io/docs/Rules/) for more info (rules can also be set via `MQTT`).

## Rule1 for Aeroponic Cloner Pump (conntcted to `POWER1`)
uses Timer1 and Timer2 - 1min on - 4min off:

`Rule1 ON Power1#Boot DO backlog Power1 ON; RuleTimer1 60 ENDON ON Rules#Timer=1 DO backlog Power1 OFF; RuleTimer2 240 ENDON ON Rules#Timer=2 DO backlog Power1 ON; RuleTimer1 60 ENDON`

## Rule2 for Aeroponic Main Setup Pump (connected to `POWER10`)
uses Timer3 and Timer4 - 1min on - 4min off:

`Rule2 ON Power10#Boot DO backlog Power10 ON; RuleTimer3 60 ENDON ON Rules#Timer=3 DO backlog Power10 OFF; RuleTimer4 240 ENDON ON Rules#Timer=4 DO backlog Power10 ON; RuleTimer3 60 ENDON`

## Rule3 for 60x60 Main Light (connected to `POWER4`)
e.g. turn light on at 10:00 and off at 04:00:

`Rule3 ON Time#Minute=600 DO POWER4 ON ENDON ON Time#Minute=1680 DO POWER4 OFF ENDON`
e.g. turn light on at 10:00 and off at 22:00:

`Rule3 ON Time#Minute=600 DO POWER4 ON ENDON ON Time#Minute=1320 DO POWER4 OFF ENDON`

## Rule4 for 60x40 Mother Plant Light (connected to `POWER2`)
e.g. turn light on at 10:00 and off at 04:00:

`Rule4 ON Time#Minute=600 DO POWER2 ON ENDON ON Time#Minute=1680 DO POWER2 OFF ENDON`

## Rule5 for 60x40 Cutlings Light (connected to `POWER9`)
e.g. turn light on at 10:00 and off at 04:00:

`Rule5 ON Time#Minute=600 DO POWER9 ON ENDON ON Time#Minute=1680 DO POWER9 OFF ENDON`

## Rule6 for main IR wakeup light (connected to `POWER7`)
apply 15min IR before main light, then turn on half an hour before main light ends for 10min, off for 10min, on for 10min again, main light off, and then still on for 15mins.
This is the rule for the main light turning on at 10:00 and off at 04:00:

`Rule6 ON Time#Minute=585 DO POWER7 ON ENDON ON Time#Minute=600 DO POWER7 OFF ENDON ON Time#Minute=1650 DO POWER7 ON ENDON ON Time#Minute=1660 DO POWER7 OFF ENDON ON Time#Minute=1670 DO POWER7 ON ENDON ON Time#Minute=1695 DO POWER7 OFF ENDON`

## Rule7 for mother plant IR wakeup light (connected to `POWER8`)
apply 15min IR before main light, then turn on half an hour before main light ends for 10min, off for 10min, on for 10min again, main light off, and then still on for 15mins.
This is the rule for the main light turning on at 10:00 and off at 04:00:

`Rule7 ON Time#Minute=585 DO POWER8 ON ENDON ON Time#Minute=600 DO POWER8 OFF ENDON ON Time#Minute=1650 DO POWER8 ON ENDON ON Time#Minute=1660 DO POWER8 OFF ENDON ON Time#Minute=1670 DO POWER8 ON ENDON ON Time#Minute=1695 DO POWER8 OFF ENDON`

## Rule8 for 30min UV bursts (connected to `POWER6`)
e.g. give UV light at 13:00 and 15:00:

`Rule8 ON Time#Minute=780 DO POWER6 ON ENDON ON Time#Minute=810 DO POWER6 OFF ENDON ON Time#Minute=900 DO POWER6 ON ENDON ON Time#Minute=930 DO POWER6 OFF ENDON`

<b>NOTE:</b>
Do not forget to enable rules with `Rule[X] 1` e.g. `Rule1 1` for Rule1 (either in the console or via MQTT).