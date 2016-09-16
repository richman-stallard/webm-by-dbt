# webm-by-dbt

/dbt/'s super awesome webm conversion script for bash

Copy webm to any directory in your PATH, make it executable.
$ webm <source file>
to get started. Will create a subfolder ./webm with your webms and a text file ./webm_log.txt which contains the supplied parameters for all the webms you made in this working directory.
See bash-example.txt for example session.

Resolution can be chosen out of three options (1280x720, 960x540 and 640x360) because it depends on source file frame rate.
File size limits were chosen with some safety margin in mind; you can edit them if you want however (maxsize).

Choosing resolution:
Start at 960x540. Convert. Does your webm look like shit or stutter? Go DOWN
to 640x360, bitrate might be too low for this resolution. Is your webm way below the size limit? Go up to 1280x720.
Rule of thumb for 30 fps video:
- up to 10 seconds -> 720p
- up to 30 seconds -> 540p
- over 30 seconds -> 360p

If your webm is really long and exceeds the size limit, lower the resolution. A certain minimum bitrate is required so you likely won't be able to keep a 30 second 720p webm under 3 MB.
