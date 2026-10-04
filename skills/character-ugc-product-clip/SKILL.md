---
name: character-ugc-product-clip
description: >-
  Use when the user wants a short vertical UGC-style product clip (TikTok /
  Shopee Video / YouTube Shorts) starring a recurring AI character from a
  character sheet, and needs the full production pack: hooks, Thai voiceover,
  shot list, image/video prompts, SRT, music/SFX, CTA, captions and edit notes.
---
# Character UGC product clip (production pack)

Turns one character sheet + one real product into a ready-to-produce 9:16 short clip pack. Output is in Thai unless the user asks otherwise; image/video prompts are in English.

## 1. Collect the INPUT
Ask only for what is missing; use sensible defaults for the rest.

```
CHARACTER = name + character sheet image (face reference)
  appearance: age, hair, accessories (e.g. glasses, bow), outfit, expression, personality
PRODUCT = full product name
PRODUCT_IMAGE = real product photo (never redraw the packaging)
TAGLINE = the brand's own line, if any
FACTS = the ONLY claims allowed (copy from the product listing/pack)
TARGET = who it is for (add 20+/18+ if the category is age-restricted)
PLATFORM = TikTok / Shopee Video / YouTube Shorts
LENGTH = 30s (default), 9:16
VOICE = gender, age, energy, pace
TONE = e.g. funny, cute, confident
CONCEPT = optional angle (e.g. "fake food review that twists into the product")
SCENE = main set, colour-matched to the product photo
```

## 2. Fixed RULES (always apply)
- Same face, hair, accessories and outfit in every shot, taken from the character sheet. Repeat the full character description in every prompt.
- Modest wardrobe as on the sheet; never add off-shoulder, revealing or suggestive styling.
- Never invent claims, numbers, reviews or results outside FACTS. If the product has a scent/flavour, describe it exactly as FACTS words it.
- Real product photo only; composite it in editing (overlay/tracking). Never generate the packaging.
- For sensitive or age-restricted categories: no suggestive poses, winks, sniffing or innuendo; mention use only indirectly and politely; keep an age notice on screen for the WHOLE clip, not just the end.
- Respect the platform's ad rules; avoid words that commonly get filtered.

## 3. Word budget (check before writing)
Thai voiceover runs about 3 words (~8–10 syllables) per second. A 30s clip fits roughly 75–90 Thai words including pauses. Put long specs (standards, measurements, certifications) on screen as text instead of in the voiceover. Make each shot's voiceover fit its time slot.

## 4. OUTPUT (all 9 sections)
1. **HOOK** – 3 options (≤3s each), pick the best with a short reason.
2. **VOICEOVER** – full Thai script fitting LENGTH, `/` marks pauses, plus one line of voice direction.
3. **SHOT LIST** – table: shot | time | visual (character / real product / B-roll) | character action & expression | camera | on-screen text (≤6 words) | voiceover for that slot. Slot times must add up to LENGTH.
4. **IMAGE/VIDEO PROMPTS** (English) – one character base prompt, then one prompt per character shot that includes the full base text, scene, action, `9:16 vertical, photorealistic, no text in image`, plus one shared negative prompt (different face, different hairstyle, missing accessories, different clothes, revealing outfit, text, watermark, blurry, plus any category-specific bans).
5. **SUBTITLES** – SRT, short lines, timed to the voiceover; include the age notice if required.
6. **MUSIC & SFX** – genre, BPM, and a timestamped SFX list.
7. **CTA** – final voiceover line + final-frame text pointing to the cart/link (mention limited stock only if FACTS says so).
8. **CAPTION + HASHTAGS** – one version per platform; avoid filtered words.
9. **EDIT NOTES** – CapCut steps (ratio, fonts, overlay/tracking of the real product, caption styling, age notice placement). If Remotion is mentioned, use only real APIs (`<Composition>`, `<Sequence>`, `<Img>`, `<Audio>`, `staticFile()`, `spring()`, `interpolate()`); custom elements like arrows or cart icons must be written as your own components, never presented as built-ins. Never reference file paths that don't exist on the user's machine; use placeholders like `product.png`.

## 5. Self-check before sending
- Voiceover fits the word budget and every slot.
- Every claim traces back to FACTS.
- The character description is identical in every prompt.
- Nothing suggestive in wardrobe, actions or wording; the age notice is on screen throughout when needed.
- No invented file paths or fake library components.

## Production notes (when the user goes past the pack)
- Most video models' native speech is English/Chinese only. For Thai, generate the voice with a Thai TTS and lip-sync it afterwards, or run the voiceover over shots where the mouth isn't the focus.
- Manual testing: a subscription tool with multi-image character references (e.g. Kling). Automation: a pay-per-second video API (e.g. fal.ai) + TTS + Remotion/ffmpeg assembly. Check current prices before recommending.
- Don't automate consumer web UIs (Meta AI etc.) with bots; it breaks their terms and is fragile.
