# Turning a 1080p Screen Recording Into a Usable 4K Asset

Screen recordings are the one case where 4K genuinely wins, because UI text is pure
high-frequency content. Measured: ink coverage and stroke solidity diverge — a 720p→4K upscale
reads as +3.4% ink while keeping 60% of native stroke darkness, 4:2:0 destroys 46% of colour in
small text invisibly to luma metrics, and stroke solidity swings 11 points at 11 px purely from
sub-pixel phase.

**Read it with the tables and the reproduction snippets:** <https://celticgemini001.github.io/upgolab-screen-recording-4k/>

## About this repo

This repository exists to serve one measured article. Every number in it came from
numpy and ffmpeg run on real files on this machine — the commands are in the page so
you can re-run them and get the same rows. Where the measurement contradicted the
hypothesis, the page says so.

Three results that did not go the way I expected, for anyone deciding whether to trust the rest:

- **Ink coverage cannot see the damage it is supposed to measure.** A 720p→4K upscale
  scores +3.4% ink while retaining 60% of the stroke darkness a native 4K render has.
  Counting ink pixels rewards grey smear as much as it rewards a dark stroke.
- **4:2:0 destroys colour in small text and hides it behind a luma metric.** 11 px text
  keeps 54.1% of its chroma at crf18; luma ink coverage over the same encode reads 100.7%.
- **Solidity is a range, not a number.** Sweeping sub-pixel phase, the same 11 px text ×3
  scores 19.1 or 30.2 depending only on where the glyph landed inside the pixel. Ink
  coverage over the same 16 phases moves 3.5%. The codec preserves the modulation
  (r = 0.998); a whole-pixel scroll rate hides it entirely.

## The tool behind the notes

<https://upgolab.com> — browser-based AI upscaler for photos and short video.
