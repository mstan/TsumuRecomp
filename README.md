# TsumuRecomp

Static recompilation of **Tsumu Light** (Japan, SLPS-02253) to native code using
the shared [psxrecomp](../psxrecomp) framework.

Tsumu Light is a budget re-release of the falling-block puzzle game *Tsumu*. The
boot EXE is a single 512 KB image loaded at `0x80010000`; puzzle/graphics/audio
data is streamed from disc (`*.BIN`, `TSUMU.XA`, FMV in `DOUGA.BIN`/`END.STR`).

## Layout

- `tsumu/` — disc image, boot EXE, SYSTEM.CNF (local-only, gitignored).
- `ghidra/` — headerless dump + import instructions for static analysis.
- `seeds/` — function-start hints for the recompiler.
- `game.toml` — per-game recompiler + runtime config.
- `psxrecomp-v4` — junction to the pinned framework worktree
  (`_wt-tsumu/psxrecomp`, branch `wt/tsumu`); see `psxrecomp-v4.pin`.

## Build

```
cmake -S . -B build-master -G Ninja
cmake --build build-master
```

Regenerate the recompiled C by invoking the framework recompiler against
`game.toml` (see the framework docs / `regen` recipe), then rebuild.

## Status

Bring-up — scaffolded 2026-06-22. See `DISC.md` for disc identity and the region
(NTSC-J BIOS) note in `CLAUDE.md`.
