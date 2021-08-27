# hld2mtex
Fonts and scripts for transcribing the music of Hildegard of Bingen

I got tired of transcribing Hildegard's music by hand, so I  looked around for software to help. Unfortunately (and not surprisingly), I couldn't find any existing music notation packages that could handle 12th century liturgical notation. So I decided to make one myself. And in the spirit of open source software, I hereby present it to anyone who might want to use it (or to improve upon it).
The entire package is actually made up of a number of different pieces, of which I only created two small bits. The pieces that I wrote are hld2mtex, a script for converting a source file into musixtex format, and neumes.mf, which defines a font to use for Hildegard's neumes. The other packages that you need are TeX, MusiXTeX, and Perl. All of these packages are platform-independent, and so should run on any computer.

