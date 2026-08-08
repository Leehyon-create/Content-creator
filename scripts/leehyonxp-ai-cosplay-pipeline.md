# LeehyonXP — AI Cosplay Pipeline (fully AI, no filming)

Cosplay-style Shorts where you are the character, generated end to end. No camera, no
wig, no set. Your face comes from a trained Soul; your voice from a cloned voice model.

**Decision on record:** fully AI, per the creator. Earlier drafts of this document
recommended a hybrid (real reaction beats, AI everything else). That recommendation is
withdrawn — the pipeline below is built for the all-AI approach and the §4 constraints
are written to make it work rather than to argue against it.

---

## 1. Lock your identity first

Everything depends on one reusable, identity-faithful reference of your face.

**Path: Soul (trained), type `soul_2`.** 5–20 photos, ~10 min, identity-faithful, one
person per generation. Usable only with `soul_2` and `soul_cinema_studio`.

Keep an **Element** as a secondary for the one thing Soul can't do: two characters in
the same frame. Elements work with Nano Banana Pro / 2, GPT Image 2, Seedream 4.5 /
5 lite, Cinema Studio, Seedance 2.0 and Kling 3.0, and accept multiple subjects.

**Training photo spec** — the set assembled for this is 16 images: 5 window-daylight
studio shots (2 front, 2 three-quarter right, 1 right profile), 4 bathroom fronts and a
left profile, plus zoo / car / beach / neon shots for lighting variety. That is a good
set: both sides covered, multiple lighting conditions, dry styled hair.

**Never train on:** AI-generated images of yourself, screen photos, contact sheets,
group photos, or anything with the eyes or hairline covered. Eyes are the strongest
identity signal the model has; train on covered eyes and you get a Soul that only knows
half your face.

## 1b. Clone your voice — do this at the same time

In an all-AI pipeline your voice is the **only** unmediated thing you contribute, which
makes it the load-bearing authorship signal (see the roadmap, §2). Record a clean
sample, clone it once, and narrate every episode with it forever.

Record close to the mic in a soft room. Aim for peaks around −3 dBFS. For reference,
the Gojo test clip came in at −21.7 dBFS peak, roughly 20 dB too quiet — that is the
failure mode to avoid.

---

## 2. Model routing

| Job | Model |
|---|---|
| Cosplay stills of you as a character | `soul_2` |
| Cinematic stills, better light and atmosphere | `soul_cinema_studio` |
| Two-of-you in one frame | Nano Banana Pro / Seedream 4.5 + Elements |
| Still → motion | Cinema Studio Video, Seedance 2.0, Kling 3.0 |
| Environments and effects with no face in them | any image model — identity is irrelevant |
| Thumbnails and covers | `youtube-thumbnail-generator` workflow |

---

## 3. Per-episode pipeline

```
1. WRITE            Script first, always. Before a single generation.
2. HERO STILLS      One approved still per shot. 6-10 shots per Short.
3. ANIMATE          Still -> 3-5s clip. Two variants per shot, keep the better.
4. VO               Your cloned voice over the whole thing.
5. ASSEMBLE         Template project. Swap media only.
6. CAPTIONS         Burned in. Every video plays muted first.
7. DISCLOSE         AI label on YouTube and Instagram.
8. EXPORT           Clean, no watermark. Separate captions per platform.
```

**Prompt skeleton — identical every time, one variable changes:**

> `[SOUL] as [CHARACTER], [costume detail], [hair/eye detail], [expression],
> [framing], [lighting], [environment], vertical 9:16, shallow depth of field,
> cinematic`

Hold framing, lighting and lens language constant across a series. Change the character
and the costume. Nothing else. Consistency of prompt structure produces consistency of
output, and consistency of output is what makes a channel look like a channel.

---

## 4. Hard constraints (this is the section that decides whether it works)

Without a camera to fall back on, these stop being style preferences.

1. **No synced mouths.** AI lip-sync over 30 seconds is the biggest tell there is.
   All dialogue is voiceover; cut to the character *reacting* while the line plays.
2. **No close-up hands.** Still where generation fails. Frame them out.
3. **Shots of 2–4 seconds.** Long AI shots drift; short ones never get the chance.
   This is also King Chris's cut rhythm, so it costs nothing.
4. **Motion in, not motion across.** Push-ins, slow turns, hair and cloth drift. No
   walking, running, or fighting — complex limb articulation breaks.
5. **Approve the still, then animate.** Never generate video straight from text; you
   lose identity control at the one step where it matters most.
6. **Same head size across shots.** Reads as one person in one place, and hides drift.
7. **Vary the environment between episodes.** Templated backgrounds are exactly the
   signature the platforms' inauthentic-content filters look for.

## 4b. Sequence characters by how forgiving they are

This is the highest-leverage scheduling decision in the whole plan, and it is free.

Some characters hide the parts of a face that AI struggles to keep consistent. Lead
with those while your Soul is new, and save the demanding ones until you have a hundred
generations of experience with it.

| Difficulty | Characters | Why |
|---|---|---|
| **Easiest — start here** | Gojo (blindfold), Kakashi (mask), Zenitsu (eyes shut) | Covered eyes remove the hardest consistency problem *and* the lip-sync problem at once. Performance moves to the mouth and jaw. |
| **Moderate** | Sukuna, Itachi, Baki | Strong face markings or distinctive features anchor the generation. |
| **Hardest — save these** | Clean-faced characters with no mask or markings | Nothing hides drift. Attempt these only once the Soul is proven. |

Gojo is Ep.1 for three reasons: your existing post shows audience signal there, the
blindfold is the most forgiving cosplay in anime to generate, and you already know what
the costume should look like.

---

## 5. Series structure

**"WOULD YOU SURVIVE?"** — you cosplay the character whose power system the episode
judges, then deliver the verdict.

| Block | Time | Production |
|---|---|---|
| COLD OPEN | 0.0–2.0 | Soul still, hero pose, full costume. Slow push-in. Title card burns in. |
| THE RULE | 2.0–9.0 | Generated b-roll of the power system. VO over it. No faces needed. |
| THE PROBLEM | 9.0–19.0 | Soul stills, 2–4s each, escalating. Expression changes per beat. |
| THE VERDICT | 19.0–27.0 | Soul still, out of costume, plain background. Two-frame audio cut, then the ruling. |
| THE QUESTION | 27.0–31.0 | Same closing line every episode, to camera. |

**The verdict beat still needs to be visually distinct** even though it's now generated.
Drop the costume, flatten the lighting, plain background, tighter framing. The
contrast is what signals "this is the channel talking, not the character" — and in an
all-AI pipeline that signal has to be carried entirely by art direction.

---

## 6. Disclosure

Label every upload. YouTube: "altered or synthetic content" in the upload flow.
Instagram/Meta: the AI label. TikTok: the AI-generated label.

This matters more for an all-AI channel than a hybrid one — undisclosed synthetic media
at volume is the profile that gets throttled. Disclosure costs almost nothing in reach.
And in this niche the "how I made this" post reliably outperforms the thing it made, so
the process is content in its own right.

Cosplaying anime characters is entirely normal on these platforms. Keep it to
characters — don't generate your face onto a real person, or a real person's onto you.

---

## 7. Working configuration

**Identity: Element (not Soul).**

```
Element name : LeehyonXP
Element ID   : f7a91fd2-9e23-4b03-8436-3e458e17618e
References   : 5 studio daylight portraits (front / three-quarter / profile)
Usage        : embed <<<f7a91fd2-9e23-4b03-8436-3e458e17618e>>> in the prompt
Models       : nano_banana_2, seedream_v4_5, cinematic_studio_2_5,
               seedance_2, kling_3 (NOT soul_2 / soul_cinema_studio)
```

**Costs measured on this account:**

| Job | Credits |
|---|---|
| Image, 2 variants, 2K, Nano Banana | ~1.5 |
| Video (Seedance 2.0), per generation | 90–330 |

Images are effectively free; **video is the entire budget.** Generate stills
generously, approve them, and only then animate — an approved still costs 0.75 credits
to replace, an unapproved animation costs up to 330.

**Soul training is broken via MCP.** Seven attempts, generic error every time,
independent of image count (10 / 16 / 20) and of balance (68 and 1,068 credits).
Nothing was ever charged. Both the count and the credit theories were tested and
disproved. Retry the Soul later in the web app; the Element carries production
in the meantime.

**Known limitation:** the Higgsfield result CDNs are blocked by this session's egress
policy, so generated images cannot be reviewed from here. The creator must approve
likeness on every hero still before it is animated.

## 8. Status

- ✅ 22 reference photos uploaded
- ✅ Element `LeehyonXP` created
- ✅ Ep.1 cold-open hero still — 2 variants generated, awaiting likeness approval
- ⬜ Ep.1 remaining shots — pending hero approval
- ⬜ Voice clone
- ⛔ Soul training — blocked, see above
