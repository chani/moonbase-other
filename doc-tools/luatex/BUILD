# From http://www.gentoo-portage.com/dev-tex/luatex
export LC_ALL=C  &&

prepare_install  &&
./build.sh  &&

# Install executable
install -m755 build/texk/web2c/luatex /usr/bin/ &&

ln -s luatex /usr/bin/lualatex
