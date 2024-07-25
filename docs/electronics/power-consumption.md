# Power consumption
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


`// TODO: add details how much energy the system consumes in different modes (veg/bloom, aero cloner running or not)`
