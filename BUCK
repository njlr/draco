cxx_library(
  name = 'draco',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('', 'compression/**/*.h'),
    ('', 'core/**/*.h'),
    ('', 'io/**/*.h'),
    ('', 'mesh/**/*.h'),
    ('', 'point_cloud/**/*.h'),
  ]),
  srcs = glob([
    'compression/*.cc',
    'core/*.cc',
    'io/*.cc',
    'mesh/*.cc',
    'point_cloud/*.cc',
  ], excludes = glob([
    '*/*_test_base.cc',
    '*/*_test_utils.cc',
    '*/*_tests.cc',
    '*/*_test.cc',
  ])),
  compiler_flags = [
    '-std=c++14',
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_library(
  name = 'core',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('', 'core/*.h'),
  ]),
  srcs = glob([
    'core/*.cc',
  ], excludes = glob([
    'core/*_test_base.cc',
    'core/*_test_utils.cc',
    'core/*_tests.cc',
    'core/*_test.cc',
  ])),
  compiler_flags = [
    '-std=c++14',
  ],
)

cxx_library(
  name = 'point-cloud',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('', 'point_cloud/*.h'),
  ]),
  srcs = glob([
    'point_cloud/*.cc',
  ], excludes = glob([
    'point_cloud/*_test_base.cc',
    'point_cloud/*_test_utils.cc',
    'point_cloud/*_tests.cc',
    'point_cloud/*_test.cc',
  ])),
  compiler_flags = [
    '-std=c++14',
  ],
  deps = [
    ':core',
  ],
)

cxx_library(
  name = 'mesh',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('', 'mesh/*.h'),
  ]),
  srcs = glob([
    'mesh/*.cc',
  ], excludes = glob([
    'mesh/*_test_base.cc',
    'mesh/*_test_utils.cc',
    'mesh/*_tests.cc',
    'mesh/*_test.cc',
  ])),
  compiler_flags = [
    '-std=c++14',
  ],
  deps = [
    ':core',
    ':point-cloud',
  ],
)

cxx_library(
  name = 'compression',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('', 'compression/**/*.h'),
  ]),
  srcs = glob([
    'compression/*.cc',
  ], excludes = glob([
    'compression/*_test_base.cc',
    'compression/*_test_utils.cc',
    'compression/*_tests.cc',
    'compression/*_test.cc',
  ])),
  compiler_flags = [
    '-std=c++14',
  ],
  deps = [
    ':core',
    ':mesh',
    ':point-cloud',
  ],
)

cxx_library(
  name = 'io',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('', 'io/**/*.h'),
  ]),
  srcs = glob([
    'io/*.cc',
  ], excludes = glob([
    'io/*_test_base.cc',
    'io/*_test_utils.cc',
    'io/*_tests.cc',
    'io/*_test.cc',
  ])),
  compiler_flags = [
    '-std=c++14',
  ],
  deps = [
    ':core',
    ':compression',
  ],
)
