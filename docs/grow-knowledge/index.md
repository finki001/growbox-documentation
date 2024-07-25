# Important things to know
- [UV/IR supplement lights - how and why](https://www.mars-hydro.com/info/post/how-to-use-uv-and-ir-for-growing-indoor-plants)
- [Leaf VPD](https://www.dimluxlighting.com/knowledge/blog/vapor-pressure-deficit-the-ultimate-guide-to-vpd/)

`const leafVPD = 0.61078 * Math.exp((msg.payload.MLX90614.OBJTMP / (msg.payload.MLX90614.OBJTMP + 237.3) * 17.2694)) - 0.61078 * Math.exp((msg.payload.BME280.Temperature / (msg.payload.BME280.Temperature + 237.3) * 17.2694)) * msg.payload.BME280.Humidity / 100.0;`

- [Cannabis problem guide](https://www.growweedeasy.com/marijuana-symptoms)