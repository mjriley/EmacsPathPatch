# EmacsPathPatch
Causes Emacs for Mac to include /etc/paths so the shell functions properly

OS X terminal sessions will modify your path to include all paths listed in /etc/paths.
Desktop applications will not augment the paths with this file.
Because of this, if you use the built-in emacs shell, you can get inconsistent behavior.

The biggest culprit is that brew tends to install its binaries in /usr/local/bin,
which is a path only added by /etc/paths.

To install:

```patch -p0 < Emacs.patch```

the above will patch /Applications/Emacs.app/Contents/MacOS/Emacs

If for some reason you have it in another location, you can try:

```patch < Emacs.patch and input the filename when prompted```
OR
```patch <fileToPatch> Emacs.patch```
