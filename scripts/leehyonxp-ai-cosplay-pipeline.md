# LeehyonXP — AI Cosplay Pipeline (your face, King Chris format)

How to produce cosplay-style Shorts where **you** are the character, using AI for the
costume, hair, environment and effects instead of buying wigs and building sets.

---

## 0. The one strategic warning, then I'll drop it

King Chris's cosplay videos work because a **real person commits to a bit**. The
comedy lives in timing, a held expression, a slow blink, the beat before a punchline.
Fully AI-generated cosplay gives you gorgeous *posters* — and posters don't have
timing. The most common way this format fails is that it looks incredible and gets
scrolled past, because nothing in it is performing.

So the pipeline below is built **hybrid-first**: your real performance, AI-generated
everything-else. You still cosplay whatever you want with no wig budget, but you keep
the thing that actually earns the follow. Where you want fully-synthetic shots, §5
tells you exactly which shots survive it and which don't.

---

## 1. Lock your identity first (do this before anything else)

Everything downstream depends on one reusable, identity-faithful reference of your
face. You have two paths, and they are not interchangeable.

| | **Soul** (trained) | **Element** (instant) |
|---|---|---|
| Setup | 5–20 photos, ~10 min training | One image, instant |
| Identity fidelity | Highest — this is the point | Good, not as locked |
| People per shot | **One only** | Multiple |
| Works with | `soul_2`, `soul_cinema_studio` | Nano Banana Pro / 2, GPT Image 2, Seedream 4.5 / 5 lite, Cinema Studio 2.5, Cinema Studio Video 2 / 3.0, Seedance 2.0, Kling 3.0 |
| Best for | Your recurring on-screen persona | Two-of-you-in-frame, props, environments |

**My recommendation: train a Soul, and keep an Element as backup.**

Reasoning: your entire growth problem is *recognisability* — a viewer has to know it's
you in half a second, across dozens of videos, on three platforms. That is exactly
what Soul is for, and drift in your own face is the one error the audience will
notice every single time. Train it once, use it forever.

The Element backup exists for one specific shot King Chris uses constantly: **two
characters in the same frame**. Soul can only do one person per generation. So the
moment you want you-as-Gojo arguing with you-as-Sukuna in a single shot, you need the
Element path — or you shoot it as two separate shots and cut between them, which is
what he actually does anyway.

**Photos to send me for training** (5–20, this quality bar matters a lot):
- Neutral expression, front-on, even lighting — 4 or 5 of these, they do the heavy lifting
- Three-quarter turn, both sides
- One profile each side
- 2–3 with different expressions (smile, flat, wide-eyed)
- Varied backgrounds and lighting; same face, different days
- **No** sunglasses, no heavy filters, no group photos, nothing blurry, no existing
  AI images of yourself

Send those and I'll run the training.

---

## 2. Model routing (what to use for what)

| Job | Model | Note |
|---|---|---|
| Cosplay stills, you as a character | `soul_2` | Your trained identity. Workhorse. |
| Cinematic cosplay stills | `soul_cinema_studio` | Better lighting/atmosphere, slower |
| Two-of-you in frame | Nano Banana Pro / Seedream 4.5 + Elements | Soul can't do multi-subject |
| Still → motion | Cinema Studio Video, Seedance 2.0, Kling 3.0 | Feed it your locked still |
| Thumbnails / covers | `youtube-thumbnail-generator` workflow | Purpose-built, don't hand-roll it |

---

## 3. Production pipeline (per video)

```
1. WRITE          Script first. Always. Before a single image.
2. LOCK IDENTITY  Soul trained once, reused forever.
3. GENERATE STILLS  One hero still per shot. ~6-10 shots per Short.
4. ANIMATE        Still → 3-5s clip per shot. Generate 2 variants, keep the better.
5. FILM YOURSELF  (hybrid) Real reaction shots, real timing, phone camera, locked tripod.
6. ASSEMBLE       Template project. Swap media only. Never rebuild the edit.
7. CAPTIONS + VO  Burned-in captions, your voice.
8. DISCLOSE       AI label on all three platforms. See §6.
9. EXPORT CLEAN   No watermarks. Three captions. Stagger the posts.
```

**Prompt template — reuse this exact skeleton for every cosplay still.** Consistency
of prompt structure is what produces consistency of output:

> `[SOUL] as [CHARACTER], [costume detail], [hair/eye detail], [expression],
> [framing: medium close-up / waist-up / wide], [lighting], [environment],
> vertical 9:16, shallow depth of field, cinematic`

Keep framing, lighting and lens language **identical** across a series. Change the
character and the costume. Nothing else.

---

## 4. Shot design rules for AI (these are hard constraints, not style advice)

Ignore these and the output looks AI in the bad way.

1. **No talking mouths.** AI lip-sync over 30 seconds is uncanny and it is the single
   biggest tell. Design every script so dialogue is **voiceover**, never a synced
   on-screen mouth. Cut to the character *reacting* while the line plays.
2. **No close-up hands.** Hands holding props are still where generation fails.
   Shoot real hands or crop them out.
3. **Short shots.** 2–4 seconds each. Long AI shots drift; short ones never get the
   chance. This also happens to be King Chris's cut rhythm, so it costs you nothing.
4. **Motion in, not motion across.** Slow push-ins, subtle turns, hair and cloth drift.
   Avoid walking, running, fighting, or anything with complex limb articulation.
5. **Hero still per shot.** Generate the still, approve it, *then* animate. Never
   generate video from text directly — you lose identity control.
6. **Same face size in frame.** Keep your head roughly the same size shot to shot.
   It reads as one person in one place, and it hides drift.

---

## 5. Which shots survive being fully synthetic

| Shot | Fully AI? | Why |
|---|---|---|
| Character reveal / hero pose | ✅ Yes | Static, styled, no performance needed. AI's best case. |
| Atmospheric b-roll, effects, environment | ✅ Yes | No face-acting involved. |
| Slow push-in on a character, VO over it | ✅ Yes | Motion is minimal, mouth is closed. |
| Reaction beat — the punchline lands | ❌ **Film this** | Timing is the joke. AI cannot do a beat. |
| Any line delivered on camera | ❌ **Film or VO it** | Lip-sync tell. |
| Two characters interacting | ⚠️ Split it | Two separate shots, cut between. Never one generated frame. |

**The 80/20:** AI does the costume reveals and the world. You film the four seconds
where the joke actually lands. That hybrid is cheaper *and* better than either extreme.

---

## 6. Disclosure — do this properly, it's cheap and the downside isn't

All three platforms require you to label realistic AI-generated or AI-altered content.
It's your own face, so there's no likeness problem — but the labelling requirement is
about the synthetic media itself, not about whose face it is.

- **YouTube:** tick "altered or synthetic content" in the upload flow.
- **TikTok:** apply the AI-generated content label.
- **Instagram / Meta:** apply the AI label.

Labelling costs you almost nothing in reach. Getting caught not labelling costs you
distribution or the video. And in a cosplay-AI niche, being open about the process is
itself content — the "how I made this" post routinely outperforms the thing it made.

**Also:** cosplaying anime characters is entirely normal on these platforms. Just keep
it to characters — don't generate your face onto a real person's body or vice versa,
which is a different thing with real rules attached.

---

## 7. How this changes the flagship series

This is the good part. **"WOULD YOU SURVIVE?" becomes a cosplay series**, and the two
ideas fit together better than either did alone:

> Each episode, **you cosplay the character** whose power system you're judging. You
> explain the system while dressed as its user, then deliver the verdict as yourself.

That single change gets you:
- **A face on the channel** — the recognisability that faceless content can never buy.
- **A reason for the AI to exist** — new costume every episode, zero wig budget.
- **The King Chris visual signature** — the costume change *is* the transition.
- **A repeatable prompt** — same framing, same lighting, one variable changes.
- **A cover frame that sells** — you in costume, every time, and your grid becomes a
  gallery of characters instead of a wall of text posts.

**Revised episode structure** (replaces the faceless one in `leehyonxp-batch-01`):

| Block | Time | Production |
|---|---|---|
| COLD OPEN | 0.0–2.0 | **AI still → slow push-in.** You in full costume, hero pose. Title card burns in. |
| THE RULE | 2.0–9.0 | **AI b-roll** of the power system. VO over it. No mouths. |
| THE PROBLEM | 9.0–19.0 | **AI stills, 2–4s each**, escalating. You in costume, changing expression per beat. |
| THE VERDICT | 19.0–27.0 | **Filmed — you, real, no costume.** Two-frame audio cut, then the ruling. This is the anchor: the AI is the bit, *you* are the channel. |
| THE QUESTION | 27.0–31.0 | **Filmed.** Same closing line every episode, straight to camera. |

Ep.1 is Gojo — you already have audience signal there from your existing post, and
the blindfold is the single most forgiving cosplay in anime to generate, because it
covers the hardest part of the face to keep consistent. Start there while your Soul is
still new.

---

## 8. What I need from you to start

1. **5–20 photos of your face** per the spec in §1. This is the only blocker.
2. Confirm **Soul** (my recommendation) or **Element** — §1 has the tradeoff.
3. Tell me if you'll film the verdict beats yourself, or want those synthetic too. I'll
   write the scripts differently depending on the answer.

Once the Soul is trained, the marginal cost of an episode drops to roughly one hour,
and the costume stops being a constraint on what you can make.
