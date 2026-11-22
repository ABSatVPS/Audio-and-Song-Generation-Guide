# Acoustic Staging and Anti-Bleed

Acoustic staging describes where sources sit in the mix, how they relate in
level and space, and which sources should remain distinct. "Bleed" in a
generated mix usually means unwanted overlap or leakage between perceptual
roles, such as backing vocals sounding like a lead double, a synth masking the
vocal, or room ambience obscuring a dry close sound.

Prompt instructions can bias a model toward a clearer arrangement, but they
are not equivalent to multitrack routing or source separation. A single stereo
render may still contain coupled sources even when the prompt names separate
roles.

## Describe roles before effects

Name each important source and its musical job before giving mix instructions.
Use a stable vocabulary for foreground, support, and ambience. For example,
distinguish a centered lead vocal from wide backing harmonies, or a dry kick
from a reverberant pad. Keep the requested arrangement physically plausible:
too many simultaneous foreground elements compete for attention.

Useful dimensions include:

- **Level and priority:** lead, foreground, supporting, background, or subtle.
- **Pan and width:** centered, slightly left or right, narrow, or wide stereo.
- **Distance:** close and direct, mid-distance, or far and ambient.
- **Space:** dry, short room, plate-like tail, or long diffuse reverb.
- **Frequency role:** low foundation, midrange body, high transient, or airy
  texture. These descriptions guide balance; they do not guarantee filtering.
- **Timing:** tight and aligned, loose, staggered, or call-and-response.

## Separate competing sources

Give sources different roles, registers, times, or spatial qualities. If a
lead vocal and a synth both need the midrange, make one sparse under the words
or have it answer in the gaps. If a backing vocal is meant to support rather
than double the lead, specify harmony, lower level, wider placement, or
intermittent phrases. Requests such as "no bleed" alone are ambiguous; describe
the desired positive mix and what should not happen.

For instance, an illustrative prompt fragment might say:

> Keep one close, centered lead vocal in front. Place soft two-part backing
> harmonies wider and lower, entering only at the ends of phrases. Keep the
> midrange accompaniment sparse while the lead sings; no constant unison
> doubling.

The terms in this example are natural-language guidance, not a universal
control syntax. A model may interpret negative instructions inconsistently.

## Syntax patterns and limitations

Some interfaces interpret labels such as `[Lead vocal]` or `[Backing vocals]`
as useful text cues; others treat the brackets as ordinary tokens. A
model-agnostic example is:

> Lead: close, dry, centered, clearly intelligible.
>
> Backing: quiet, wide harmonies in phrase endings.
>
> Instrumental: leave space around the vocal; keep pads diffuse and behind it.

If a model supports explicit stem, channel, or spatial controls, prefer those
controls for strict separation. Prompt text cannot reliably force independent
stems, exact panning, phase alignment, or the absence of source leakage.

## Diagnose the result

Listen to the whole mix and, if available, solo the stems. Check whether
masking is caused by role overlap, sustained notes, reverberation, or dense
arrangement rather than just loudness. Revise one dimension at a time: reduce
simultaneous density, shorten ambience, move the supporting part out of the
lead's register, or restrict its entrances. Iteration makes it easier to tell
which instruction helped.
