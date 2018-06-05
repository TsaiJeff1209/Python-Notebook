

[Iterate all files in a directory using a 'for' loop
](https://stackoverflow.com/questions/138497/iterate-all-files-in-a-directory-using-a-for-loop)



176
down vote
Iterate through...
* files in current dir: `for %f in (.\*) do @echo %f`
* ubdirs in current dir: `for /D %s in (.\*) do @echo %s`
* files in current and all subdirs: `for /R %f in (.\*) do @echo %f`
* subdirs in current and all subdirs: `for /R /D %s in (.\*) do @echo %s`
