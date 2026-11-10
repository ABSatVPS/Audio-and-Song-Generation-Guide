# Phonetics and Pacing

Lyrics are both language and a sequence of sounds that must fit a musical
phrase. Prompt formatting can influence where a model places syllables,
stresses, consonants, and breaths. These methods are heuristics: tokenization,
pronunciation, and singing behavior differ across models.

## Syllable hyphens

Hyphens can suggest syllable boundaries in multisyllabic words or in a sung
phrase. Use them sparingly and preserve the intended spelling where possible.
For example, `ev-er-y` signals a three-part delivery more clearly than an
ambiguous run-on syllable sequence. A lyric model may instead read the hyphens
literally or alter its pronunciation, so compare the result with normal
spelling.

To guide rhythmic grouping, line breaks are often less intrusive:

> Every little light  
> rises with the tide

Use hyphens when the syllable split is important; use line breaks to suggest
phrase boundaries. Do not add a hyphen to every word.

## Sustained vowels

To request a held note, identify the vowel or word to sustain and give musical
context. An illustrative lyric might write `so-o-o` or say "hold the final
vowel of 'home' for the end of the bar." Repeated letters can be interpreted
as extra syllables or unusual spelling, so natural words plus a short delivery
instruction may be more reliable. If the interface has a duration or note
control, use that instead of relying only on spelling.

## Breath punctuation

Commas, periods, and line breaks can suggest pauses or breaths. Place
punctuation at intended phrase boundaries and avoid punctuation that conflicts
with the desired legato flow. For example:

> I follow the river,  
> then breathe before the dawn.

This may encourage a pause after "river," but it does not prescribe an exact
breath duration. Explicit phrases such as "brief breath between lines" can
reinforce the request.

## Stress and pacing

For difficult timing, state the intended delivery in ordinary language:
"short, evenly spaced syllables over the quick beat" or "leave a small pause
before the final word." Keep lines at a manageable length and avoid dense
clusters of consonants at fast tempos. If stress lands on the wrong syllable,
rewrite the line with simpler syntax or add a concise stress cue. Excessive
capitalization or phonetic spellings can cause unexpected emphasis.

## Iterate with the audio

Listen for swallowed consonants, unintended extra syllables, misplaced
emphasis, and missing breaths. Change one lyric or cue at a time. When the
model consistently mispronounces a name, provide a plain pronunciation hint
near that word or substitute a pronounceable equivalent if appropriate. Keep
phonetic cues distinct from content so that the model is less likely to sing
the instructions themselves.
