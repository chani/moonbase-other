if in_depends $MODULE lua; then
  export LUA_LIBS+=" /usr/lib/lua" &&
  export LUA_CFLAGS+=" -DLUA_COMPAT_ALL=1"
fi &&

if module_installed live555; then
  CPPFLAGS_live555="-I/usr/lib/live/liveMedia -I/usr/lib/live/groupsock -I/usr/lib/live/BasicUsageEnvironment -I/usr/lib/live/UsageEnvironment"
fi &&

if in_depends vlc qt4; then
 . /etc/profile.d/qt4.rc
fi &&

OPTS+=" --enable-xvideo --enable-real --enable-realrtsp --enable-media-library --disable-sid --with-tuning=$CPUTUNE" &&

default_build &&

sedit "s:Categories=:Categories=Multimedia;:" /usr/share/applications/vlc.desktop &&

unset LUA_LIBS &&
unset LUA_CFLAGS
