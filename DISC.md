# Disc identity — Tsumu Light (Japan)

Format: **bin/cue, single track (data only), MODE2/2352, NTSC-J**. Do **not**
convert to ISO — a 2048-byte "cooked" ISO discards the Mode-2 Form-2 XA sectors
PSX uses for streaming FMV/audio (this disc ships `TSUMU.XA`, `DOUGA.BIN`,
`END.STR`).

| Field | Value |
|-------|-------|
| Title | Tsumu Light |
| Serial | SLPS-02253 |
| Region | NTSC-J (Japan) |
| Track 01 | MODE2/2352, data (single track, no Red Book audio) |
| Size (.bin) | 118,416,144 bytes |
| MD5 | `252baaee71ef8ab359a0cae42da573df` (locally computed) |
| SHA-1 | `22926ffa79dc816b85947f7ebd7dd82e341123e7` (locally computed) |

Hashes above are computed locally from the working dump; cross-check against the
Redump database before treating as canonical.

Boot EXE: `SLPS_022.53` — load `0x80010000`, entry `0x800691F0`, text `0x80000`
(524,288 bytes), initial `$sp` `0x801FFFF0`. `$gp` is 0 in the header (set at
runtime). SYSTEM.CNF: `BOOT=cdrom:\SLPS_022.53;1`, `TCB=4`, `EVENT=16`,
`STACK=801fff00`.

Disc files of note: `SLPS_022.53` (boot EXE), `SYSTEM.CNF`, `TSUMU.XA`
(streaming audio), `DOUGA.BIN` / `END.STR` (FMV), `GRAPH1-4.BIN`, `SOUND.BIN`,
`MOJI.BIN` / `MONDAI.BIN` (text/puzzle data), `DUMMY.BIN` (40 MB pad).

Disc image and extracted EXE are local-only (gitignored); recreate from the
source dump if missing. Extract the boot EXE with mkpsxiso's `dumpsxiso`.
