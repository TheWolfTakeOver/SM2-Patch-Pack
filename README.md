# Spider-Man 2 (Original Xbox) — Patch Pack (USA)

**Inf Sense • Lock Timer • 10K Awards • INI God Mode (clean + toggleable)**  
**TitleID:** 4156002B (USA)

This repo is a small **“total package”** of stable, tested patches for **Spider-Man 2 (Xbox OG)**.

The goal is simple: **toggleable, repeatable patches** with **no trainer menu required**.

I started by reverse-engineering an EvoX trainer and then converted the useful behavior into **clean, permanent patches**.  
This was the right order. *(Future us: do this first.)*

---

## What You Get

### ✅ Stable Patches (XBE)
- **Infinite Spider-Sense** (no drain / stays filled)
- **Locked Timer**
- **10,000 Hero Points per award event** (stable)

### ✅ Safe God Mode (INI)
- God Mode lives in `game.ini` because the **health write path affects enemies too**
- This makes God Mode **easy to enable/disable** without breaking combat logic

---

## Repo Layout

### `MERGE_WITH _SM2_GAME_FOLDER/`
Drop-in files to merge into your game folder:
- `default.xbe` (patched)
- `data/game.ini` (with God Mode toggle)

### `PATCHES/`
IPS patch files if you prefer patching yourself:
- `Spiderman2_NTSC_Cheats_xTWTO.ips`
- includes `lips102.zip` (IPS patcher)

### `STOCK/`
Original baseline copies used for diffing/verification:
- `default.xbe`
- `data/game.ini`

### `RESEARCH/`
- Notes
- Offsets
- Toolchain used

---

## Install (Recommended: Drop-In Merge)

1. **Back up** your original:
   - `default.xbe`
   - `data/game.ini`
2. Copy everything from:
MERGE_WITH _SM2_GAME_FOLDER/
3. Paste into your existing Spider-Man 2 game directory.
4. Overwrite when prompted.

That’s it.

---

## Install (Alternate: IPS Patch Your Own XBE)

If you want to patch manually:

1. Start with the **USA** `default.xbe` (TitleID `4156002B`)
2. Apply:
PATCH/Spiderman2_NTSC_Cheats_xTWTO.ips
3. Replace your game’s `default.xbe` with the patched output.
4. *(Optional)* Copy `data/game.ini` if you want INI-based God Mode.

---

## God Mode Toggle (INI)

God Mode is **intentionally not hard-patched** into the XBE.

Why?  
Because the same health write path is shared with **non-player entities**.  
Hard-patching it makes enemies immortal — funny once, then effectively a soft-lock (unless you enjoy drowning enemies for sport).

**Design choice:**
- **Health** → INI God Mode
- **Sense / Timer / Awards** → XBE patches

To toggle:
1. Open:
data/game.ini
  2. Flip the relevant flag (see comments in file)

If you break it: you didn’t.  
Just restore from `STOCK/data/game.ini`.

---

## Compatibility

- ✅ **Spider-Man 2 (USA / NTSC)** — TitleID `4156002B`
- ⚠️ Not tested on PAL or other releases  
*(Offsets will need to be located/ported)*

---

## Credits

- Original EvoX Trainer: **dootdoo / Evox-T**
- Reverse engineering, patch conversion & validation: **me + a stubborn AI sidekick**

---

## Legal / Respectful Use

This repo contains patch data and modified binaries intended for **personal use on legally owned copies** of the game.

Don’t be weird with it.

---

## What *Maybe* Next (Not Included Yet)

- Patch the **award function directly** so rewards count toward mission progression
- More surgical **player-only God Mode** *(don’t count on it)*
- Region ports (PAL)

---

🍻
