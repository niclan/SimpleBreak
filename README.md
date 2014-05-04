SimpleBreak
===========

SimpleBreak - a HandBrake wrapper to transcode DVD (and Blu-Ray) rips
to smaller files which are easier to stream to TVs and to copy to
laptops and hand helds.

I have been looking for the easiest way to acomplish this a while.  By
easy I mean

 - Few clicks or key-presses
 - Few decisions

MakeMKV + SimpleBreak is fast and easy enough that I can be bothered
to rip the disks for storage on the family server.

I have settled on this work flow:

 1. makemkv - this rips everything on the tracks I want - all audio
    tracks, all subtitles - into a matroska file with chapter marks
    and the works.

    These matroska files are large and does not play easily on the
    necessary devices either.  They need to be smaller.

 2. HandBrake is possible to understand.  But there are still too many
    things to keep track of.

    SimpleBreak figures out which languages (audio and subtitle) are
    available in the ripped matroska, asks you which ones you want,
    adds some hard coded options regarding video and audio quality.
    If the input is HD (1080 or 720) you are offered to reduce
    resolution to 720HD or SD (Standard Defenition).

    After the user interactions it queues the transcoding job using
    the Unix/Linux batch system.  That way you can queue up many
    transcodings in one sitting and have the computer churn away at
    all hours. The batch job sends a email when it ends (if you've set
    up email correctly).  And then the next job starts running at
    once.

    The files made from DVDs are in the order of 1-1.7GB for a feature
    film and are easily played on the family TV over DLNA, or on the
    hand helds (try MediaHouse and MX Player on Android) and does not
    take quite forever to copy around.

The program has no options (only user interactions), but you can set
two variables to controll it:

  export SBBATCH=0 
     Run HandBrakeCLI in the foreground instead of as batch

  export SBDEBUG=1
     Do not actually run any HandBrakeCLI command, only show it, and
     turn on tracing in the shell.
