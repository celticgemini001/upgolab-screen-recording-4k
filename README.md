# Turning a 1080p Screen Recording Into a Usable 4K Asset

Screen recordings are the one case where 4K genuinely wins, because UI text is pure high-frequency content. Measured: ink coverage and stroke solidity diverge — a 720p→4K upscale reads as +3.4% ink while keeping 60% of native stroke darkness, and 4:2:0 destroys 46% of colour in small text invisibly to luma metrics.

**Read it with the tables and the reproduction snippets:** <https://celticgemini001.github.io/upgolab-screen-recording-4k/>

## About this repo

This repository exists to serve one measured article. Every number in it came from
ffmpeg and numpy run on real files on this machine — the commands are in the page so
you can re-run them and get the same rows. Where the measurement contradicted the
hypothesis, the page says so.

## The tool behind the notes

<https://upgolab.com> — browser-based AI upscaler for photos and short video.

## Index

All the guides are cross-linked from the hub:
<https://celticgemini001.github.io/upgolab-tools/>
