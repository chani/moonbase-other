OPTS+=" --with-linux-kernel-headers=/usr/src/linux"

# This is needed or a test will fail
export EXTRA_CFLAGS="$CFLAGS"
unset CFLAGS

patch_it $SOURCE2 1 &&
patch_it $SOURCE3 1 &&
patch_it $SOURCE4 1 &&
patch_it $SOURCE5 1 &&

case `uname -r` in
  2.6.*|3.*)
    kv="26"
    ;;
  *)
    message "Unsupported kernel version!"
    exit -1
    ;;
esac &&

case `arch` in
  x86_64)
    OPTS+=" --with-afs-sysname=amd64_linux${kv}"
    ;;
  i386|i486|i586|i686|athlon)
    OPTS+=" --with-afs-sysname=i386_linux${kv}"
    ;;
  *)
    OPTS+=" --with-afs-sysname=`arch`_linux${kv}"
    ;;
esac &&

./regen.sh -q &&
./configure   --prefix=/usr                   \
              --sysconfdir=/etc               \
              --localstatedir=/var/lib        \
              --infodir=/usr/share/info       \
              --mandir=/usr/share/man         \
              $OPTS                           &&
make only_libafs &&
prepare_install
