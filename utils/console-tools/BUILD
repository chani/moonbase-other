unset CC CXX
(

  patch_it  $SOURCE_CACHE/$SOURCE2 1  &&
  patch_it  $SOURCE_CACHE/$SOURCE3 1  &&
  patch_it  $SOURCE_CACHE/$SOURCE4 0  &&
  patch_it  $SOURCE_CACHE/$SOURCE5 1  &&

  sedit "s/doc//"       Makefile.am   &&
  sedit "s/doc//"       Makefile.in   &&
  sedit "s/examples//"  Makefile.am   &&
  sedit "s/examples//"  Makefile.in   &&

  ./configure  --host=$BUILD             \
               --bindir=/bin             \
               --sbindir=/sbin           \
               --libdir=/lib             \
               --sysconfdir=/etc         \
               --infodir=/usr/share/info \
               --mandir=/usr/share/man   \
               --prefix=/usr             &&

  default_make  &&

  # Install man pages.

    for  (( COUNT=1 ; COUNT < 9 ; COUNT++ ));  do
      cp  doc/man/*.$COUNT  /usr/share/man/man$COUNT  2> /dev/null
      true
    done

) > $C_FIFO 2>&1
