(

  TARGET=/usr/share/eclipse

  prepare_install  &&
  mkdir -p $TARGET &&
  cp -a * $TARGET &&
  ln -s $TARGET/eclipse /usr/bin/eclipse

) > $C_FIFO 2>&1
