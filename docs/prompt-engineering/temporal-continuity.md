# Temporal Continuity

Chunked generation extends a composition by asking a model to continue from a
previous segment, often through an audio context window, a text prompt, or both.
The continuation must preserve identity while still making meaningful musical
progress. Useful anchors include tempo feel, tonal center, groove, instrumentation,
vocal identity, motif, and the current section's role.

## Build a continuity anchor

At each extension, repeat the minimum identity cues needed to orient the model.
Keep the wording stable for properties that should persist, and explicitly
describe what changes in the next segment. A concise anchor can state:

- the style and energy level;
- approximate tempo feel and meter, if known;
- tonal or harmonic character, if known;
- the recurring rhythm, hook, or melodic motif;
- the lead voice and core instrument roles;
- the current section and the intended transition.

Avoid adding many fresh descriptors to every extension. Changes in vocabulary
can be interpreted as changes in arrangement or style rather than harmless
paraphrases.

## Recursive tagging

Recursive tagging means carrying forward a small, consistent set of labels or
descriptors for the features that define the piece. It is a prompt-writing
practice, not a universal feature of model internals. Keep tags stable across
chunks, for example:

> Identity: mellow synth-pop, restrained pulse, warm analog-style bass, breathy
> lead vocal, recurring four-note descending hook.
>
> Current section: second verse, sparse accompaniment.
>
> Next section: build gently into the chorus; retain the hook and vocal tone.

If an interface uses section tags such as `[Verse]` and `[Chorus]`, follow its
documented syntax. Otherwise, use clear prose labels. Repeating every detail
can overload the prompt, so prioritize identity elements that drifted in
previous generations.

## Plan the transition

Describe the temporal change as a sequence: what remains, what enters, what
leaves, and where the energy moves. For example, retain the drum pattern,
introduce a counter-melody during the last two bars, then open the chorus with
fuller harmonies. If exact bar counts are unsupported, phrase them as
approximate intent rather than a guaranteed boundary.

For a seamless edit, preserve a short overlap or tail where the workflow allows
it. Align the continuation to a musically stable point, such as a downbeat,
phrase boundary, or held chord. Crossfade or edit after generation if needed;
prompting alone cannot ensure waveform-phase continuity or a click-free join.

## Common continuity failures

When the next chunk changes vocalist, groove, or instrumentation, restate the
relevant anchor and reduce conflicting alternatives. When it repeats the
previous section instead of developing, make the next event and its timing
more explicit. When a motif disappears, name the motif's contour or rhythmic
identity in plain language and state whether it should recur unchanged or be
transformed.

Use audio-context or continuation features when available, since a text
description cannot preserve every detail of a prior waveform. Evaluate several
extensions: continuity is probabilistic, and one successful sample does not
prove that a prompt is deterministic.
