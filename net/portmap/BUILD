(

  sedit "/#include <tcpd.h>/d" pmap_check.c &&
  sedit 's;}/sbin;}/usr/sbin;g' Makefile &&

  make NO_TCP_WRAPPER=1    &&
  prepare_install          &&
  make install

) > $C_FIFO 2>&1
