---
name: baby-scene-english
description: Generate personalized baby English learning scenes from user-owned character images, licensed lesson text/audio, and an authorized caregiver voice. Build scene art, bilingual sentence cards, posters, playback, and a verified deployment without bundling private child data or copyrighted assets.
---

# Baby Scene English

Use this skill to turn a user's own baby reference image, lesson text, authorized audio, and caregiver voice into a reusable scene-based English learning product.

## Non-negotiable privacy and licensing

- Never include private child images, generated personal images, voice IDs, API keys, purchased teaching audio, or user data in the repository.
- Accept only user-owned or explicitly licensed lesson audio and voice references.
- Store personal inputs under `user-assets/` and keep them in `.gitignore`.
- Use TTS provider adapters; do not hard-code Fish Audio or any provider credential.

## Workflow

1. Read project docs and inspect the current repository; do not use chat history as the source of facts.
2. Import and hash the user's authorized audio; transcribe keywords, English, Chinese, and timestamps.
3. Use the user's character reference to generate a text-free 9:16 scene. Keep the character's identity, face, eyes, hands, feet, and natural posture consistent.
4. Render bilingual sentence cards and A4 posters deterministically in code. Default to a side-by-side layout that never covers the character's head, face, hands, feet, or key objects.
5. Integrate the single scene data source, playback, sentence seeking, scene library, calendar rotation, and downloads.
6. Run build, TypeScript, lint, tests, image dimensions, audio checks, and a thumbnail plus full-size visual QA.
7. Commit small changes.
8. Deploy to the selected production host. A local build is not completion.
9. Download production audio, scene art, and posters and compare HTTP status, dimensions, and SHA-256 with local artifacts. Only then mark the scene complete.

## Failure handling

Keep working when generation, build, upload, network, or deployment fails: inspect the error, retry or repair, and continue from the failed step. If the run's safe time budget expires, preserve evidence, report the exact blocked step, and do not advance the scene number or claim success.

## Default visual baseline

- Modern, clear picture-book watercolor; avoid an overly vintage color cast.
- Complete lower-half composition; no meaningless blank floor.
- Upright head and neck; eyes look at the same target; no tilted neck, squinting, or sideways gaze.
- Shoes and socks may coordinate with the user's outfit palette while keeping a consistent shoe structure.
- A4 posters are 2480×3508; English body text should remain large and readable on a phone, with Chinese directly paired below.

## Provider-neutral TTS

Implement a provider adapter with `voice_reference_id`, `text`, `format`, and `consent_record`. A Fish Audio adapter is optional and must read credentials from the environment. Do not ship or publish generated personal voice audio by default.

## Completion gate

The only successful state is: local artifacts pass QA, production deployment is READY, and production downloads pass HTTP, dimension, and SHA-256 verification.
