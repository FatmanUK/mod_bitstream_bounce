# mod_bitstream_bounce
The direct follow-on from Signal Lost. I've dialled the LLM's intelligence down to its lowest setting.

## A Gemini mod in Flash-Lite mode! Can it do it?
This is the first abject failure. Flash-Lite is so unbelievably stupid, it doesn't even understand the concept of storing data in order to analyse it. It's possible Gemini was suffering an outage at the time.

I'm thinking about the next (or *first*) step. Gemini is so pathetically bad at this, I might just switch to Claude to get this one done.

## result

No output as yet.

## build notes
To get the ST-01 and ST-02 archives on Debian-based Linux, issue these commands:
   
    ❯ sudo apt update
    ❯ sudo apt install lhasa wget
    ❯ install -d mod_cold_boot/stxx
    ❯ cd mod_cold_boot/stxx
    ❯ wget -O st-01.lha https://aminet.net/mods/inst/st-01.lha
    ❯ lha x st-01.lha
    ❯ wget -O st-01.lha https://aminet.net/mods/inst/st-02.lha
    ❯ lha x st-02.lha

These samples are in IFF format and AmigaOS doesn't use file extensions, so to make MilkyTracker see them you have to rename the ones you want with '.iff' extensions. Like this:
   
    ❯ mv Stabs Stabs.iff
