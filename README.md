![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/test/badge.svg) ![](../../workflows/fpga/badge.svg)

Team Memebers:
Sanjay Krishna A (23BEC0113)
Adarsh Somu Palaniappan (23BEC0155)
Jyotsna Pillai (23BEC0076)
Abishek Guru M (23BEC0187)

Overview:
This chip takes a fundamentally different approach: it eliminates the processor entirely. Instead,the heartbeat detection happens continuously using an event-driven digital circuit that activates only when a heartbeat arrives—roughly once per second at rest. The chip detects both AFib (irregular rhythm) and bradycardia/asystole (dangerously slow or absent heartbeats), delivering two critical cardiac warnings in a footprint of just 959 standard cells.

Conventional approaches waste power keeping a processor alive. This design consumes switching energy only when a heartbeat triggers detection. The chip recognizes irregular (AFib) and dangerously slow (bradycardia/asystole) rhythms in real time because the pattern recognition is physically embedded—not software-simulated.

What makes it different from other TT neural network submissions:

Computation embedded in silicon: Behavior emerges directly from circuit dynamics rather than software-style abstraction.
True LSM architecture: 8 LIF neurons with membrane potentials stored in flip-flops preserve activity across heartbeats.
Real temporal memory: A 1-bit recurrent feedback loop provides cross-beat memory (echo state behavior), enabling dynamic signal interpretation.
Stateful, non-lookup processing: Persistent neuron states capture ECG temporal patterns without relying on precomputed tables.
Compact, efficient reservoir: Rich dynamics achieved with minimal hardware—no large memory blocks or multipliers.
Bit-optimized weights: 3-bit 2’s complement weights with sign extension handled via wiring, eliminating extra logic.
Clinically grounded detection: Dual-window AND voting aligns with ESC 2020 criteria for sustained irregularity.
Full architecture walkthrough, clinical justification for every design decision, and training methodology in the docs.

---
- [Read the documentation for project](docs/info.md)

## What is Tiny Tapeout?

Tiny Tapeout is an educational project that aims to make it easier and cheaper than ever to get your digital and analog designs manufactured on a real chip.

To learn more and get started, visit https://tinytapeout.com.

## Set up your Verilog project

1. Add your Verilog files to the `src` folder.
2. Edit the [info.yaml](info.yaml) and update information about your project, paying special attention to the `source_files` and `top_module` properties. If you are upgrading an existing Tiny Tapeout project, check out our [online info.yaml migration tool](https://tinytapeout.github.io/tt-yaml-upgrade-tool/).
3. Edit [docs/info.md](docs/info.md) and add a description of your project.
4. Adapt the testbench to your design. See [test/README.md](test/README.md) for more information.

The GitHub action will automatically build the ASIC files using [LibreLane](https://www.zerotoasiccourse.com/terminology/librelane/).

## Enable GitHub actions to build the results page

- [Enabling GitHub Pages](https://tinytapeout.com/faq/#my-github-action-is-failing-on-the-pages-part)

## Resources

- [FAQ](https://tinytapeout.com/faq/)
- [Digital design lessons](https://tinytapeout.com/digital_design/)
- [Learn how semiconductors work](https://tinytapeout.com/siliwiz/)
- [Join the community](https://tinytapeout.com/discord)
- [Build your design locally](https://www.tinytapeout.com/guides/local-hardening/)

## What next?

- [Submit your design to the next shuttle](https://app.tinytapeout.com/).
- Edit [this README](README.md) and explain your design, how it works, and how to test it.
- Share your project on your social network of choice:
  - LinkedIn [#tinytapeout](https://www.linkedin.com/search/results/content/?keywords=%23tinytapeout) [@TinyTapeout](https://www.linkedin.com/company/100708654/)
  - Mastodon [#tinytapeout](https://chaos.social/tags/tinytapeout) [@matthewvenn](https://chaos.social/@matthewvenn)
  - X (formerly Twitter) [#tinytapeout](https://twitter.com/hashtag/tinytapeout) [@tinytapeout](https://twitter.com/tinytapeout)
  - Bluesky [@tinytapeout.com](https://bsky.app/profile/tinytapeout.com)
