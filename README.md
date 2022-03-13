This is the source of several AUR packages (each corresponding to a versioned branch e.g. `10.3`):
- https://aur.archlinux.org/packages/aarch64-none-linux-gnu-gcc-9.2-bin
- https://aur.archlinux.org/packages/aarch64-none-linux-gnu-gcc-10.3-bin

I can't seem to upload from this repository, since AUR gets confused by older commits which had a different `pkgbase`, due to using a 32-bit version as a template.

Remember we always need to run `makepkg --printsrcinfo > .SRCINFO` upon making any changes to `PKGBUILD`, before committing.

A git repo for a new version can be created as follows:
```
VER=10.3
cd ..
mkdir aarch64-linux-gnu-gcc-$VER-bin
cd aarch64-linux-gnu-gcc-$VER-bin
cp ../aarch64-linux-gnu-gcc/PKGBUILD .
cp ../aarch64-linux-gnu-gcc/.SRCINFO .
git init
git add .
git commit -m Initial
git remote add origin ssh://aur@aur.archlinux.org/aarch64-none-linux-gnu-gcc-$VER-bin
git push --set-upstream origin master
```
