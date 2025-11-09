# SPDX-License-Identifier: LGPL-2.1-or-later
# Author: Antonio Vázquez Blanco <antoniovazquezblanco@gmail.com>

if get_option('string_pooling')
  if get_option('strpool_build')
    tool_strpool = executable('strpool',
                              sources: 'strpool.c')
  else
    tool_strpool = find_program(get_option('strpool_path'))
  endif
endif
