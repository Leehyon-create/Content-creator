# EP.1 — CURSED ENERGY (Gojo) · Build Sheet

**"WOULD YOU SURVIVE?" Ep.1** · 31s · 9:16 · fully AI
Element: `LeehyonXP` — `f7a91fd2-9e23-4b03-8436-3e458e17618e`
All stills: 1536×2752, 2K, Nano Banana. Total spend so far: **~6 credits.**

---

## Generated shots

| # | Job ID | Content | Use |
|---|---|---|---|
| 0 | `e2b05f08-c1f2-4e22-95a6-e56fe1c11ed8` | Gojo hero, smirk, blue haze — **variant A** | Cold open |
| 1 | `f68900d8-e5c8-4397-9a39-b18471ac1c3a` | Gojo hero, smirk, blue haze — **variant B** | Cold open (alt) |
| 2 | `a77247bd-0da3-4c78-ade3-bfd632ecb0e6` | Cursed energy, abstract, no face | The Rule |
| 3 | `9563497a-2590-4d26-89e7-a0872d4e488f` | Night street, shadow forming on wall | The Rule / Problem 1 |
| 4 | `2dc576a3-d787-4d71-8e2f-bbbf27a6da11` | Gojo, flat serious mouth, head turned | Problem 1 |
| 5 | `b4871f2b-b134-4c02-bd4d-2ed9af04c539` | Gojo, chest-up, energy at shoulders | Problem 2 |
| 6 | `d4b9714f-d51d-4cb0-a57e-bcd2eceef41a` | Him, no costume, neutral, grey seamless | Verdict |
| 7 | `9b8a568a-6785-4d33-bf0e-f69d795275a3` | Him, no costume, slight smile, grey seamless | The Question |

Shots 6 and 7 are deliberately flat-lit on plain grey against the hard-lit black of the
costume shots. That contrast is what tells the viewer "the channel is talking now,
not the character" — in an all-AI pipeline it's the only signal carrying that job.

---

## Timeline

| Time | Shot | Motion | VO | On-screen |
|---|---|---|---|---|
| 0.0–2.0 | 0 (or 1) | Slow push-in 5% | "Cursed energy. Episode one." | **WOULD YOU SURVIVE?** / *Ep.1 — Cursed Energy* |
| 2.0–5.0 | 2 | Slow drift | "It runs on negative emotion. Fear, stress, hate — it all becomes fuel." | "negative emotion = fuel" |
| 5.0–9.0 | 3 | Push-in 8% | "Which means the fuel is already inside you. And it's already leaking." | — |
| 9.0–13.0 | 4 | Hold, 3% push | "Problem one. You can't see them. Non-sorcerers can't perceive curses at all." | "you can't see them 💀" |
| 13.0–19.0 | 5 | Slow push-in 10% | "You will not be attacked. You'll be *removed* — and everyone will call it an accident." | "they call it an accident" |
| 19.0–21.0 | 5 frozen → black | Freeze, hard cut | *(silence — 2 frames of full audio cut)* | — |
| 21.0–27.0 | 6 | Static, no motion | "Verdict: you survive if you are *boring*. Cursed energy pools around strong emotion. Panic, and you light yourself up like a flare." | **"stay calm or die"** |
| 27.0–31.0 | 7 | Static | "So — would you survive? Tell me, and I'll tell you if you're wrong." | **"would you survive?"** |

**Hard cut to black at 31.0, mid-beat.** No outro, no logo, no "like and subscribe."

### Non-negotiables
- **Two-frame full audio cut before the verdict** at 19.0. Every episode. It becomes the sound of the series.
- **Burned-in captions**, 3–6 words at a time, one line, centre frame, bold sans with a hard black stroke.
- **The closing line never changes.** Same words, same delivery, every episode.

---

## Voiceover

Record close to the mic, peaks around **−3 dBFS**. Measured, certain, unhurried — never
hyped. Certainty is the voice of the series.

> Cursed energy. Episode one.
>
> It runs on negative emotion. Fear, stress, hate — it all becomes fuel.
> Which means the fuel is already inside you. And it's already leaking.
>
> Problem one. You can't see them. Non-sorcerers can't perceive curses at all.
> You will not be attacked. You'll be removed — and everyone will call it an accident.
>
> *(beat)*
>
> Verdict: you survive if you are boring. Cursed energy pools around strong emotion.
> Panic, and you light yourself up like a flare.
>
> So — would you survive? Tell me, and I'll tell you if you're wrong.

~85 words. At 31 seconds that's a deliberate pace with room for the silences. Don't rush it.

---

## Publishing

**YouTube Shorts**
Title: `Would You Survive Cursed Energy? | Jujutsu Kaisen | Ep.1`
Tick **"altered or synthetic content"** in the upload flow.

**Instagram Reels**
Caption: `would you survive cursed energy? be honest 💀`
Tags: `#jujutsukaisen #anime #powerscaling #gojo #jjk`
Cover frame: shot 0. Apply the **AI label**.

**TikTok** (test bed, keep it running)
Same as IG. Apply the **AI-generated label**.

**Pinned comment, all three — post it the moment the video goes live:**
> the calm ones survive. so most of you are gone

---

## Assembly in DaVinci

Six clips, 5s each, all silent and 9:16. Trim each to the timeline durations above.

| Timeline | Use clip | Trim to |
|---|---|---|
| 0.0–2.0 | A upscaled (`b09230bf…`) | 2.0s |
| 2.0–5.0 | B (`25721b12…`) | 3.0s |
| 5.0–9.0 | C (`243cadeb…`) | 4.0s |
| 9.0–13.0 | D upscaled (`fc51c3de…`) | 4.0s |
| 13.0–19.0 | E upscaled (`869e9e40…`) | 5.0s + freeze to 6.0s |
| 19.0–21.0 | E last frame, frozen | 2.0s |
| 21.0–27.0 | still 6 (`d4b9714f…`), static | 6.0s |
| 27.0–31.0 | F (`8bb4442f…`) | 4.0s |

1. New 9:16 timeline, **1080×1920, 30fps**.
2. Drop clips in the order above and trim. The generated push-ins replace the manual
   Transform keyframes — don't add zoom on top of them.
3. Layer the VO. Music bed low, ducked under the voice.
4. **Kill all audio for 2 frames at 19.0.**
5. Burn the captions. Same font and position for every episode from here on.
6. Export clean — **no watermark** on the Reels and Shorts versions.

**Save this timeline as a template.** From Ep.2 you only swap media.

**Save this timeline as a template.** From Ep.2 you only swap media; you never rebuild
the edit. That's what makes 4 episodes a week possible.

---

## Animated clips

Likeness approved by the creator on the blindfold shots and on shot 7.
All clips: Seedance 2.0, 5s, 1080p, `mode=std`, silent (`generate_audio=false`) —
VO and music are laid over them in the edit.

| Clip | Video job ID | From still | Model | Motion |
|---|---|---|---|---|
| A | `1651db7c-7391-41ca-b62b-359c79c8fad3` | 0 | Kling 3.0 | Slow push-in, hair drift, haze |
| B | `25721b12-39cc-43ac-81fc-f8177b4f475f` | 2 | Seedance 2.0 | Energy tendrils coiling in place |
| C | `243cadeb-0e0b-4eda-ba54-28697bacd9f7` | 3 | Seedance 2.0 | Push-in, shadow grows on the wall |
| D | `4bc58efe-5721-4eec-9bb5-a69b4d809db4` | 4 | Kling 3.0 | Head settle, near-static |
| E | `f2851eb3-4d39-41d9-ae7e-1eb2460fcc4d` | 5 | Kling 3.0 | Push-in, glow pulses at shoulders |
| F | `8bb4442f-a12b-460d-9872-eb3c5e4192a7` | 7 | Seedance 2.0 | One slow blink, faint breathing |

**Upscales of the three Kling clips** (720×1280 → 1080×1920, ByteDance, `aigc` preset,
30fps). Use these in the edit, not the originals:

| Source clip | Upscale job ID |
|---|---|
| A | `b09230bf-97b8-4033-be2c-eb54a3999bf6` |
| D | `fc51c3de-3138-4e03-92bb-bdae6a93afe2` |
| E | `869e9e40-7269-4f95-840d-0c7794668476` |

### The blindfold / video-moderation problem — important for every future episode

**Seedance 2.0 rejected every blindfold clip and accepted every non-blindfold one.**
Five separate failures across two prompt rewrites; the bare-face clip passed first
time. Kling 3.0 then accepted all three blindfolded shots unchanged.

This inverts part of the plan. The blindfold is the *best* costume for image
consistency — covered eyes remove both the identity-drift and the lip-sync problem —
but it is the *worst* for video moderation, which reads it as restraint imagery.

**Rule going forward:** route covered-eye and mask characters (Gojo, Kakashi,
Zenitsu) to **Kling 3.0**; everything else can use Seedance 2.0. Kling is also
6× cheaper (7.5 vs 45 credits per 5s clip) but caps at 720p in `std` mode, so budget
an upscale pass on top.

Still-image moderation has the same bias but milder: "tight close-up on the lower half
of the face", "low angle looking up" and "knowing half-smile" were all rejected, while
"medium close-up" and "calm neutral mouth" passed with the identical costume.

Every prompt specifies **mouth closed, no talking** — the clips must never appear to
speak, because the VO is separate and any lip movement reads as broken sync.

**Alternate bare-face stills** (generated before the creator confirmed shot 7 was fine;
kept as options): `aeab8838-6f64-4823-8349-8049d021233d` (Nano Banana, neutral),
`8591cae6-f550-46d0-8ce9-4e932b534053` (Seedream 4.5, neutral),
`722491e8-0e01-4ad8-8caf-63731184eb7f` (Nano Banana, slight smile).

### Corrected costs

Earlier estimates were wrong and are superseded. Measured on this account:

| Job | Credits |
|---|---|
| Image, 2 variants, 2K | ~1.5 |
| Video, 5s, 1080p, Seedance 2.0 std | 45 |
| Video, 5s, 720p, Seedance 2.0 fast | 17.5 |
| Video, 5s, Seedance 2.5 (text-to-video only) | 32.5 |
| **Video, 5s, Kling 3.0 std (720p)** | **7.5** |

The 90–330 figures in the account's older transaction history were longer or
higher-tier jobs, not the per-clip rate for this workflow.

**Ep.1 actual: 1,068 → 889 credits before the upscales — ~179 spent**, including six
failed Seedance jobs that were not charged. At Kling rates a full episode costs well
under 100 credits, so the ~889 remaining is roughly **9 more episodes**.

**Seedance 2.5 will not accept a start image** — it is text-to-video only and returns a
422. Use `seedance_2_0` for image-to-video; it declares `start_image` and `end_image`.

## Outstanding

- **Voice clone.** Not started. Do it before Ep.2 so the series is consistent early.
- **Assembly.** Must be done in DaVinci — the result CDN is blocked from the agent
  session, so clips cannot be pulled down and cut here.
