# Ring Oscillator Based True Random Number Generator (TRNG)

## Overview
This project presents the design and implementation of a True Random Number Generator (TRNG) using ring oscillator architecture in Cadence Virtuoso. The design utilizes inherent circuit noise, jitter, and process variations to generate unpredictable random bits for hardware security applications.

---

## Objectives
- Design a hardware-based TRNG using ring oscillators  
- Generate entropy using jitter and timing variations  
- Improve randomness using XOR logic  
- Implement sampling using a D Flip-Flop  
- Simulate and analyze output using Cadence Virtuoso  

---

## Working Principle
The TRNG operates based on the phase difference and jitter between two independent ring oscillators.

1. Two ring oscillators generate oscillating signals  
2. Due to process variations, their frequencies slightly differ  
3. Outputs are combined using an XOR gate  
4. The XOR output is sampled using a D Flip-Flop  
5. The final output produces a random bitstream  

---

## Architecture
Ring Oscillator 1 ─┐
├── XOR ── D Flip-Flop ── Random Output
Ring Oscillator 2 ─┘ ↑
Clock (VPULSE)

---

## Tools Used
- Cadence Virtuoso  
- Spectre Simulator  
- Analog Design Environment (ADE L)  

---

## Implementation Details
- Two 5-stage ring oscillators were designed using CMOS inverters  
- XOR gate used for entropy enhancement  
- D Flip-Flop used for synchronous sampling  
- VPULSE used as clock input  
- Buffer stages added to improve signal integrity  

---

## Simulation
- Analysis Type: Transient (tran)  
- Stop Time: 500 ns – 1 µs  
- Output observed:
  - Oscillator waveforms  
  - XOR output  
  - Final sampled random bits  

---

## Results
- Oscillators generated periodic signals with slight phase variation  
- XOR output showed irregular transitions  
- Final output produced a random bitstream  
- Issues like metastability were reduced using buffering and clock tuning  

---

## Low Power Techniques
- Used minimum-stage ring oscillators  
- Optimized transistor sizing  
- Reduced clock frequency to minimize switching power  
- Avoided additional complex circuitry  

---

## Future Scope
- Validate randomness using NIST SP 800-22 test suite  
- Improve entropy using multiple oscillators  
- Apply post-processing techniques (whitening)  
- Integrate with cryptographic systems  

---
