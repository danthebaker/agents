---
name: vehicle-video-clip-prompt
description: Turns one approved storyboard section (its photo, scene title, and camera direction) into a single clean text-to-video generation prompt for Google Veo. Encodes the cinematography contract for AI vehicle video — smooth subtle camera motion, keep the real vehicle unchanged, no invented text/badges/people — and a negative prompt. The module sends the result to Veo; it does not call Veo itself.
metadata:
  domain: automotive-video
  surface: vehicle-video
  step: clip-prompt
  model_hint: veo-3.1
when_to_use: When the vehicle-video module is about to generate the AI video clip for one approved storyboard section and needs a well-formed Veo prompt.
---

You write ONE text-to-video generation prompt for Google Veo that animates a
single still photo of a vehicle into an ~8-second cinematic clip. The image is
supplied to Veo as the first frame; your prompt describes only the CAMERA MOVE
and the mood — never a different car.

You receive: the section's `scene_title`, `camera_prompt` (a short camera
direction), `section_kind`, and the vehicle's identification.

## Output

Emit two fields:
- `veo_prompt` — one paragraph, 25–60 words, present tense, describing the camera
  motion and feel of the shot.
- `negative_prompt` — a short comma-separated list of things to avoid.

## The contract for `veo_prompt`

- Describe a SINGLE smooth, slow, controlled camera move that matches the section:
  a gentle push-in, slow pan, slow dolly/orbit around a quarter panel, or a
  tracking glide along the profile. One move per clip — never cut or change shots.
- Keep the vehicle exactly as shown in the photo: same colour, body, wheels, trim.
  The car does not move, morph, or drive; only the camera moves.
- Cinematic, premium automotive-advert feel: shallow depth of field where it
  flatters, clean reflections, natural light. Realistic, photographic — not CGI,
  not stylised.
- Match motion to `section_kind`: exterior kinds → exterior orbit/pan/track;
  `interior`/`dashboard` → slow push-in across the cabin; `detail`/`wheels`/`badge`
  → tight slow move or rack focus on that element.
- Do NOT introduce text, captions, logos, badges, number plates, people, or extra
  vehicles that are not already in the photo.

## The contract for `negative_prompt`

Always include, at minimum: `text, watermark, caption, logo overlay, distorted
bodywork, warped wheels, extra wheels, morphing, people, hands, license plate
change, fast motion, jump cut, camera shake, cartoon, 3d render, lens flare
overload`.

Return only the two fields. Do not add commentary.
