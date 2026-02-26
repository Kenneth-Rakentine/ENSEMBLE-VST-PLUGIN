# ENSEMBLE
<br>
[![Logo](2026logo.png)] <br>
**A spectral texture forge that transforms live audio into evolving, Penderecki-inspired orchestral swarms.**

ENSEMBLE captures your audio into a circular buffer and continuously re-reads it through 8 voices with golden-ratio panning, incommensurate LFOs, and dual MASS/DUST grain layers — producing dense, breathing string-like textures from any input.

---

## Installation

Download the latest release for your platform from the [Releases](../../releases) page.

**Windows:** Copy the `ENSEMBLE.vst3` folder to `C:\Program Files\Common Files\VST3\`

**macOS:** Copy `ENSEMBLE.vst3` to `~/Library/Audio/Plug-Ins/VST3/`

Rescan plugins in your DAW. ENSEMBLE appears as an audio effect.

---

## How to Use

1. Place ENSEMBLE on an **effects/send track** or your **master bus** — it processes incoming audio, it's not an instrument.
2. Feed audio into it — synths, guitar, vocals, samples, whatever. Play sounds one at a time and let the texture build between each.
3. Dial in the parameters as it plays back to you. Start with defaults and experiment.
4. Press **CLEAR** to wipe the buffer and start fresh whenever you want a clean slate.

## Tips

- Feed sounds in **one by one** in real time. Let each sound layer into the texture before adding the next.
- **Melodic and harmonic sources** work best — pads, guitars, vocals, strings, textural samples. Drums and percussion tend to produce harsh results.
- **PERSIST** controls how long audio stays in the buffer. Higher values build denser, more layered textures over time.
- **BLEND** shifts between pointillist stippling (left) and smeared bowing (right). Try automating it slowly.
- **EVOLVE** controls how much the texture moves on its own. High values create constant internal motion without any input.
- **DRY** mixes your original signal back in. Keep it low for pure texture, or bring it up for parallel processing.
- The **12-band EQ** is great for carving out mud or taming harsh frequencies in the texture.
- The **bandpass filter** (toggle on, then sweep the frequency) can isolate a specific range of the texture for focused, narrow sounds.

---

## Building from Source

See [BUILD.md](BUILD.md) for full instructions. Requires JUCE 8.0.4 and a C++ compiler (Visual Studio 2022+ on Windows, Xcode on macOS).
