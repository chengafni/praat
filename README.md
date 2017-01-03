# Plugins for Praat

* This repository contains some plugins for Praat. Each plugin adds functions to Praat's menus.
* To install a plugin, download its zip file and unzip it in your Praat's preference folder. If you don't know where Praat's preference folder is located, download *praatPrefDir.praat* and run it in Praat: on the *Praat* menu select *Open Praat script...*, select *praatPrefDir.praat* and click *Run* in the *Run* menu.
* Once a plugin folder is placed in Praat's preference folder, starting Praat will automatically add the functions included in the plugin to the appropriate menus of Praat.

List of plugins:
## 1) Spectral emphasis: 
* Download: plugin_SpectralEmphasis.zip
* Calculates the intensity (in dB) contained in the high-frequency band of a sound signal. This is accomplished by low-pass filtering the sound signal and calculating the intensity lost in the process (See: Traunmüller and Eriksson, 2000). This measure is used in voice quality analysis.
* The plugin adds the command *Get spectral emphasis* to the following menus: 
    * Objects window: at the bottom of the *Query* menu for Sound objects.
    * Sound and TextGrid editors: at the bottom of the *Spectrum* menu.

## 2) Mean Intensity slope
* Download: plugin_IntensitySlope.zip
* Calculates the mean slope of the intensity curve (in dB/s).
* Two methods: 
    1. raw: the direction of local changes in the intensity curve is taken into account; 
    2. aboslute: the direction of local changes in the intensity curve is disregarded.
* The plugin adds the command *Get mean slope* to the following menus: 
   * Objects window: at the bottom of the *Query* menu for Intensity objects.
   * Sound and TextGrid editors: at the bottom of the *Intensity* menu.
