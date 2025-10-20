# Vala Documen
## Introduction

Vala is a programming language using modern high level abstractions
without imposing additional runtime requirements and without using a
different ABI compared to applications and libraries written in C.

Vala uses the GObject type system and has additional code generation
routines that make targeting the GNOME stack simple. Vala has many other
uses where native binaries are required.

[Learn more about Vala](about)

## Sections

- [Installation Guide](installation-guide)
- [Tutorials](tutorials/)
- [Tooling](tooling/)
- [Contributor Guide](contributor-guide/)
- [Developer Guides](developer-guides/)
- [FAQ](faq)

## External Resources

- [API References (valadoc.org)](https://valadoc.org)
- [Reference Manual](https://gnome.pages.gitlab.gnome.org/vala/manual/index.html)
- [GNOME Developer Documentation](https://developer.gnome.org/documentation/)
- [elementary OS Developer Documentation](https://docs.elementary.io/develop)
- [Vala Compiler Repository](https://gitlab.gnome.org/GNOME/vala)
- [Vala Website](https://vala.dev)
- [Vala Project GNOME Wiki (Deprecated)](https://wiki.gnome.org/Projects/Vala)

## Community

- [Vala Community Links](https://vala.dev/#community)

## Contribute

- [View the source code of this documentation](https://github.com/vala-lang/vala-docs)

- apt install libgtk-3-dev valac meson 
using Gtk;
int main (string[] args) {
    Gtk.init (ref args);
    var window = new Window ();
    window.destroy.connect (Gtk.main_quit);
    window.show_all ();
    Gtk.main ();
    return 0;

}
Desktop Entry]
Name=uygulama-ornek
Comment=Example application
Exec=uygulama-ornek
Terminal=false
Type=Application
Icon=uygulama-ornek
Categories=System;
Keywords=uygulama,ornek
valac -o main main.vala --pkg gtk+-3.0
# veya şu şekilde de yapılabilir.
valac -C main.vala --pkg gtk+-3.0
gcc -c main.o main.c `pkg-config --cflags gtk+-3.0`
gcc -o main main.o `pkg-config --libs gtk+-3.0`
deps = [
    dependency('gtk+-3.0'),
]
executable('uygulama-ornek', sources, dependencies: deps, install: true)
# uygulama simgesi
install_data('icon.svg', install_dir: get_option('prefix') / 'share/icons/hicolor/scalable/apps/',rename: 'uygulama-ornek.svg')
# uygulama başlatıcısı
install_data('application.desktop', install_dir: get_option('prefix') / 'share/applications/',rename: 'org.uygulama.ornek.desktop')
project('uygulama-ornek', 'vala', 'c')
sources =  [
    'main.vala',
]
deps = [
    dependency('gtk+-3.0'),
]
executable('uygulama-ornek', sources, dependencies: deps, install: true)
install_data('icon.svg', install_dir: get_option('prefix') / 'share/icons/hicolor/scalable/apps/')
install_data('application.desktop', install_dir: get_option('prefix') / 'share/applications/',rename: 'org.uygulama.ornek.desktop')
