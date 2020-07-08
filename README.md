# CRLF Demo

This repo is just used as a demonstration of an error when cloned with JGit.

Using JGit the file `datei.txt` will be marked as modified directly after it
has been cloned. This seems to be the case because the file `.gitattributes`
tells git to convert Windows linebreaks (CRLF) to Unix linebreaks (LF) on
commit. But because this file has been added __after__ the file `datei.txt`
had been added, it is stored with CRLF line breaks. This seems to confuse
JGit, because it checkes out the file with LF linebreaks, only, and therefore
gets the difference.

When this repository is cloned with git, the file `datei.txt` is checked out
with its original CRLF line breaks and therefore no difference is detected.

