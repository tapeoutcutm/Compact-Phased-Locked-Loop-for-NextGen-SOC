![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/lvs/badge.svg)

---

## Introduction

Phase-Locked Loops (PLLs) are fundamental building blocks in integrated circuits (ICs), playing a vital role in frequency synthesis and clock generation. By aligning the phase and frequency of an output signal with a given reference, PLLs find widespread use in communication systems, microprocessors, and mixed-signal designs.

This document presents the design of a PLL circuit developed using open-source Electronic Design Automation (EDA) tools and the Skywater 130nm (Sky130) Process Design Kit (PDK). The design is structured into four primary sub-blocks:

Phase Frequency Detector (PFD): Compares the phase and frequency of reference and feedback signals.

Charge Pump: Translates the PFD output into a current signal that regulates the VCO control voltage.

Voltage-Controlled Oscillator (VCO): Produces an oscillating signal whose frequency depends on the control voltage.

Divider: Reduces the VCO output frequency to generate feedback for the PFD.

Each sub-block was designed independently by specialized teams and then integrated to form the complete PLL system.
---
