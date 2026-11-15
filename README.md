# RS485 Bench

An interactive, single-page explainer that builds up RS485 from the wire. Each section has a short explanation, a few things to try, and a live simulation.

| # | Experiment | What you can change |
|---|---|---|
| 1 | Two wires, one difference | Common-mode noise, differential noise, signal swing. Compares a differential receiver with a single-ended one. |
| 2 | The driver is four switches | Bit, supply voltage, bus load. Shows the H-bridge, current path and the 1.5 V minimum into 54 Ω. |
| 3 | Ground offset | Ground difference between sender and receiver, against the −7 V to +12 V input window. |
| 4 | Termination and reflections | Cable length, far-end resistor, baud rate, edge speed. Zoomed edge plus a bit stream with sample points. |
| 5 | Bias and the idle bus | Bias on/off, resistor value, terminators, noise, standard or true fail-safe receiver. Shows garbage bytes on an unbiased bus. |
| 6 | How a UART frames a byte | Character to send and receiver clock error. Steps through the start bit, data bits and stop bit. |
| 7 | Many devices, one pair | Modbus RTU master with three slaves, real CRC-16, broadcast, and an early DE release that corrupts the last byte. |

## Run it

It's a single static file with no build step. Open `index.html` in a browser, or serve the folder with any static server.

## Accuracy

Limits come from TIA/EIA-485-A: ±200 mV receiver thresholds, at least 1.5 V into 54 Ω, −7 V to +12 V common mode, and 32 unit loads. Driver resistance, cable behaviour (a lossless 120 Ω line) and receiver thresholds beyond that are simplified models close to a MAX485-class part. They're meant for building intuition, not for signing off a design.
