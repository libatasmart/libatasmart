# SPDX-License-Identifier: LGPL-2.1-or-later
# Author: Antonio Vázquez Blanco <antoniovazquezblanco@gmail.com>

# Dependencies
pkg_mod = import('pkgconfig')
dep_udev = dependency('libudev', version : '>=143')

# Library definition
if get_option('enable_string_pooling')
    src_atasmart = custom_target('atasmart_strpool',
                               input: 'atasmart.c',
                               output: 'atasmart_strpool.c',
                               command : [tool_strpool, '@INPUT@', '@OUTPUT@'])
else
    src_atasmart = 'atasmart.c'
endif
inc_atasmart = include_directories('.')
lib_atasmart = shared_library('atasmart',
                       sources: src_atasmart,
                       include_directories: inc_atasmart,
                       vala_header: 'atasmart.h',
                       vala_vapi: 'atasmart.vapi',
                       version: '4.0.5',
                       dependencies: dep_udev,
                       install: true)
dep_atasmart = declare_dependency(include_directories: inc_atasmart,
                                  link_with: lib_atasmart)

install_headers('atasmart.h')

pkg_mod.generate(libraries : dep_atasmart,
                 version : meson.project_version(),
                 name : 'libatasmart',
                 description : 'ATA S.M.A.R.T. reading and parsing library.')
