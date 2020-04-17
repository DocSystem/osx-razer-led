# osx-razer-led
Command-line application to control lights on Razer Blade that are running a Hackintosh (macOS on a non-Apple device). Successfully tested so far on a Razer Blade Stealth (Late 2017) and Razer Blade 15 Base (2019). The driver should work with older and new Razer laptops as well. It supports various effects on the keyboard and the ability to turn the monitor Razer logo on and off.

This simple application builds on the porting work by @kprinssu and their https://github.com/kprinssu/osx-razer-blade project. The Razer driver was adapted from the Linux project, https://github.com/terrycain/razer-drivers/.

This fork of [osx-razer-led](https://github.com/dylanparker/osx-razer-led) is not based on the original [osx-razer-blade](https://github.com/kprinssu/osx-razer-blade) but on my own [fork](https://github.com/DocSystem/osx-razer-blade) that adds support for the latest Razer drivers.

Only the Xcode command-line tools are needed to build and run this project. Install Xcode command-line tools by running:

    xcode-select --install

Usage:

1. Clone the repo
2. Build the project by typing `make`
3. Run the `osx-razer-led` program to get the effect you want.

Currently supported effects:

```
usage: osx-razer-led <command> [options]
Where <command> is one of:

   info                        # Display some keyboard information.

   static                      # All keys green (default)
   static {red|blue|white}     # All keys to a preset colour
   static <R G B>              # All keys to a custom colour

   breathe                     # Throb with random colours
   breathe <R G B>             # Throb with a custom single colour
   breathe <R G B> <R G B>     # Throb with two custom colours

   starlight                   # Twinkling green stars
   starlight <speed>           # Set twinkle speed: 1,2,3
   starlight <speed> <R G B>   # Custom twinkle speed and colour.

   reactive                    # Keys light green and fade when typed.
   reactive <speed> <R G B>    # Custom react speed and colour.

   spectrum                    # Keys cycle through colour spectrum.

   wave {left|right}           # Spectrum coloured wave.

   logo                        # Display the current logo state.
   logo {off|on}               # Turn the back logo off or on.

   fnkey {off|on}              # Use 'fn' key to access F1-F12 keys.

   brightness                  # Display the current brightness value.
   brightness <value>          # Sets the brightness to value: 0 - 255
   brightness {up|down}        # Increases or decreases the brightness

Note: <R G B> custom colours are specified with three numbers representing
RED, GREEN and BLUE. Each number ranges from 0 (0%) to 255 (100%).

   eg. osx-razer-led static 255 100 50
   eg. osx-razer-led breathe 255 0 0 0 0 255
   eg. osx-razer-led starlight 1 255 255 255

Note: <speed> values range from 1 to 3. 1 is fast, 3 is slow.
```


This project unless otherwise stated in the file is licensed under the GPLv2 license.
