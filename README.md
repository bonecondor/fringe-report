# fringe-report

Static generator for [fringe.report](https://fringe.report). Paper page, typewriter ink, numbered dispatches, red tag stamps. No dependencies — same pattern as foid-report and scene-log.

Notes on interesting things, people talked to lately, and little-more-than-scratchpad musings. One chronological stream; tags are optional and free-form.

## Posting

1. Add a markdown file to `posts/` named by date: `posts/2026-07-05.md`
   (two posts same day: `posts/2026-07-05-two.md`)
2. Optional frontmatter:

   ```
   ---
   title: what the post is about
   tags: person, musing
   time: 9:05 pm
   ---
   ```

   Everything is optional — a bare paragraph is a valid post. Posts are numbered chronologically at build time (FR 0001, FR 0002, ...); a title renders as "FR 0002: the title". Include `time:` since posts are dated by filename only. Each tag gets its own page at `/tag/<tag>.html`.
3. Build and publish:

   ```
   python3 build.py
   git add -A && git commit -m "dispatch" && git push
   ```

GitHub Pages serves `docs/` on `main`. `drafts/` is ignored by the build.
