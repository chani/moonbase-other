(

  # Get rid of user prompt, we know where the iptables headers are...
  sedit "s:^my \\\$IPTABLES_DIR.*:my \$IPTABLES_DIR = '/usr';:" Makefile.PL        &&
  sedit "s:^\\\$IPTABLES_DIR = lc prompt(.*::" Makefile.PL        &&

  perl Makefile.PL        &&
  default_make

) > $C_FIFO 2>&1
