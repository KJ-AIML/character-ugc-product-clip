# character-ugc-product-clip

An agent skill that turns **one character sheet + one real product** into a ready-to-produce 9:16 UGC-style short clip pack for TikTok, Shopee Video and YouTube Shorts. It is written for Thai-market clips, but it works for any language.

Give it a recurring AI character and a product, and it returns:

1. Three hooks, with the best one picked and the reason
2. A full voiceover script sized to the clip length
3. A shot list with timing, actions, camera and on-screen text
4. English image/video prompts that keep the character's face consistent
5. SRT subtitles
6. Music and SFX timeline
7. CTA
8. Captions and hashtags for each platform
9. Edit notes for CapCut / Remotion

It also has guardrails: claims come only from the FACTS you give, the real product photo is used instead of redrawn packaging, wardrobe stays modest, age notices stay on screen for restricted categories, and the pack never invents file paths or library components.

## Use

Copy `skills/character-ugc-product-clip/SKILL.md` into your agent's skills folder (Cursor, Claude Code, or any agent that reads `SKILL.md`). You can also paste its contents into ChatGPT, Gemini or another LLM, then fill in the INPUT block.

```
CHARACTER = name + character sheet image
PRODUCT = product name
PRODUCT_IMAGE = real product photo
FACTS = the only claims allowed
PLATFORM = TikTok / Shopee Video / YouTube Shorts
LENGTH = 30s, 9:16
VOICE / TONE / CONCEPT / SCENE = ...
```

## License

MIT
