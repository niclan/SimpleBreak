SimpleBreak
===========

SimpleBreak - a HandBrake wrapper to transcode DVD rips to smaller
files which are easier to stream and to copy to phones, pads and
laptops.

15-20 years ago I ripped all my CDs.  My disks are large enough and my
computer fast enough to rip the DVDs now.  I have been looking for the
easiest way to acomplish this a while.  By easy I mean

 - Few clicks or key-presses
 - Few decisions

I have settled on this work flow to rip DVDs:

 1. makemkv - this rips everything on the tracks I want - all audio
    tracks, all subtitles - into a matroska file with chapter marks
    and the works.

    These matroska files are large and does not play easily on the
    family TV (or handheld devices) either.  So they need to be
    smaller.

 2. HandBrake offers transcoding with a interface that is possible to
    understand.  There is a command line version too.  But there are
    still too many options.  Enter SimpleBreak: It figures out which
    audio and subtitle languages are available in the ripped matroska,
    asks you which ones you want, adds some hard coded options
    regarding video and audio quality and queues the transcoding job
    using the Unix/Linux batch system.  That way you can queue up many
    transcodings in one sitting and have the computer churn away at
    all hours. The batch job sends a email when it ends (if you've
    set up email correctly).  And then the next job starts running at
    once.

    The files made from DVDs are in the order of 1-1.7GB for a feature
    film and are easily played on the family TV over DLNA, on my
    phone, on a pad or whatever (try MX Player on Android) and does
    not take quite forever to copy around.

This is fast and easy enough that I can be bothered.

The program has no options, but you can set two variables to controll
it:

  export SBBATCH=0 
     Run HandBrakeCLI in the foreground instead of as batch

  export SBDEBUG=1
     Do not actually run any HandBrakeCLI command, only show it, and
     turn on tracing in the shell.
