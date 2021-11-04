project('A GTK4 Project',
        'c', # lang-name e.g. 'c', 'cpp', etc
        version: '1.0.alpha')

gtkmm_dep = dependency('gtk4')
include_dir = include_directories('include')

subdir('src')

# SubDir's meson.build
lib_sources = files('mainWindow.c')
main_sources = files('main.c')

libtest1 = library(
	              'test1', lib_sources,
		          include_directories: include_dir,
		          dependencies: gtkmm_dep
		          )

executable(
	      'test1', main_sources,
          include_directories: include_dir,
          dependencies : gtkmm_dep,
          link_with: libtest1,
          install: true
          )
