# Donut Payments Client — prototype source (Fabric 1.21.11)

This is an **uncompiled prototype**, not a verified, working JAR. The build environment used to prepare it has no external Maven access and no Fabric/Minecraft dependencies cached, so compilation and gameplay testing were not possible.

## Implemented
- Client-side chat/system-message scanning for common `NAME paid you $AMOUNT` and `+$AMOUNT from NAME` formats.
- Right-aligned feed, colored border, cached player-list skin-head rendering.
- Large payment celebration for payments >= 1 billion, with animated particles and text.
- Duplicate-message suppression and capped notification queue.

## Limitations
- DonutSMP's exact incoming packet/text format is not verified. Real messages may use styled components, custom payloads, or scoreboard events instead of plain chat.
- Heads render only when the player is present in the server player list. Remote skin lookups are not implemented.
- Celebration is an approximation, **not a frame-perfect reproduction** of the clip (rocket model, custom art, shader particles, exact timings and sounds are not yet implemented).
- Fabric dependency versions and 1.21.11 API method signatures have not been verified against a downloaded toolchain.

## Build on a connected computer
Install JDK 21 and Gradle 9.x, then run `gradle build` in this directory. If Fabric Loom reports an unavailable dependency or a Minecraft API change, update the version coordinates or method signatures to the current 1.21.11 Fabric API. The output would be in `build/libs/` after a successful build.

## Testing
Join DonutSMP, receive a real payment, and capture the unmodified client log / chat component text. Use that to refine the detector. The mod does not initiate payments, automate scanning, or bypass server rules.

## Payment threshold
The simple payment feed triggers for incoming payments of **$10,000,000 or more** (including 10m, 10,000,000, and 0.01b). The existing large celebration threshold remains $1,000,000,000.

Build requires Gradle and online Fabric/Minecraft dependencies: `gradle build`.
