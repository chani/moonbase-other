cd "$SPL_PATH" &&
default_config &&
make ${MAKES:+-j${MAKES}} &&

cd "$ZFS_PATH" &&
OPTS+=" --with-spl=$SPL_PATH" default_config &&
make ${MAKES:+-j${MAKES}} &&

prepare_install &&

# SPL and ZFS try to install files on top of each other and fail, so do
# this hack to work around it.
cd "$SPL_PATH"                       &&
mkdir -p pkg                         &&
make install DESTDIR="$SPL_PATH/pkg" &&
cd "$SPL_PATH/pkg"                   &&
cp -av * /                           &&

cd "$ZFS_PATH" &&
mkdir -p pkg         &&
make install DESTDIR="$ZFS_PATH/pkg" &&
cd "$ZFS_PATH/pkg" &&
cp -av * /
