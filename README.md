PDF Decrypt
===========

This is a fork from https://github.com/zvynar/pdf-decrypt/

Just a wrapper / instructions on how to implement on macOS


Work from repo
--------------

```bash
cd ~
git clone git@github.com:jakelime/pdf-decrypt.git
cd pdf-decrypt
brew install qpdf
cp ~/Downloads/sample.pdf /pdf-decrypt/sample.pdf
bash pdf-decrypt.bash sample.pdf
```


Convert shell scripts to binary files
-------------------------------------

```bash
brew install shc
cd pdf-decrypt/
shc -U -f pdf-decrypt.bash -o pdf-decrypt
cp pdf-decrypt /usr/local/bin/pdf-decrypt
# Now, we can simply run the command pdf-decrypt anywhere
N2390113:~ jli8$ pdf-decrypt
pdf-decrypt: Operation not permitted
Killed: 9

 ¯\_(ツ)_/¯
```


Add to system path and run anywhere
------------------------------------------------

```bash
cp ~/pdf-decrypt/pdf-decrypt.bash /usr/local/bin/pdf-decrypt.sh
cd ~/Anywhere/
pdf-decrypt.sh sample.pdf
N2390113:Downloads jli8$ pdf-decrypt.sh sample.pdf
Password:

(base) N2390113:Downloads jli8$
```



From original readme:
================================================================

Dependencies:
 - qpdf, a PDF-transformation-program (pdf-decrypt is actually just a small
   wrapper of it).
 - bash (what means: I use bash-features like extended `test` or `function`s)

The bash-file works out of the box, no installation needed. If you want to have
it integrated in your desktop-environment, you can use the desktop-file and
icons. Remember to change the path in the .desktop-file if you do not copy the
files as follows:
 - `pdf-decrypt.bash` -> `/usr/bin/pdf-decrypt`
 - `pdf-decrypt.desktop` -> `/usr/share/applications/pdf-decrypt.desktop`
 - `pdf-decrypt.png` -> `/usr/share/pixmaps/pdf-decrypt.png`

(``/usr/bin/``) is protected by SIP in latest versions of macOS


Usage
-----

```bash
pdf-decrypt encrypted.pdf
```
The program will ask for a password and replace the encrypted PDF-file with an
unencrypted version preserving the content (including notes and comments inside
the encrypted version).
