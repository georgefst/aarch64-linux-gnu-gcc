This is the source of several AUR packages:
- https://aur.archlinux.org/packages/aarch64-none-linux-gnu-gcc-9.2-bin

I can't seem to upload from this repository, since AUR gets confused by older commits which had a different `pkgbase`, due to using a 32-bit version as a template.

Remember we always need to run `makepkg --printsrcinfo > .SRCINFO` upon making any changes to `PKGBUILD`, before committing.
