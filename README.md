# Baby Scene English

An agent skill for building personalized bilingual baby-English scenes from user-owned assets.

This repository contains the workflow and provider-neutral interfaces only. It does not contain any child image, character artwork, purchased lesson audio, voice ID, API key, or personal data.

## Install

```bash
npx skills add YOUR_GITHUB_ACCOUNT/baby-scene-english --skill baby-scene-english
```

## Distribution

GitHub is the source of truth. After the repository is public, it can also be listed on skills.sh for discovery. For OpenClaw users, publish a separate ClawHub listing that points back to this repository; never bundle private family assets or purchased audio.

It can also be installed manually by placing the skill directory containing `SKILL.md` in the agent's skills directory.

## Bring your own assets

Put authorized inputs in `user-assets/` (which must remain gitignored):

- a baby reference image;
- lesson text, Chinese translations, and timestamps;
- user-owned or licensed audio;
- an authorized caregiver voice reference or provider voice ID.

The skill generates the scene art, deterministic bilingual cards, A4 posters, playback integration, and a release verification report. A local build alone is never considered released; production deployment and online hash verification are required.

## License

MIT for the workflow instructions and example schemas in this repository. Provider SDKs, model weights, fonts, audio, images, and generated personal outputs retain their own licenses.
