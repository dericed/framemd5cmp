Description: framemd5cmp bash script
========================

This script will evaluate two video files and identify discrepancies between their frames. It will only show where frames between the two files do not decode to exactly equal data. It is given the checksum of the decoded frame, not the stored data of the frame [this aspect will be updated in future instances of the script]

Dependencies/ required applications installed: ffmpeg diff

The script should be run as follows, from the folder where the script lives: sh framemd5cmp /Firstfile2compare /Secondfile2compare

Press enter.

A few text files will result.

Resulting text files
-------------------------

Firstfile2compare001_objects_hashonly.txt 

Firstfile2compare001_objects_vs_Secondfile2compare002objectsdiff.txt 

Secondfile2compare002objectsframemd5.txt 

Secondfile2compare002objects_hashonly.txt

Description of resulting text files
--------------------------

Firstfile2compare001objectshashonly.txt This file lists an MD5 hash for each individual frame for the file first listed to compare in the command. An 001 extension is added to distinguish if two file names are the same (common).

Firstfile2compare001objectsvsSecondfile2compare002objects_diff.txt This report compares the hashes of the two files.

Secondfile2compare002objectsframemd5.txt This report lists the frame number and associated hash.

Secondfile2compare002objectshashonly.txt This report lists the hash only.

Most important symbol to look out for is the “-” symbol before checksum hash. This indicates a frame that is brand new - e.g. altered in some way, not just taken away (for example, in the case of a black frame cut out from the beginning of a transfer).

Three lines - where there are @@ - these indicate changes 

DHC0038_objects_vs_DHC0038_save_as_test_diff.txt
--- means the frame is in original and not in the copy (second in the command line).
+++ indicates an original frame (if original is the first in the command line).

