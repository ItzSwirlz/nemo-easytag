libdeps = [gio_unix, libnemo]

nemo_easytag_lib = shared_library(
  'nemo-easytag',
  sources: 'nemo-easytag.c',
  dependencies: libdeps,
  include_directories: rootdir,
  install: true,
  install_dir: libnemo_extension_dir
)
