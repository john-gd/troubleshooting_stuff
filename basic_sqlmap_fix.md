# sqlmap error after updating

After downloading **sqlmap** on a debian machine through `sudo apt install sqlmap`, and verifying that it was an outdated version (as per usual, when using the standard linux packages).

I then ran `sudo sqlmap --update`, hit *y* when prompted for the attempt to download on a beta option instead of having to `git clone` their official [git repository](https://github.com/sqlmapproject/sqlmap). And ran into an */usr/bin/env: ‘python’: No such file or directory* error.

So I used `which sqlmap` to find its instalation folder, then I `sudo nano sqlmap` and changed the first line of the program file from **#!/usr/bin/env python** to **#!/usr/bin/env python3**.

Sqlmap runs on python, so when it calls python on the first line, it needs to be the same name of python on your system.
