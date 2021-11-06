project('A GTK4 Project',
        'c', # lang-name e.g. 'c', 'cpp', etc
        version: '1.0.alpha')

gnome = import('gnome')
gtk_dep = dependency('gtk4')
include_dir = include_directories('include')

subdir('src')

# SubDir's meson.build
gresource_xml = files('example-app.gresource.xml')
lib_sources = files('mainWindow.c')
main_sources = files('main.c')

resources = gnome.compile_resources('example-app-ui', gresource_xml)

libtest1 = library('test1', lib_sources,
                   include_directories: include_dir,
                   dependencies: gtk_dep)

executable('test1', main_sources, resources,
           include_directories: include_dir,
           dependencies : gtk_dep,
           link_with: libtest1,
           install: true)
