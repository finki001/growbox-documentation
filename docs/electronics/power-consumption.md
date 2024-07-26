# Power consumption
Peak power consumption is either `167.4W` (grow) or `227.4W` (bloom)

## 60x60 main area (`97.8W / 157.8W`)
`35W` extractor, `2.8W` monkey fans: `37.8W`

### Growing (`60W`)
average `40W`. Peak with UV/IR (never on at the same time): `60W`

### Flowering (`120W`)
average `100W`. Peak with UV/IR (never on at the same time): `120W`

## 60x40 area (`69.6W`)
`15W` extractor, `2.8W` monkey fans: `17.8W`

### 60x40 mother plant (`21.8W`)
- `20W` for the growlight
- `1.8W` for the airstone pump

### 60x40 aero cloner (`30W`)
`26W` for the growlight, and let's say `4W` for the pump: `30W`

### Monitoring
I'm using a smart plug that supports measuring the total power consumption of the grow setup and is also Tasmota compatible:
[Tasmota Steckdose NOUS A1T](https://www.amazon.de/gp/product/B0054PSIPA/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&th=1)

An example payload would look like this:
```
{
  "Time": "2024-07-24T22:24:32",
  "ENERGY": {
    "TotalStartTime": "2024-01-04T15:00:40",
    "Total": 279.919,
    "Yesterday": 2.499,
    "Today": 2.29,
    "Period": 11,
    "Power": 126,
    "ApparentPower": 178,
    "ReactivePower": 125,
    "Factor": 0.71,
    "Voltage": 296,
    "Current": 0.601
  }
}
```