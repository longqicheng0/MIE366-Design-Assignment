# Engineering Specification

<!-- Google Docs draft, created and visually checked 2026-09-14:
https://docs.google.com/document/d/1G7m3psEyE-etR88Xyv4Ig0tU98JhpPj-uQR8AM_3weM/edit
The native document uses formatted subscripts and the equivalent exact gain 61/7.
-->

[REQ] The current-sense block shall measure returning load current from 0 to 3.5 A using a 0.1 Ω sense resistor connected on the low side, with its lower terminal tied to circuit ground. It shall provide one voltage output representing load current [1, pp. 2–3].

[DERIVED] The nominal sense voltage is

\[
V_{\mathrm{SENSE}}=I_{\mathrm{LOAD}}R_{\mathrm{SENSE}}
=(0.1\,\Omega)I_{\mathrm{LOAD}},\qquad
0\leq V_{\mathrm{SENSE}}\leq0.35\,\mathrm{V}.
\]

[REQ] The output shall target a linear relationship with an offset, from 0.25 V at 0 A to 3.3 V at 3.5 A [1, pp. 3, 7]. [DERIVED] Therefore, the nominal transfer function is

\[
V_{\mathrm{OUT}}
=\frac{3.3\,\mathrm{V}-0.25\,\mathrm{V}}{0.35\,\mathrm{V}}V_{\mathrm{SENSE}}+0.25\,\mathrm{V}
\approx8.7143V_{\mathrm{SENSE}}+0.25\,\mathrm{V}.
\]

[REQ] The circuit may use up to three LM324N op-amp units. These should be powered from a single +19 V supply with the negative supply terminal at ground. Only the permitted op-amps and resistors may be used. Non-sense resistors should have nominal values from 1 kΩ to 100 kΩ, selected from the standard 5% values in Appendix A. Series or parallel combinations must not circumvent this range [1, pp. 3, 10].

[REQ] The final design shall be simulated over the specified current range to demonstrate feasibility [1, p. 4]. The handout permits small endpoint departures from standard-value rounding, with less margin at the lower endpoint and upward deviation preferred there [1, p. 9]. A quantitative acceptance band remains to be clarified.

## References

[1] *MIE366 — Design Assignment 1B, Deliverable Handout*, v1.1, pp. 2–4, 7, 9–10. Course-provided document: `source-docs/MIE366 - Design Assignment 1B, Deliverable Handout v1.1.pdf`.
