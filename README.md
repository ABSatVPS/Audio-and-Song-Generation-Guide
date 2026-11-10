# Generative Music and Audio Prompt Engineering

This repository is a structured knowledge base for prompting, conditioning, and
troubleshooting generative music and audio systems. It covers both practical
prompt construction and the model architectures that shape prompt behavior,
including diffusion and autoregressive approaches.

The material is intended for musicians, researchers, developers, and listeners
who want to make generation more controllable and understand why particular
prompt strategies work. Examples describe general techniques; exact syntax and
conditioning behavior vary between models and interfaces.

## Documentation modules

### Prompt engineering

- [Acoustic staging and anti-bleed](docs/prompt-engineering/acoustic-staging-anti-bleed.md):
  separate vocal, instrumental, and spatial instructions to reduce unwanted
  source overlap.
- [Temporal continuity](docs/prompt-engineering/temporal-continuity.md):
  maintain musical identity and section transitions across generated chunks.
- [Phonetics and pacing](docs/prompt-engineering/phonetics-and-pacing.md):
  shape syllable timing, sustained vowels, and breath placement in lyrics.
- [Style and gear proxies](docs/prompt-engineering/style-and-gear-proxies.md):
  express sound through era, instrumentation, production, and mix properties.

### Model architectures

- [Prompt rewriters and conditioning](docs/architectures/prompt-rewriters-and-conditioning.md):
  understand text rewriting and multi-stream semantic, textual, phonetic, and
  adaptive conditioning.
- [Attention and guidance](docs/architectures/attention-and-guidance.md):
  explore cross-attention, modality separation, and independently controlled
  lyric and style guidance.

### Reference

- [Troubleshooting index](docs/reference/troubleshooting-index.md):
  map common generation failures to prompt adjustments and architectural causes.

## Accessibility

This repository is optimized for screen-reader accessibility. Headings follow a
strict hierarchy, filenames are descriptive and kebab-case, and explanations
use plain text rather than visual ASCII diagrams or raw mathematical notation.
Examples are labeled in text so their meaning does not depend on visual layout.

## Contributing

Community contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md)
before submitting a change or an observation.

## License

Unless a file says otherwise, the documentation in this repository is made
available under the Creative Commons Attribution 4.0 International license
(CC BY 4.0). See [LICENSE](LICENSE) for the complete legal text. Contributions
are submitted under the same license unless the contributor clearly identifies
content that is not theirs to license.
