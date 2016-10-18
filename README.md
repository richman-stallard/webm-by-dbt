# webm-by-dbt

/dbt/'s super awesome webm conversion script for bash

Requires ffmpeg compiled with --enable-libvpx --enable-libvorbis and possibly --enable-gpl.


# getting started

Make file "webm" executable with

$ chmod +x ./webm

, copy or move it to a directory in your PATH, e.g.

$ sudo cp ./webm /usr/local/bin/

, then start converting by calling

$ webm "/path/to/source.file"

# output

Will create a subfolder of the current working directory ./webm with your webms and a text file *.log (replace * with name of input video file) which contains the supplied parameters for all the webms you made in this working directory based on that file.
See "bash-example.txt" for example session and "Steel Panther - Live from Lexxi’s Mom’s Garage DVD (Full Concert)-FXXcvntSlmY.mkv.log" for the sample logfile created in that session.

# resolution

Resolution can be chosen out of three options (1280x720, 960x540 and 640x360) because it depends on source file frame rate.
File size limits were chosen with some safety margin in mind; you can edit them if you want however (maxsize).

Choosing resolution:
Start at 960x540. Convert. Does your webm look like shit, stutter or exceed the file size limit? Go DOWN
to 640x360, bitrate might be too low for this resolution. Is your webm way below the size limit? Go up to 1280x720.
Rule of thumb for 30 fps video:
- up to 15 seconds -> 720p
- up to 30 seconds -> 540p
- over 30 seconds -> 360p

After conversion script asks for input for next clip; exit with escape sequence (ctrl+c).
