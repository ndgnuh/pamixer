======================================
pamixer: pulseaudio command line mixer
======================================

pamixer is like amixer but for pulseaudio. It can control the volume levels of the sinks.

Also, this project can provide you a small C++ library to control pulseaudio.


Features
--------

* Get the current volume of the default sink, the default source or a selected one by his id
* Set the volume for the default sink, the default source or any other device
* List the sinks
* List the sources
* Increase / Decrease the volume for a device (using gamma correction optionally)
* Mute or unmute a device

Dependencies
------------

* libpulse
* boost-program_options

You need the headers as well (“-dev” packages for Debian).

Debian users::

        sudo apt install --mark-auto libboost1.74-dev libpulse-dev libboost-program-options-dev

(Search for packages' name using ``apt-file search $file`` with ``$file`` being the header files included in the source code)

Installation
------------

* From source:

    * Get the source::

        git clone https://github.com/cdemoulins/pamixer.git

    * Compile::

        meson setup build
        meson compile -C build

    * And use it::

        ./build/pamixer --help

        Allowed options:
          -h [ --help ]         help message
          -v [ --version ]      print version info
          --sink arg            choose a different sink than the default
          --source arg          choose a different source than the default
          --default-source      select the default source
          --get-volume          get the current volume
          --get-volume-human    get the current volume percentage or the string "muted"
          --set-volume arg      set the volume
          -i [ --increase ] arg increase the volume
          -d [ --decrease ] arg decrease the volume
          -t [ --toggle-mute ]  switch between mute and unmute
          -m [ --mute ]         set mute
          --allow-boost         allow volume to go above 100%
          --set-limit arg       set a limit for the volume
          --gamma arg (=1)      increase/decrease using gamma correction e.g. 2.2
          -u [ --unmute ]       unset mute
          --get-mute            display true if the volume is mute, false otherwise
          --list-sinks          list the sinks
          --list-sources        list the sources

    * Or install it::

        meson install -C build

