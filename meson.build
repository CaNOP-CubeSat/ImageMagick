project('ImageMagick', 'c', version: '0.0.1')

message('Building ImageMagick (make)')
r = run_command('./configure', check: true)
output = r.stdout().strip()
errortxt = r.stderr().strip()
r = run_command('make', '-j', '4', check: true)
output = r.stdout().strip()
errortxt = r.stderr().strip()

message('Installing ImageMagick (make install - must have elevated privileges)')
r = run_command('make', 'install', check: true)
output = r.stdout().strip()
errortxt = r.stderr().strip()

im_dep = declare_dependency(
    version: meson.project_version(),
    include_directories : ['MagickCore/.deps', 'MagickWand/.deps']
)

message('Finished with ImageMagick (make)')
