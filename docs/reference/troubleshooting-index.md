# Troubleshooting Index

Use this index to connect an audible failure with a focused prompt experiment
and a possible architectural explanation. The explanations are hypotheses,
not diagnoses: model behavior, interface controls, and random sampling can all
affect the result.

## Quick lookup

| Failure mode | Prompt adjustment to try | Possible architectural factor |
| --- | --- | --- |
| Vocal is masked by instruments | Describe the lead as foreground and close; reduce accompaniment density during sung phrases; make backing roles quieter or intermittent. | Text conditioning may express broad scene semantics more strongly than precise source balance; a single mix has no guaranteed stem isolation. |
| Backing vocal merges with the lead | Assign distinct roles, level, width, register, and phrase entrances; avoid an unspecified request for "more vocals." | The model may share vocal texture representations or lack independent spatial controls. |
| Lyrics are mispronounced or syllables collapse | Shorten the line, clarify syllable boundaries, use simple pronunciation guidance, and state the desired pacing. | G2P coverage, tokenizer behavior, and lyric-to-audio alignment may be limited. |
| Lyrics are ignored or reordered | Put lyrics in the designated lyric field if available, simplify style instructions, and test a shorter lyric passage. | A semantic style stream may dominate; the model may not have robust lyric alignment or a separate lyric condition. |
| Instrumentation or genre drifts between chunks | Repeat a concise stable identity anchor and state what remains unchanged before describing the transition. | The continuation may rely on a limited context window or text/audio conditioning may be weak. |
| A continuation repeats instead of developing | State the next section's role, the new event, and when it enters; preserve only the essential anchor details. | The model may favor local continuation of its audio context over a new structural instruction. |
| The mix is dense or muddy | Name source priority and reduce simultaneous parts; specify sparse accompaniment or gaps around the vocal. | A global text embedding may not encode detailed arrangement constraints reliably. |
| Reverb obscures consonants | Request a closer, drier lead with shorter ambience and keep long tails on supporting elements only. | Text descriptions may not map to per-source effects; the generator may create a shared acoustic scene. |
| Strong guidance sounds brittle or repetitive | Reduce the relevant guidance strength and use more concise, compatible conditions. | Excessive CFG can amplify condition-related artifacts or reduce output diversity. |
| Prompt additions cause unpredictable changes | Remove new descriptors, test one variable at a time, and review any prompt rewriter output. | Rewriting and multiple conditioning streams can alter more than the intended attribute. |

## A controlled iteration method

First describe the audible failure without guessing at its cause. Change one
prompt feature or one available setting, generate a small comparison set, and
record the result. Keep the original prompt and settings so that the effect
can be compared. If the issue persists, check whether the model offers
structured controls, audio context, or separate stems instead of relying on
natural-language text to provide exact engineering control.
