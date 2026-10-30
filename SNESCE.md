# Genesis Plus GX EX for the NES and SNES Classic

This branch builds the [Expanded Rom Size](https://github.com/RapidEdwin08/Genesis-Plus-GX-Expanded-Rom-Size) fork of Genesis Plus GX for the NES and SNES Classic (ARMv7, 253 MB of RAM), as the `genesis_plus_gx_ex` core of [retroarch-snesce-cores](https://github.com/DefKorns/retroarch-snesce-cores).

## Changes

All in `core/cart_hw/paprium.h`, plus the library name in `libretro/libretro.c`.

- Only the Paprium track being played stays in memory. The upstream code never freed a track and loaded four boss tracks at start, which runs out of memory on the console at the title screen.
- The music plays in stereo. Upstream played the left channel on both sides.
- A `.wav` next to an `.mp3` of the same name (PCM, 16 bit, stereo) is read instead of the MP3, without decoding it.
- The library name is `Genesis Plus GX EX`, so its options do not mix with the plain core.

## Credits

Genesis Plus GX is by Charles MacDonald and Eke-Eke, and is licensed for non-commercial use (see `LICENSE.txt`). The Paprium support and the expanded ROM size are by RapidEdwin08 and BillyTimeGames, on the work of Project Little Man.
