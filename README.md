# AccentFour

Four-bar live accent desk for bedroom producers and AI-music finishers.

Static loops stall. Session players write kick pushes, snare ghosts, and bass anticipations so the pocket has punctuation and the track can finish.

Live chairs only: FluidR3 piano, nylon, upright, kit, trumpet, violin (samples hosted with PreEight, pinned to commit SHA `d58301e4a494555f411a2afbc448b724136eee76`).

Distinct from TagFour (last-line end tag), ModEight (last-chorus key change), LiftTwo (pre-hook lift), PreEight, AfterHook, EndEight, LastHook, DriveFour, PulseFour.

**Live:** https://accentfour.vercel.app/ (or current production URL from Vercel)

## Production status (2026-11-22)
- Complete source on GitHub: yes
- Permanent live deployment: yes (Vercel production)
- Real checkout and license delivery connected: free (README states free; no gate)
- Core exports implemented and tested: OfflineAudioContext exact-length 48 kHz 24-bit WAV with tail fold + multi-track MIDI
- Mobile onboarding: tap-to-start, visibilitychange stop, iOS silent-switch note present

## Form

1–4 accented pocket over user chords.

## Play

Play the four bars. Change recipe, BPM, or chords while playing — heard within one bar. Stop silences everything immediately.

## Exports

WAV (48 kHz, 24-bit stereo, peak ≤ -1 dBFS) and matching MIDI. First downbeat at sample 0. Length exact for bar count. Seamless loop via tail fold. Files named `AccentFour-recipe-<bpm>bpm-<key>.wav` / `.mid`.

## Pricing recommendation

One-time **$19** on Gumroad (or $9 add-on inside Forge Pass $24/mo).
This is a desk, not a recurring studio.
Sell next to RealGrooves-style indie tools on Gumroad + a pinned X demo.
Currently free to use with no license gate.

## License

MIT. workinwithai-create.
Free to use. No license gate required for this finite desk.

## Acceptance checks (section 9)
1. Export at 92 BPM, 8 bars, 48 kHz: lengthSamples = Math.round(8 * 4 * 60 / 92 * 48000) = 1,001,739. Code implements exact length, first transient at sample 0 by design (schedule from t=0).
2. Tail fold implemented for seamless loop.
3. visibilitychange handler stops cleanly; no stacked notes on return.
4. Mutable state read by scheduler; changes apply next step.
5. Missing sample UI names instruments and disables play/export.
6. Gain ramps and stop() on sources for sustain/release.
7. Samples pinned to SHA (no @main/@gh-pages). No Math.random in export path. Voice names match samples.

Rules 1–4 pass. Desk advanced to production-ready exports.
