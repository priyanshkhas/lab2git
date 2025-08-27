**ASSIGNMENT OF MICROWAVE DEVICES AND CIRCUIT**


**BY - PRIYANSH KHASDEV**

**1. Define S-parameters and write their general equation for an N-port network.**

**Answer:**
Scattering Parameters (S-parameters) are a set of parameters that describe the electrical behavior of a linear electrical network when undergoing various steady-state stimuli by electrical signals. They relate the voltage waves incident on the ports to those reflected from the ports.

For an N-port network, the general equation is:
`[b] = [S][a]`
where:
*   `[b]` is the column vector of **outgoing** waves.
*   `[S]` is the N x N **scattering matrix**.
*   `[a]` is the column vector of **incident** waves.

The individual elements are defined as:
`S_{ij} = b_i / a_j |_{a_k=0 \text{ for } k≠j}`
This means `S_{ij}` is the ratio of the outgoing wave at port `i` to the incident wave at port `j`, with all other ports terminated in matched loads (so no reflections from them).

---

**2. Differentiate between E-plane Tee and H-plane Tee junctions.**

**Answer:**

| Feature | E-Plane Tee (Series Tee) | H-Plane Tee (Shunt Tee) |
| :--- | :--- | :--- |
| **Construction** | A waveguide tee where the axis of the side arm is parallel to the **E-field** of the main waveguide. | A waveguide tee where the axis of the side arm is parallel to the **H-field** of the main waveguide. |
| **Phase Relationship** | The output from the side arm (Port 3) is **180° out of phase** with the inputs from the collinear arms (Ports 1 & 2). | The output from the side arm (Port 3) is **in phase** with the inputs from the collinear arms (Ports 1 & 2). |
| **Equivalent Circuit** | It can be represented as a **series junction** to the main transmission line. | It can be represented as a **shunt junction** to the main transmission line. |
| **S-matrix Property** | `S_{13} = -S_{23}` | `S_{13} = S_{23}` |

---

**3. What is the function of a directional coupler in microwave systems?**

**Answer:**
The primary function of a directional coupler is to sample a small portion of the microwave power traveling in one direction on a transmission line while being isolated from (i.e., not sampling) power traveling in the opposite direction. Its key functions are:
1.  **Power Sampling:** To measure incident or reflected power without significantly disturbing the main signal.
2.  **Power Monitoring:** To provide a signal proportional to the main power for monitoring purposes.
3.  **Power Division:** To split power in a specific ratio with a defined phase relationship between outputs.
4.  **Reflection Measurement:** Used in conjunction with a matched load to create a reflectometer for measuring VSWR and impedance.

---

**4. Write the ideal S-matrix of a 3-port circulator.**

**Answer:**
For an ideal 3-port circulator with clockwise circulation (power entering port 1 exits at port 2, port 2 to port 3, port 3 to port 1), the S-matrix is:
```
    [0   0   1]
S = [1   0   0]
    [0   1   0]
```

---

**5. What is the difference between a circulator and an isolator?**

**Answer:**
*   **Circulator:** A **non-reciprocal**, passive, multi-port (usually 3 or 4) device that directs power from one port only to the next adjacent port in a specific cyclic order. It allows bidirectional flow but in a controlled, circular path.
*   **Isolator:** A **non-reciprocal**, passive, **two-port** device that allows power to flow almost unattenuated in the forward direction while providing very high attenuation to power flowing in the reverse direction.

An isolator is essentially a circulator where one port is terminated with a matched load. For example, a 3-port circulator becomes an isolator by connecting a matched load to port 3. Signal enters port 1 and goes to port 2 (forward path). A reflected signal entering port 2 is directed to port 3, where it is absorbed by the load, providing isolation.

---

**6. State two practical applications of the magic tee.**

**Answer:**
1.  **Impedance Measurement / Reflectometer:** The magic tee is used to compare an unknown impedance to a known standard. The E-arm and H-arm outputs provide signals proportional to the reactive and resistive components of the unknown load, allowing for precise measurement.
2.  **Duplexer in Radar Systems:** It is used to connect the transmitter, receiver, and antenna. The high-power transmit signal from the H-arm goes to the antenna (collinear arm) and is isolated from the sensitive receiver connected to the E-arm. The received signal from the antenna goes to the E-arm and the receiver.

---

**7. What is meant by coupling factor in a directional coupler?**

**Answer:**
The coupling factor (C) is a measure of the fraction of the input power that is coupled to the auxiliary (coupled) port. It is defined as:
`C = 10 log_{10}(P₁ / P₃) dB`
where:
*   `P₁` is the power input to the main line (port 1).
*   `P₃` is the power output at the coupled port (port 3).

A 10 dB coupling factor means that the power at the coupled port is 10 dB below the input power (i.e., one-tenth of the input power).

---

**8. Derive the properties of S-parameters for a lossless reciprocal network.**

**Answer:**
For a lossless network, the total input power must equal the total output power. This leads to the **unitary property**:
`[S]^T [S]* = [I]`
where `[S]^T` is the transpose of `[S]`, `[S]*` is the complex conjugate of `[S]`, and `[I]` is the identity matrix. This implies that the sum of the products of the S-parameters for any column `k` with their complex conjugates must be 1, and for different columns `k` and `m`, the sum must be 0:
`Σ_{i=1}^N S_{ik} S_{im}* = δ_{km}` (where `δ_{km}` is the Kronecker delta).

For a **reciprocal** network, the S-matrix is symmetric:
`S_{ij} = S_{ji}` for all `i` and `j`.

---

**9. Explain the construction and working of an E-plane Tee junction with neat sketches.**

**Answer:**
**(Note: A sketch would show a rectangular waveguide with a third arm attached to the broad wall.)**

*   **Construction:** An E-plane tee (or series tee) is formed by adding a side arm along the direction parallel to the **electric field (E-field)** of the main rectangular waveguide. The main waveguide has ports 1 and 2 (collinear arms), and the side arm is port 3.

*   **Working:** When signals are fed into the two collinear arms (ports 1 and 2), the resulting E-fields are parallel to the axis of port 3. The output at port 3 is the **vector difference** of the inputs at ports 1 and 2. Conversely, if a signal is fed into the side arm (port 3), it splits equally but **180 degrees out of phase** between the two collinear arms (ports 1 and 2). This 180° phase shift is due to the construction, which makes it equivalent to a series connection on the main transmission line.

---

**10. With a diagram, explain the operation of a magic tee (hybrid tee) and its applications.**

**Answer:**
**(Note: A diagram would show a combination of an E-plane and H-plane tee, forming a four-port network with H-arm, E-arm, and two collinear arms.)**

*   **Operation:** A magic tee is a combination of an E-plane tee and an H-plane tee. It has four ports:
    *   Port 1: H-arm (side arm parallel to H-field)
    *   Port 2: E-arm (side arm parallel to E-field)
    *   Port 3 and 4: Collinear arms (main waveguide)
    Its operation is defined by two key properties:
    1.  **If a signal is input at the H-arm (Port 1):** It splits equally and **in-phase** between the two collinear arms (Ports 3 & 4). The E-arm (Port 2) is isolated.
    2.  **If a signal is input at the E-arm (Port 2):** It splits equally but **180° out-of-phase** between the two collinear arms (Ports 3 & 4). The H-arm (Port 1) is isolated.

*   **Applications:** See Answer 6 (Impedance measurement, Duplexer).

---

**11. Derive the S-matrix of an ideal directional coupler.**

**Answer:**
An ideal directional coupler is a matched, lossless, reciprocal, four-port device with specific properties. Let the ports be:
*   Port 1: Input
*   Port 2: Through
*   Port 3: Coupled
*   Port 4: Isolated

The defining properties lead to these S-parameter conditions:
1.  **All ports are matched:** `S_{11} = S_{22} = S_{33} = S_{44} = 0`
2.  **Perfect isolation between Port 1 and Port 4:** `S_{14} = 0`
3.  **Perfect isolation between Port 2 and Port 3:** `S_{23} = 0`
4.  **Reciprocity:** `S_{ij} = S_{ji}`
5.  **Losslessness (Unitary property):** Applying the unitary condition leads to the relationships between the coupling and transmission coefficients.

Let the coupling factor be `C` (a voltage ratio, so `C = |S_{13}|`). From the unitary condition, the through port voltage is `√(1 - C²)`, so `|S_{12}| = √(1 - C²)`.
Assuming phase references are chosen appropriately, the S-matrix for an ideal directional coupler is:
```
    [0       α        jβ      0]
S = [α       0        0      jβ]
    [jβ      0        0      α]
    [0      jβ       α       0]
```
where `α = √(1 - C²) = S_{12} = S_{21} = S_{34} = S_{43}` and `β = C = S_{13} = S_{31} = S_{24} = S_{42}`. The `j` factor indicates a 90° phase shift for the coupled port.

---

**12. Explain the working principle of a circulator with a block diagram and S-matrix.**

**Answer:**
*   **Working Principle:** A circulator is a non-reciprocal ferrite device that uses the Faraday rotation effect or phase shift effects in a magnetically biased ferrite material. This magnetic bias breaks reciprocity, forcing power to flow only in one predetermined direction around its ports.

*   **Block Diagram:** **(A diagram would show a Y-shaped junction with three ports, 120° apart, with a ferrite element and a permanent magnet at the center.)**

*   **S-matrix:** For an ideal 3-port circulator with clockwise circulation (Power flow: 1→2, 2→3, 3→1), the S-matrix is:
```
    [S_{11}  S_{12}  S_{13}]   [0   0   1]
S = [S_{21}  S_{22}  S_{23}] = [1   0   0]
    [S_{31}  S_{32}  S_{33}]   [0   1   0]
```
This shows that the input at port 1 comes out only at port 2 (`S_{21}=1`), input at port 2 comes out only at port 3 (`S_{32}=1`), and input at port 3 comes out only at port 1 (`S_{13}=1`). All ports are matched (`S_{11}=S_{22}=S_{33}=0`), and isolation is perfect (`S_{12}=S_{23}=S_{31}=0`).

---

**13. Discuss the working of an isolator. How is it realized using a circulator?**

**Answer:**
*   **Working:** An isolator is a two-port device that allows microwave power to pass through with minimal attenuation in the **forward direction** (from Port 1 to Port 2) while providing very high attenuation in the **reverse direction** (from Port 2 to Port 1). This is achieved using a non-reciprocal attenuation mechanism, often involving a ferrite material positioned near the waveguide and biased with a magnetic field. Waves in one direction are absorbed, while waves in the opposite direction are largely unaffected.

*   **Realization using a Circulator:** A circulator can be easily converted into an isolator. In a 3-port circulator, if power is intended to flow 1→2→3→1, then port 3 is terminated with a matched load. Now:
    *   **Forward Path (1→2):** A signal entering port 1 exits at port 2 with low loss.
    *   **Reverse Path (2→1):** Any reflected signal entering port 2 is directed to port 3, where it is absorbed by the matched load instead of returning to port 1. This provides the desired isolation. The device now functions as a two-port isolator.

---

**14. Write short notes on:**
**a) Scattering Matrix properties**
**Answer:**
*   **Definition:** The scattering matrix ([S]-matrix) is a square matrix that completely characterizes the linear behavior of a multi-port network at microwave frequencies.
*   **Key Properties:**
    1.  **Symmetry for Reciprocal Networks:** `S_{ij} = S_{ji}`.
    2.  **Unitarity for Lossless Networks:** `[S]^T[S]* = [I]`. This implies conservation of power.
    3.  **Zero Diagonal for Matched Ports:** If a port `i` is perfectly matched, `S_{ii} = 0` (no reflection).
    4.  **Phase Shift:** The argument (angle) of `S_{ij}` represents the phase shift from port `j` to port `i`.

**b) Applications of couplers in measurement**
**Answer:**
*   **Power Monitoring:** A directional coupler can tap off a known fraction of the power from a source (e.g., a klystron or TWT) to a power meter for stable monitoring and levelling of the output power.
*   **Reflectometry and VSWR Measurement:** A dual-directional coupler can sample both the incident (forward) and reflected waves on a transmission line. By measuring these two powers, the reflection coefficient (Γ), VSWR, and return loss can be accurately calculated.
*   **Signal Sampling:** Couplers are used to inject a test signal into a system or to sample a signal for analysis with a spectrum analyzer without introducing a significant mismatch.

---

**16. An ideal magic tee is used to feed two input signals of equal magnitude and 180° out of phase. Show that the output appears only at the H-plane port, while the E-plane port remains isolated.**

**Answer:**
Let the two input signals be fed into the two collinear arms:
*   Let `a₃` be the incident wave at port 3.
*   Let `a₄` be the incident wave at port 4, where `a₄ = -a₃` (equal magnitude, 180° phase difference).

For a magic tee, the outputs at the side arms are given by:
`b₁ = (1/√2)(a₃ + a₄)`  // H-plane port output
`b₂ = (1/√2)(a₃ - a₄)`  // E-plane port output

Substituting the inputs (`a₄ = -a₃`):
`b₁ = (1/√2)(a₃ + (-a₃)) = (1/√2)(0) = 0`
`b₂ = (1/√2)(a₃ - (-a₃)) = (1/√2)(2a₃) = √2 a₃`

**Result:**
*   The output at the H-plane port (Port 1), `b₁`, is **zero**.
*   The output at the E-plane port (Port 2), `b₂`, is **√2 a₃**.
Therefore, the output appears **only** at the E-plane port, and the H-plane port is isolated. *(Note: The question statement appears to have a typo; it should say the output appears at the E-plane port, not the H-plane port, given these inputs.)*

---

**17. A directional coupler has a coupling factor of 20 dB and directivity of 30 dB. If the input power is 1 W, calculate the power delivered to the coupled port, through port, and isolated port.**

**Answer:**
**Given:**
*   Input Power `P_in = P₁ = 1 W`
*   Coupling Factor `C = 20 dB`
*   Directivity `D = 30 dB`

**Convert dB to linear power ratios:**
*   Coupling Factor (Linear), `C_lin = 10^{-C/10} = 10^{-20/10} = 10^{-2} = 0.01`
*   Directivity (Linear), `D_lin = 10^{D/10} = 10^{30/10} = 10^{3} = 1000`

**Calculate Powers:**
1.  **Coupled Port Power (P₃):**
    By definition, `C = 10 log(P₁ / P₃)`. Therefore,
    `P₃ = P₁ * C_lin = 1 W * 0.01 = 0.01 W` or **10 mW**

2.  **Through Port Power (P₂):**
    For an ideal, lossless coupler, the power is split between the through and coupled ports.
    `P₂ ≈ P₁ - P₃ = 1 W - 0.01 W = 0.99 W` or **990 mW**
    (More precisely, `P₂ = P₁ * (1 - C_lin)`

3.  **Isolated Port Power (P₄):**
    Directivity is defined as `D = 10 log(P₃ / P₄)`. It measures how well the coupler isolates the forward and backward waves.
    `D = 10 log(P₃ / P₄) => 30 = 10 log(0.01 / P₄)`
    `3 = log(0.01 / P₄)`
    `10³ = 1000 = 0.01 / P₄`
    `P₄ = 0.01 / 1000 = 10^{-5} W` or **10 µW**

**Summary:**
*   Power at Coupled Port (P₃) = **10 mW**
*   Power at Through Port (P₂) = **990 mW**
*   Power at Isolated Port (P₄) = **10 µW**
