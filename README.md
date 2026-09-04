# DC-DC Buck Converter Design and Simulation

**12 V Input → ~4.52 V Output | 100 kHz | 41.7% Duty Cycle | ~88.9% Efficiency**

## Overview

This project demonstrates the design and simulation of a DC-DC buck converter in LTspice. The converter steps down a 12 V DC input to approximately 4.52 V using PWM-controlled switching.

The circuit was analyzed for output voltage, voltage ripple, inductor current, switching frequency, startup response, and overall efficiency.

## Circuit Parameters

| Parameter | Value |
|---|---|
| Input Voltage | 12 V |
| Switching Frequency | 100 kHz |
| PWM Period | 10 µs |
| PWM ON Time | 4.17 µs |
| Duty Cycle | 41.7% |
| Inductor | 100 µH |
| Output Capacitor | 100 µF |
| Load Resistance | 5 Ω |

## Simulation Results

| Measurement | Result |
|---|---|
| Average Output Voltage | ≈ 4.52 V |
| Average Load Current | ≈ 0.903 A |
| Average Inductor Current | ≈ 0.916 A |
| Inductor RMS Current | ≈ 0.920 A |
| Inductor Current Ripple | ≈ 0.310 A p-p |
| Output Voltage Ripple | ≈ 3.14 mV p-p |
| Output Ripple Percentage | ≈ 0.0695% |
| Average Input Current | ≈ 0.383 A |
| Input Power | ≈ 4.59 W |
| Output Power | ≈ 4.08 W |
| Simulated Efficiency | ≈ 88.9% |

> **Note:** LTspice reports the average input-source current as approximately −0.383 A due to its current reference direction. The magnitude (0.383 A) was used when calculating input power and efficiency.

## PWM Control

The converter uses a PWM signal with a period of 10 µs and an ON time of approximately 4.17 µs.

### Switching Frequency

**f = 1 / T = 1 / (10 µs) = 100 kHz**

### Duty Cycle

**D = Ton / T = 4.17 / 10 = 41.7%**

## Simulation Waveforms

### Output Voltage

![Output Voltage](Results/output_voltage.png)

The simulated converter produces an average output voltage of approximately 4.52 V from a 12 V DC input.

### Output Voltage Ripple

![Output Voltage Ripple](Results/output_voltage_ripple.png)

The steady-state output voltage ripple is approximately 3.14 mV peak-to-peak, corresponding to about 0.0695% of the output voltage.

### Inductor Current

![Inductor Current](Results/inductor_current.png)

The inductor current has the expected triangular waveform for continuous switching operation, with an average current of approximately 0.916 A.

### Switching Frequency

![Switching Frequency](Results/frequency.png)

The measured switching period is approximately 10 µs, corresponding to a switching frequency of approximately 100 kHz.

### Switching Waveform

![Switching Waveform](Results/switching_waveform.png)

The PWM switching signal controls the converter switch and determines the energy transferred to the output during each switching cycle.

### Startup Response

![Startup Response](Results/startup_response.png)

The startup waveform shows the transient response of the converter before the output settles to its steady-state value.

## Power and Efficiency

Using the measured input-current magnitude:

**Pin = Vin × Iin**

**Pin = 12 V × 0.3826 A ≈ 4.59 W**

The simulated output power is approximately:

**Pout ≈ 4.08 W**

Therefore, the simulated efficiency is:

**Efficiency = (Pout / Pin) × 100 ≈ 88.9%**

## Tools

- LTspice
- GitHub

## Files

- `Buck_Converter.asc` — LTspice schematic and simulation setup
- `Results/` — Simulation waveform screenshots
- `README.md` — Project documentation

## What I Learned

This project helped demonstrate the relationship between PWM duty cycle, switching frequency, and the energy-storage components of a DC-DC buck converter. It also provided experience analyzing output ripple, inductor current, transient response, power consumption, and converter efficiency using LTspice.
