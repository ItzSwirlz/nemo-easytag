project('nemo-easytag', 'c', version: '4.9.0', meson_version: '>= 0.52')

nemo_easytag_version = meson.project_version()
ver_arr = nemo_easytag_version.split('.')

nemo_easytag_major_version = ver_arr[0]
nemo_easytag_minor_version = ver_arr[1]
nemo_easytag_micro_version = ver_arr[2]

datadir = join_paths(get_option('datadir'))
localedir = join_paths(get_option('localedir'))
rootdir = include_directories('.')
schemadir = join_paths(datadir, 'glib-2.0', 'schemas')

# config.h
conf = configuration_data()
conf.set_quoted('GETTEXT_PACKAGE', meson.project_name())
conf.set_quoted('LOCALEDIR', localedir)
conf.set_quoted('VERSION', nemo_easytag_version)
conf_h_file = configure_file(output: 'config.h',
                             configuration: conf)

# Dependencies
gio_unix = dependency('gio-unix-2.0')
libnemo = dependency('libnemo-extension', version: '>= 3.0')
libnemo_extension_dir = libnemo.get_pkgconfig_variable('extensiondir')

# Install scripts
meson.add_install_script('install-scripts/meson_install_schemas.py')

subdir('data')
subdir('src')
