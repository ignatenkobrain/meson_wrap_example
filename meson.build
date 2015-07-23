project('meson-wrap', 'c')
enet_dep = dependency('libenet', required : false)

if enet_dep.found()
  enet_inc = []
  enet_lib = []
else
  enet_sp = subproject('enet')
  enet_inc = enet_sp.get_variable('incdir')
  enet_lib = enet_sp.get_variable('enetlib')
endif

executable(
  'main',
  sources : 'main.c',
  include_directories : enet_inc,
  link_with : enet_lib,
  dependencies : enet_dep
)
