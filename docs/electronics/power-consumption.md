# Power consumption

## 60x60 main area (`120W/180W`)
`35W` extractor, `5W` monkey fans: `40W`

### Growing (`80W`)
`60W` average. Peak with UV/IR (never on at the same time): `80W`

### Flowering (`140W`)
`100W` average. Peak with UV/IR (never on at the same time): `140W`

## 60x40 area (`130W`)
`15W` extractor, `5W` monkey fans: `20W`

### 60x40 mother plant (`80W`)
`60W` average. Peak with IR (never on at the same time): `80W`
<!-- # - `2W` for the airstone pump-->

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