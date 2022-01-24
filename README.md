(Vezi [README-ro.md](README-ro.md) pentru o traducere greșită în română.)

# RUNZ80 for Cobra

RUNZ80 is a CP/M utility for the Cobra microcomputer which loads and executes
ZX Spectrum snapshots in the [.z80 format][z80format] used by many Spectrum
emulators.

It supports .z80 snapshot versions 1, 2, and 3, but it ignores any information
that isn't applicable to Spectrum 48K or Cobra.

[z80format]: https://worldofspectrum.org/faq/reference/z80format.htm

## Acknowledgments

The method for jumping into a memory snapshot and restoring CPU state was taken
from [the BASIC+NMI page of cobrasov.com][BASIC+NMI].  The code in LOADER.Z80
and RESTORE.Z80 was taken directly from there with minimal modifications.  Many
thanks to the anonymous author of cobrasov.com!

[BASIC+NMI]: http://cobrasov.com/CoBra%20Project/basic+nmi.html

## Synopsis

`RUNZ80 SNAPSHOT[.Z80]`

***NOTE: RUNZ80 attempts to restore AY-3 sound chip registers.  Because of the
address conflict between the Spectrum 128K's AY-3 and the Cobra floppy
controller, this may cause corruption of floppy disks if they are not removed
or if the drives are not disabled after loading the snapshot.***

When RUNZ80 is finished loading the snapshot file it will pause and wait for
keyboard input.  Once you press a key, it will resume execution from the
snapshot.  The pause gives you an opportunity to remove your floppy disks from
the drives or otherwise disable them to avoid corruption.

RUNZ80 runs the CPU restore routine from the bottom of video memory, so when a
snapshot starts, there will be some garbage at the top of the screen.

## Building

RUNZ80 was written in Z80 assembly for SLR Systems Z80ASM Rel 1.32.  You can
assemble your own RUNZ80.COM by running:

`Z80ASM RUNZ80`

## What's Cobra?

(It's pretty obscure).  Cobra is a Romanian home computer from the 1980s.  It's
compatible with the ZX Spectrum 48K but can also run CP/M.  The most extensive
source of information is [cobrasov.com].

[cobrasov.com]: http://cobrasov.com
