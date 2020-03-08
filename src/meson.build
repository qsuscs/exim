project('exim', 'c')

cc = meson.get_compiler('c')
m_dep = cc.find_library('m', required: false)

conf = configuration_data()
if cc.sizeof('off_t', prefix: '#include <sys/types.h>') > cc.sizeof('long')
  conf.set('OFF_T_FMT', '%lld')
else
  conf.set('OFF_T_FMT', '%ld')
endif

if cc.sizeof('long long') > cc.sizeof('long')
  conf.set('LONGLONG_T', 'long long int')
else
  conf.set('LONGLONG_T', 'long int')
endif
