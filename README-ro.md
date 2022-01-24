# RUNZ80 pentru Cobra

RUNZ80 este un utilitar CP/M pentru microcalculatorul Cobra care încărcă și
execută snapshot-uri ZX Spectrum în [formatul .z80][z80format] folosit de mulți
emulatori Spectrum.

[z80format]: https://worldofspectrum.org/faq/reference/z80format.htm

Suportă versiuni 1, 2, și 3 a formatului .z80, dar ignoră orice informație care
nu se aplică Spectrum 48K sau Cobra.

## Mulțumiri

Metoda de săltare în un snapshot de memorie și restaurare statul CPU-ului a
fost luat din [pagina BASIC+NMI a cobrasov.com][BASIC+NMI].  Codul în
LOADER.Z81 și RESTORE.Z80 a fost luat direct de acolo cu modificări minime.
Multe mulțumiri autorului anonim al cobrasov.com!

[BASIC+NMI]: http://cobrasov.com/CoBra%20Project/basic+nmi-ro.html

## Rezumat

`RUNZ80 SNAPSHOT[.Z80]`

***NOTĂ: RUNZ80 va încerca să restaureze registrele cipului de sunet AY-3.  Din
cauza conflictului de adrese între AY-3-ul Spectrumului 128K și interfața de
floppy disk Cobra-ului, acest lucru poate cauza coruperea dischetelor dacă ei
nu sunt scoase mai întâi sau dacă unitățile nu sunt dezactivat după încărcarea
snapshot-ului.***

Când RUNZ80 a terminat să încarce fișierul, se va întrerupe și va aștepta
intrare de tastatură.  Odată ce apăsați o tastă, va relua execuția din
snapshot-ul.  Pauza îți da oportunitatea să scoateți dischete din unități sau
le dezactivați altfel să evitați corupere.

RUNZ80 execută o rutină pentru restaurare statul CPU-ului din fundul memoriei
video, deci când se încărcă un snapshot va exista niște gunoi în partea de sus
a ecranului.

## Assamblând

RUNZ80 a fost scris în asamblarea Z80 pentru SLR Systems Z80ASM Rel 1.32.
Puteți asambla propriul RUNZ80.COM rulând:

`Z80ASM RUNZ80`

## Ce e Cobra?

(Este destul de obscur).  Cobra este un calculator Românesc din anii 1980.
Este compatibil cu ZX Spectrum 48K dar poate rula și CP/M.  Cele mai extinsă
sursă de informații este [cobrasov.com].

[cobrasov.com]: http://cobrasov.com
