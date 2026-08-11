# USER MANUAL: DOM RADIO SUITE (v1.0)

---

## 1. INTRODUCTION & HISTORICAL PROTOTYPE

**DOM RADIO MASTER** is a mastering processor designed to model the physical non-linearities and mechanics of late 1970s broadcast recording gear. Built on a Grey-Box architecture, it component-models the entire signal path: from input transformers and discrete transistor preamps to magnetic tape hysteresis and output clipping.

The preamp and EQ section reference Hungarian **MEQ-610** studio modules (found in BEAG / Mechlabor broadcast consoles).

The noise profiles (**Tape Noise**), granular textures, and contact friction patterns were directly sampled from authentic regional radio tape archives in Dagestan ("Makhachkala 1978").

---

## 2. DSP ARCHITECTURE & DESIGN CHOICES

Specific engineering choices were made during DSP development to ensure musicality:
* **Modified Saturation Core (Spiral):** The input stage uses a logarithmic sine curve with tube-like characteristics, allowing aggressive overdriving without sacrificing transient clarity.
* **Decoupled Non-linearities:** Transistor preamp drive (`PRE DRIVE`) and tape magnetization (`TAPE DRIVE`) are mathematically separated, enabling use as a pure tape emulator or clean transistor drive.
* **Expanded Tape Headroom:** Langevin magnetic saturation point is expanded by +40% relative to the original physical prototype to provide a wider usable range for `TAPE DRIVE`.
* **Phase-Linear Smart Mix:** Dry/Wet parallel processing operates without double-scaling, guaranteeing phase coherence at any drive level.

---

## 3. PARAMETER REFERENCE

### SECTION 1: INPUT & DRIVE
* **IN GAIN (-18.0 to +18.0 dB):** Input trim.
* **LINK (Button):** Inverse link between `IN GAIN` and `OUTPUT`.
* **DRIVE TYPE:** 
  * *Silicon:* Symmetrical clipping (generates odd harmonics: 3rd, 5th).
  * *Germanium:* Asymmetrical clipping (generates even harmonics: 2nd) with DC offset.
* **PRE DRIVE (1.0 to 10.0):** Transistor preamp drive.
* **TAPE DRIVE (0% to 100%):** Tape magnetization level along Langevin curve.
* **SLEW (0.0 to 1.0):** Slew-rate limiter ($dV/dt$). Acts as a transient tamer and gentle de-esser.
* **PRE / TAPE / SLEW LEDs:** Real-time saturation activity indicators.

### SECTION 2: TAPE & CALIBRATION
* **TAPE SPEED (1.875 to 15.0 ips):** Continuous tape speed control.
* **EQ STD:** Hardware EQ standards: *CCIR* (35/70 µs) or *NAB* (90 µs).
* **AIR (0.0 to 15.0 dB):** Models the LC-resonant circuit in record amplifiers for high-frequency sheen.
* **BIAS (-1.0 to +1.0):** Tape bias. Under-bias increases THD and transients; Over-bias compresses highs.
* **DECAY (0.0 to 10.0):** Models HF head gap loss and friction absorption.
* **TAPE MODEL:** Selects tape formulation (*SVEMA A4409*, *ORWO TYP 106*, *SCOTCH 2500*, *BASF SPR 50*).

### SECTION 3: OUTPUT & METERING
* **SMART MIX (0% to 100%):** Parallel dry/wet processing.
* **OUTPUT (-18.0 to +18.0 dB):** Output level *before* final analog clipper.
* **DETAILS (0% to 100%):** Upward compression intensity for pulling out subtle textures. *Modern Detail Extractor (Musical Upward Compressor)* — secret weapon for electronic producers and working with old samples. It gently lifts hidden micro-textures, tails and attacks from the depths of the track, instantly saturating them with analog tape warmth without harsh digital sharpness.
* **TILT (-100% to +100%):** Tonal balance tilt for the Detail Extractor (LF/HF focus).
* **DETAIL ALGO:** Extractor algorithm (*Wideband Tilt* or *Multiband Spectral*).
* **IRON (0% to 100%):** Output transformer core saturation for sub-bass weight.
* **VU Meter:** Ballistic logarithmic meter with physical needle inertia.

### SECTION 4: EQ MONITOR (BEAG MEQ-610 Panel)
* **BASS GAIN / TREB GAIN (-18.0 to +18.0 dB):** Low and High shelving filters.
* **BASS FREQ (30 - 300 Hz) / TREB FREQ (1 - 15 kHz):** Shelving cutoff frequencies.
* **CRT Display:** Phosphor oscilloscope visualizer reacting to THD, Wow/Flutter, and dropouts.

### SECTION 5: ARCHIVE '84 UNIT (Master Edition Only)
* **AGE (0 to 50 Years):** Macro age control affecting coercivity, gap loss, and micro-dropouts.
* **OXIDE:** Dropout frequency and depth.
* **AZIMUTH:** L/R phase drift due to head misalignment.
* **BIAS SAG:** Dynamic bias ducking and peak distortion asymmetry.
* **SCRAPE:** High-frequency metallic scrape flutter friction.
* **X-TALK:** Stereo channel crosstalk.
* **WOW & FLUTTER:** Low-frequency speed drift (Wow) and motor vibration (Flutter).
* **TAPE NOISE & HUM:** 50 Hz mains hum and sampled Dagestan tape noise (with *Dynamic* gating mode).
* **TEMPERATURE (15°C to 50°C):** Ambient unit temperature modifying transistor $H_{fe}$ and tape coercivity.

---

## 🕊️ DEDICATION & ACKNOWLEDGMENTS

The **DOM RADIO** project expresses deep gratitude to the pioneers of open DSP programming and the great performers whose voices are forever captured on magnetic tape.

### 💻 Masters of DSP and Open Source Code
* **Chris Johnson (Airwindows):** For his uncompromising fidelity to mathematical purity, minimalism, legendary saturation algorithms, and selfless contribution to the global audio developer community. His philosophy of thinking in sound waves became the main guiding principle in creating this plugin.
* **Jatin Choudhury (ChowDSP / ChowTape):** For his fundamental research in physical magnetic tape modeling, the open-source Giles-Atherton hysteresis equation code, and the inspiration his work has given to a new generation of DSP engineers.

---

### 🎙️ Golden Voices of Dagestan
This plugin is created in memory of and with deep respect for the great singers whose voices and beautiful songs constitute the golden heritage of Makhachkala radio broadcasting:

* **Mui Gasanova** — the legendary Avar singer whose soulful performances became a symbol of the musical culture of the mountainous region.
* **Mariyam Dandamaeva** — the unforgettable Lak nightingale performer whose bright voice was heard in millions of receivers across the Caucasus.
* **Sultanat Kurbanova** — the outstanding Dargin singer whose expressiveness and vocal artistry preserved the power and depth of folk song for us.

*It was the archival tapes of their performances that served as the main auditory reference, test material, and source of noise textures during the debugging of DOM RADIO DSP algorithms.*

---

## 🎨 ARCHITECTURE AND ARTISTIC LICENSE

While DOM RADIO is based on real principles of circuitry from Hungarian **BEAG / Mechlabor MEQ-610** studio modules and Soviet tape transport mechanisms (MEZ/STM), the plugin is not a dry or rigid SPICE clone.

During DSP modeling, conscious **artistic licenses** were taken to make the device more flexible, musical, and applicable in modern digital DAWs:

1. **Hybrid Mathematical Core (Grey-Box):** Instead of blindly copying the limitations of real transistors, the input `Spiral` stage uses a modified logarithmic saturation curve. It combines the attack characteristic of silicon with the smooth limiting of tubes, preserving transient readability even at extreme drive.
2. **Independent Stage Decoupling:** In a real analog tape machine, it is impossible to overheat the input preamp without also overloading the tape itself. In DOM RADIO, the `PRE DRIVE` (transistors) and `TAPE DRIVE` (tape magnetization) stages are mathematically decoupled. You can use the device as a transparent tape saturator or as an aggressive transistor overdrive.
3. **Expanded Dynamic Range (Headroom):** The maximum magnetic saturation point in the Langevin equation is shifted upward by 40% relative to the historical prototype, giving the engineer a smoother and more controllable operating range for the `TAPE DRIVE` knob.
4. **Phase Coherence (Smart Mix):** The Dry/Wet parallel processing is designed without double scaling and completely eliminates comb filtering or the introduction of unwanted phase shifts at any degradation setting.

*DOM RADIO is not a copy of a specific broken device from 1978, but a musical instrument and an artistic image of a sound era.*

---

## 4. TOLERANCE MODELING TECHNOLOGY (TMT)

The `ToleranceModel` engine models component manufacturing variances between left and right channels. Each device generates a persistent 32-bit seed based on your computer's MAC address.

### TMT Unit Modes:
1. **Calibrated (TMT OFF):** Perfect channel symmetry.
2. **Typical:** Standard tolerance variation at **50%** maximum intensity.
3. **Loose:** Full factory component tolerance (**100%**).
4. **Vintage:** Aged component drift (-8% transistor $H_{fe}$, +40% azimuth drift, lowered Head Bump Q).
5. **Custom:** User-defined manual seed.

### Modeled Component Tolerances:
* *Input:* Transformer Gain (±3%), APF Resonance Shift (±5%), Iron Harmonics (±8%).
* *Drive:* Spiral Bias Shift (±4%), Transistor $H_{fe}$ Beta (±15%), Slew Rate (±10%).
* *Tape:* Coercivity (±6%), Gap Loss Freq (±3%), Head Bump Freq (±2%), Head Bump Q (±12%).
* *Mechanics:* Wow Freq Drift (±2%), Flutter Freq Drift (±5%), Azimuth Amplitude (±20%).
* *Output:* Clipper Threshold (±2 dB), Transformer LPF (±300 Hz), Channel Imbalance (±0.5 dB), Crosstalk (±10%).
