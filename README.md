# Music Creator 🎵

A creative pipeline for transforming poems into music, visuals, and animated stories.

## Vision

Every poem can become more than words. This project is a workshop where we take a poem — from a web page, a book, or anywhere — and bring it to life through multiple stages of creation:

1. **Source** — Capture the original poem from a URL or text
2. **Lyrics** — Adapt the poem into singable lyrics for Suno AI
3. **Music** — Generate music from the adapted lyrics with style/genre tags
4. **Visuals** — Design scenes and generate images that tell the story visually
5. **Animation** — Animate the scenes into motion (video)
6. **Final** — Combine everything into a polished artifact

Each poem lives in its own folder under `poems/`, tracked by a `manifest.json` that records every stage of its journey.

## Project Structure

```
music-creator/
├── README.md              # This file
├── docs/                  # Documentation & workflows
│   └── manifest-schema.json  # JSON Schema for manifest files
├── ideas/                 # Brainstorming, sketches, concepts
├── poems/                 # One folder per poem
│   └── <poem-name-ru>/    # Named in Russian
│       ├── manifest.json  # Tracks all stages of this poem
│       ├── images/        # Generated visuals
│       ├── audio/         # Generated music
│       └── video/         # Generated animations
└── skills/                # Hermes-compatible skill definitions
    └── ...                # Reusable workflows as skills
```

## Manifest Format

Each poem has a `manifest.json` that records everything:

```json
{
  "id": "poem-slug",
  "title_ru": "Название стиха",
  "title_en": "Poem Title in English",

  "source": {
    "url": "https://...",
    "author": "Author Name",
    "title": "Original Title",
    "original_text": "Full text of the original poem"
  },

  "lyrics": {
    "adapted_text": "Lyrics adapted for Suno",
    "suno_prompt": "Description for Suno generation",
    "suno_tags": "genre:pop, mood:melancholic, ..."
  },

  "music": {
    "suno_url": "https://suno.com/song/...",
    "audio_file": "audio/final.wav",
    "notes": "What worked, what to change"
  },

  "scenes": [
    {
      "scene_number": 1,
      "description": "What happens in this scene",
      "visual_style": "watercolor, cinematic, anime...",
      "image_prompt": "Prompt for the first frame",
      "animation_hint": "How to animate (slow pan, zoom, etc.)",
      "image_file": "images/scene-01.png",
      "video_file": "video/scene-01.mp4"
    }
  ],

  "timeline": [
    { "stage": "source", "date": "2026-07-27T22:00:00Z", "notes": "Found on stihi.ru" },
    { "stage": "lyrics", "date": "2026-07-27T23:00:00Z", "notes": "Adapted for Suno" }
  ]
}
```

## Workflow Stages

### 1. Source 📄
Find a poem (URL, book, text). Copy it into the manifest's `source` field.

### 2. Lyrics Adaptation 🎤
Rewrite the poem into lyrics that work well with Suno AI — natural phrasing, chorus structure, emotional pacing.

### 3. Music Generation 🎵
Craft a Suno prompt with style tags (genre, mood, instruments) and generate the song. Save the link and audio file.

### 4. Scene Design 🎨
Break the poem into narrative scenes. For each scene, write:
- A description of what happens
- The visual style (art direction)
- An image prompt for the first frame
- An animation hint (camera movement, effects)

### 5. Image Generation 🖼️
Generate the first-frame images using AI image models. Refine prompts until they match the vision.

### 6. Animation 🎬
Animate each scene — zooms, pans, transitions, effects — into short video clips.

### 7. Final Assembly 🎞️
Combine music, animated scenes, and titles into a complete music video.

## Skills

Workflows from this project can be saved as Hermes skills for reuse. Each skill captures a repeatable step with all the prompts and patterns we discover.

## Contributing Ideas

The `ideas/` folder is for brainstorming — throw in concepts, visual references, style experiments, anything.

## License

MIT
