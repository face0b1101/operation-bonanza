# Message attachments

Media recovered from the seized handsets in Operation BONANZA. Demo only.

`manifest.json` is the contract between the thread NDJSON, the generation scripts and
the app: for every attachment it records the filename, the thread and `message.id` it
hangs off, the caption (images) or transcript and speaker (voice notes), and which file
the embedding is taken from. The NDJSON carries the filename, mime type and
caption/transcript; the vector, SHA-256 and byte size are merged in at ingest from
`embeddings.json`.

The app serves these at `/source/df/<filename>`, the same way it serves the
intelligence originals.

## Files

| File | Role |
| ---- | ---- |
| `manifest.json` | Attachment contract, derived from the thread NDJSON |
| `<name>.prompt.md` | Gemini prompt that produced (or will produce) an image |
| `<name>.jpg` | Attachment image, phone-camera profile, roughly 1024px and 150-250 KB |
| `<name>.wav` | Voice note as generated, 24 kHz, kept because it is what gets embedded |
| `<name>.ogg` | Voice note for playback, 16 kHz mono Opus, referenced by the NDJSON |
| `embeddings.json` | Filename to vector sidecar written by `embed_attachments.py` |

## Workflow

1. Images: copy the body of `<name>.prompt.md` (everything below the `---` line) into
   Gemini and save the result here under the filename in the manifest. Downscale to
   roughly 1024px on the long edge; these sit in every search result, so 2-3 MB pages
   like the intelligence originals are far too heavy.
2. Voice notes: `uv run python scripts/media/generate_voice_notes.py --apply`.
3. Embeddings: `uv run python scripts/media/embed_attachments.py --apply`, which writes
   `embeddings.json`.
4. Ingest: `uv run ds es ingest --apply --dataset df`, which fails loudly if any
   attachment named in the NDJSON has no vector in the sidecar.

## Weapons imagery

`unit7-workshop-bench.prompt.md` carries two prompts. Prompt A depicts the deactivated
items directly as UK law enforcement training material. Prompt B is a proxy: the same
bench with tools, a part-stripped mechanism and no weapon in frame. Either one saves to
the same filename, so a refusal costs nothing downstream and the caption in the NDJSON
stays true for both.
