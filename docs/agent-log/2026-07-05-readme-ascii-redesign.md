# 2026-07-05 — README ASCII redesign

## [now] Full rewrite of README.md

- **Action:** README.md — full rewrite (>30% change)
- **Why:** Brief: "minimal ascii style, clean and mature, not kid playground." Old design's playground signals: animated Lanyard Discord card with idle message, two tokyonight-colored stat cards, centered div header. Chose man-page motif (MEO(1)) over the templated `whoami`/figlet terminal cliché — mature, developer-native, one code block.
- **Result:** 24-line README. One `text` code block styled as a man page (NAME / DESCRIPTION / ENVIRONMENT / SEE ALSO) + one plain link line. Removed: Lanyard card, both github-readme-stats images, all centering markup.
- **Lesson:** 📌 GENERAL: "minimal" redesigns are mostly deletion — the new content was 20 lines; the value was cutting 3 third-party image embeds that dated the page.

## [now] Alignment fix

- **Action:** Footer line padded 77 → 79 chars to match header
- **Why:** Man-page frame reads as sloppy if left/right edges don't align; verified with `awk length()` not by eye.
- **Result:** header 79 = footer 79.
- **Lesson:** ASCII art alignment: measure with awk/wc, never trust visual inspection in a proportional-font editor.

## Summary

- Changed: README.md (full rewrite)
- Unchanged: everything else (repo has no other files)
- Remaining: optional — re-add GitHub stats with a muted theme (`theme=graywhite&hide_border=true`) if stats are wanted back
- Key decisions: man-page motif over terminal-prompt motif (mini-ADR: `whoami` block is the default ASCII-README cliché; man page is equally ASCII but rarer and reads older/calmer). Dropped SYNOPSIS section — fake CLI flags read as cute, brief said mature.
- Top 3 lessons:
  1. Minimal = deletion first; the embeds were the problem, not the text.
  2. Verify ASCII alignment mechanically (awk), not visually.
  3. Links can't live inside code blocks — keep one plain markdown link line outside the frame.
- Mistakes & dead ends: first footer write was 77 chars vs 79 header — caught by width check, fixed with 2-space pad.
