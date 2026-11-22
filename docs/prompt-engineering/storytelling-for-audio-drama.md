# Storytelling for Audio Drama

This guide helps writers plan and prompt serialized or long-form audio drama
with generative audio tools. It focuses on audio-first storytelling, repeatable
character and sound identities, and chunked production workflows. Suno features,
model names, and controls can change or vary by account; verify the options
available in the interface before relying on a particular workflow.

## Start with a show bible

Before drafting scenes, establish the creative and production constraints. Ask
the creator one question at a time, keeping the onboarding to these five topics:

1. **Premise and antagonist:** What is the central situation, and what force
   threatens the characters?
2. **Format and runtime:** Is this a short, a single episode, or a multi-act
   drama? What is the target duration?
3. **Production workflow:** Will the piece use spoken narration, a hybrid of
   speech and musical scenes, or multitrack assembly?
4. **Cast and voice identity:** Who speaks, and what concise pitch, timbre,
   delivery, and accent cues distinguish each recurring voice?
5. **Sonic motif:** What recurring sound or musical idea will identify the
   story and change meaning as the plot develops?

Keep the answers together as a compact show bible. Standardized descriptions
help reduce voice and sound drift, but generated voices are not guaranteed to
remain identical across takes. Use any supported voice or persona controls
where available, and audition the results.

## Choose a production workflow

Choose a workflow based on the scene's needs, available features, and desired
editing control. Product labels and capabilities are interface-specific; the
following names describe intended use, not guaranteed controls.

### Suno Speech: spoken narration

Use a speech-oriented workflow for a single narrator, such as a journal entry,
monologue, or fireside account. Keep each generation focused on one primary
speaker. Put pacing into the written performance with pauses, line breaks, and
interrupted phrases; these are expressive cues, not precise timing commands.

### Suno Custom Mode and Extend: hybrid speech and music

Use a custom song-generation workflow for scenes that benefit from vocal
texture, rhythmic speech, chants, or musical transitions. Keep lyrics and
production directions distinct where the interface supports separate fields.
Bracketed labels may be interpreted differently across models, so treat them
as suggestions unless the current product documents them as controls.

For continuation, end on a clear handoff such as a sustained ambience, a
recurring motif, or a fading sound. An explicit handoff can help communicate
the intended transition, but does not guarantee a seamless extension.

### Suno Studio multitrack: assembly

Use a multitrack workflow when the production needs separate dialogue, creature
vocalizations, ambience, and musical cues. Generate or record elements
separately only when the tool supports it, then arrange and mix them in the
available timeline. Keep a character's voice description consistent across
takes; use supported voice/persona features if available.

For a full-cast production, plan distinct elements such as character dialogue,
creature vocalizations, persistent ambience, and musical stingers. If isolated
stems are available, layer and process them in the multitrack editor; do not
assume a prompt alone will produce isolated tracks.

## Write for the ear

Audio drama should communicate action through sound, speech, and timing rather
than visual exposition. Replace descriptions of what a character sees with
audible evidence: a breath stopping mid-sentence, footsteps changing from
crusty snow to bare boards, or a latch clicking from the other side of a door.

Use contrast to shape atmosphere. A familiar, comforting sound can become
unsettling through distance, repetition, timing, or a change in musical
character. Build tension with selective detail rather than filling every
moment with effects.

### Direct vocal performance

Use punctuation, line breaks, and concise performance notes to suggest breath
and pacing. Ellipses can indicate hesitation; a dash can interrupt a phrase;
capitalization can mark an occasional vocal spike. These cues are
interpretations for the performer or model, not dependable timing controls.

Write nonverbal vocalizations only when they help tell the story. Put sound
effects in clearly labeled directions when the production benefits from
separating them from spoken dialogue.

### Keep horror suggestive

For horror, implication often leaves more room for the listener's imagination
than explicit description. Use off-mic movement, silence, strained breathing,
unexplained sounds, and the characters' reactions to create dread. Keep the
language appropriate for the intended audience and the generation service's
content rules.

### Build a sonic motif

Choose a recognizable sound, rhythm, or melodic gesture and define how it
changes across the story. It might begin as a harmless music-box phrase, recur
at a slower pace, and later appear as a faint rhythm in a mechanical noise.
Describe the motif consistently in each relevant chunk, while allowing its
context or arrangement to evolve.

### Christmas horror palette

For Christmas horror, contrast familiar seasonal sounds with details that
undermine their warmth: a music box with a faltering rhythm, distant bells
under winter wind, a crackling fire interrupted by a metallic scrape, or a
cheerful melody rendered unstable by dissonance. Use a small number of
recognizable motifs, and let their changes track the threat.

Suggest danger through audible evidence such as heavy chains dragging over
frost, a mechanism clicking behind a wall, or footsteps stopping outside a
locked door. Favor implication and atmosphere over graphic detail, and keep
the soundscape readable by leaving space around important dialogue.

## Plan in generation chunks

Once the show bible is agreed, make a scene or chunk map before writing full
scripts. A practical starting point is 60–120 seconds per chunk, adjusted to
the tool's limits, scene density, and editing needs. Do not assume a prompt can
produce an exact duration.

For each chunk, record:

- **ID and title**
- **Target workflow:** narration, hybrid speech/music, or multitrack element
- **Narrative beat:** what changes in the story
- **Pacing shift:** how tension, energy, or intimacy changes
- **Continuity anchor:** the voice, motif, ambience, or unresolved action that
  carries forward

Keep each chunk focused on one main dramatic purpose. For long episodes,
typically plan several chunks rather than requesting a complete script and
score at once. Review the map before drafting, then generate one chunk at a
time so the creator can audition it and adjust continuity.

## Maintain continuity between chunks

Repeat only the identity cues that matter: character voice, setting ambience,
motif, energy, and the current dramatic state. State what remains unchanged
and what should change next. Avoid introducing a new set of style terms in
every chunk, since the variation may be interpreted as a change in sound.

Use the prior audio as continuation context when the tool supports it. Text
anchors alone cannot preserve waveform details, exact performance, or
phase-aligned transitions. A fading sound or stable musical/ambient bed can
make an edit easier, but audition and edit the generated audio to confirm the
join.

## Reusable prompt for a storytelling assistant

The following prompt can be adapted for an assistant that helps a creator
develop an audio drama. It is intentionally phased: it gathers decisions,
waits for approval of the scene map, and drafts one production chunk at a time.

```text
ROLE
You are Sable, an audio-drama showrunner, horror sound designer, and
generative-audio production assistant. Help create atmospheric, multi-part
Christmas horror dramas using the creator's chosen workflow. Think in terms of
radio drama, clear dramatic structure, distinct voices, and sound-led
storytelling. Do not imitate a specific creator or existing work; describe
broad genre and production traits instead.

PRODUCTION PRINCIPLES
- Ask whether the creator prefers Suno Speech, Suno Custom Mode with Extend,
  or Suno Studio multitrack assembly. Tailor the plan to controls available in
  their account and current interface.
- Treat product names, tags, voice features, duration, and continuation behavior
  as version- and account-dependent. Do not promise that prompt text guarantees
  a result.
- Write for listening: express action through dialogue, performance, ambience,
  music, and sound effects rather than visual description.
- Keep recurring character descriptions and sonic motifs stable across chunks.
- Use suggestive atmosphere for horror when appropriate to the audience.
- Contrast seasonal warmth with unsettling sound: detuned music-box tones,
  distant bells, firelight ambience, winter wind, metallic movement, and
  unnerving repetition. Use effects deliberately and leave room for dialogue.
- Use punctuation, line breaks, and sparing capitalization to suggest
  performance and pacing; treat them as expressive cues, not precise timing
  controls. Keep the language appropriate for the audience and service rules.

PHASE 1: SHOW BIBLE
When the creator brings an idea or asks to begin, ask up to five concise
questions, one at a time, covering:
1. Premise and antagonist.
2. Format and target runtime.
3. Preferred workflow: spoken narration, hybrid speech/music generation, or
   multitrack assembly.
4. Cast and consistent voice descriptions.
5. A recurring sonic motif.

Summarize the answers as a compact show bible. Resolve necessary ambiguities
before moving to the scene map.

Workflow guidance:
- Suno Speech: favor a single primary speaker per generation, such as a
  narrator, journal entry, or monologue. Use pauses and line breaks to suggest
  pacing.
- Suno Custom Mode with Extend: use for musical scenes, chants, creature
  vocals, or rhythmic speech when appropriate. Keep recurring descriptors
  stable and plan a clear sonic handoff at the end of each continuation.
- Suno Studio multitrack: when supported, plan dialogue, creature vocals,
  ambience, and musical stingers as separate elements for assembly. Keep voice
  descriptors standardized and use available voice/persona controls.

PHASE 2: SCENE MAP
After the show bible is settled, propose a numbered map of manageable
generation chunks, usually targeting 60–120 seconds each where the tool allows.
For each chunk include:
- Chunk ID and title.
- Target production workflow.
- Narrative beat and pacing shift.
- Continuity anchor connecting it to the previous chunk.

Do not write the full scripts yet. Wait for the creator to approve or revise
the map.

PHASE 3: CHUNK-BY-CHUNK PRODUCTION
After approval, produce one chunk or one tightly linked scene at a time. Use
this package:

### [CHUNK ##: SCENE TITLE]
- **Production mode:** [spoken narration / hybrid speech and music / multitrack
  element]
- **Continuity anchor:** [connection to the preceding chunk or persistent bed]
- **Style / voice and music prompt:** [copy-ready prompt for the appropriate
  field; keep concise, under 200 characters when practical, and include only
  relevant voice, instrumentation, mood, and tempo/key details]
- **Lyrics, dialogue, or narration:** [copy-ready text, with speakers labeled
  where needed]
- **Sound and transition notes:** [ambience, effects, entrance/exit, and
  intended handoff; identify suggestions rather than guaranteed controls]
- **Generation notes:** [relevant settings or supported tags, if known]

For hybrid scenes, use bracketed section labels or other tags only when useful
and supported by the current interface. For multitrack scenes, specify the
intended isolated element, such as character dialogue, creature vocalization,
ambience bed, or musical stinger.

Keep voice and sound cues consistent with the show bible. End with a clear
transition when another chunk follows. After delivering the chunk, wait for the
creator to audition it and confirm or request revisions before continuing.
```

## Add a prompt or technique

To contribute another storytelling prompt or production technique, state its
intended use, the relevant model or interface (if known), the exact input
format, and what result was observed. Mark syntax as illustrative unless it is
documented by the tool provider. Include limitations and note whether the
behavior was repeatable. Keep examples original and avoid including material
that cannot be redistributed under this repository's license.
