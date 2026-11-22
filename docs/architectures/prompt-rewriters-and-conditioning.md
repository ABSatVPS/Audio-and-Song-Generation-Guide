# Prompt Rewriters and Conditioning

Generative music systems may transform a user's text before generation and
may condition the generator on several kinds of input. The exact pipeline is
model-specific. A useful mental model is that text can be rewritten or encoded
into one or more representations, then combined with audio context, timing,
or structural controls during generation.

## Prompt rewriting

A prompt rewriter can expand short descriptions, normalize wording, infer
arrangement details, or convert an instruction into model-preferred language.
This can improve consistency but may also introduce unwanted instruments,
moods, or structural assumptions. If the output diverges from the request,
inspect any exposed rewritten prompt, shorten conflicting language, and state
non-negotiable constraints explicitly.

Rewriters are not necessarily transparent or deterministic. A change in the
user-facing prompt may affect the rewritten text as well as the generator's
direct text conditioning.

## Multiple conditioning streams

Some systems can combine information from more than one representation:

- **Text encoders such as T5:** encode natural-language descriptions into
  contextual token representations. A model may use these to represent
  detailed instructions or lyrics.
- **Audio-text encoders such as CLAP:** produce embeddings intended to align
  text and audio concepts. They can support broad semantic or style matching,
  but alignment does not imply precise control of every musical detail.
- **Grapheme-to-phoneme processing (G2P):** maps written text to a phonetic
  sequence. It can help a singing system align lyric syllables and sounds,
  although pronunciation dictionaries and language coverage vary.
- **Adaptive layer normalization (AdaLN):** modulates a network's activations
  using conditioning information, often through learned scale and shift
  parameters. It is an architectural mechanism, not a prompt syntax.

These are examples of component families, not a claim that every music model
uses them together. Conditioning streams may be fused, routed to different
layers, or used only in particular generation stages.

## Practical implications

Different representations can emphasize different properties. A semantic
audio-text embedding may respond strongly to broad genre or instrumentation;
a contextual language embedding may retain relationships in a longer
description; and a phonetic stream may prioritize how lyrics sound. These
roles overlap and are not guarantees.

When one property dominates, simplify the prompt and separate goals into
explicit clauses. Keep the lyric text distinct from production instructions
when the interface supports separate fields. If the system exposes separate
conditioning strengths, adjust one at a time and listen for changes in
semantic adherence, lyric intelligibility, and audio quality.

## Diffusion and autoregressive systems

In audio diffusion, conditioning can guide a denoising process from noise
toward a waveform or audio representation. In autoregressive systems, context
and conditioning influence the prediction of subsequent tokens or audio
frames. Both families can support text and audio context, but their behavior
depends on the trained model and inference implementation. Prompt wording
alone does not reveal the full conditioning path.
