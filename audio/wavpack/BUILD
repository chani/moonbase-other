(

  OPTS+=" --disable-static" &&
  grep -E '\<mmx\>' /proc/cpuinfo &> /dev/null && OPTS+=" --enable-mmx" &&

  default_build

) > $C_FIFO 2>&1
