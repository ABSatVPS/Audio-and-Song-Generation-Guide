# Attention and Guidance

Attention and guidance are mechanisms that influence how a generator uses
conditioning information. Their names are used differently across systems,
so the discussion here describes common design patterns rather than claiming
that every audio model implements them identically.

## Cross-attention

Cross-attention lets a model's current audio representation use information
from another sequence, such as text embeddings. At a high level, the model
compares its current state with conditioning tokens and combines the most
relevant information. This can let different words influence different
moments or layers, but attention is not a literal word-to-sound alignment
guarantee.

## Decoupled conditioning

A decoupled design keeps distinct information sources or objectives separate
for some part of generation. For example, style text and lyric content may be
encoded through different paths, then combined at selected layers. Separation
can reduce interference: style cues can describe instrumentation and mood,
while lyric cues describe the words and their order.

The term "decoupled cross-attention" is not a single universal architecture.
Implementations may use separate attention blocks, separate encoders, masks,
or other routing. Users should rely on model documentation for the controls
actually available.

## Classifier-free guidance

Classifier-free guidance (CFG) compares a prediction made with conditioning
against a prediction made with reduced or absent conditioning, then increases
the influence of their difference. In general, stronger guidance can increase
adherence to the condition, but excessive strength may reduce variation,
distort audio, or overemphasize a narrow interpretation. The useful range is
model- and task-dependent.

## Separate lyric and style guidance

Some systems expose independent guidance strengths for different conditioning
streams, such as lyrics and style. This allows targeted tuning:

- If the words are omitted or reordered, modestly increase lyric influence or
  simplify competing instructions.
- If the arrangement ignores the style description, adjust style influence
  while checking that the mix remains natural.
- If the output becomes harsh, repetitive, or less coherent at higher
  strengths, reduce the setting and make the text more specific instead.

Separate controls are meaningful only when the model actually implements
separate streams. A single CFG value does not imply independent lyric and
style control, and changing a UI slider may affect multiple model components.
Change one exposed setting at a time and compare several samples at matched
seeds or conditions when the workflow permits.

## Interpreting failures

Poor adherence may result from ambiguous text, conflicting conditions,
training-data limits, tokenization, or inference settings rather than an
attention defect. Use short controlled prompts to isolate a failure. Treat
architectural explanations as hypotheses unless the model's technical
documentation or experiments support them.
