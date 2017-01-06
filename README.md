# Plugins for Praat

* This repository contains some plugins for Praat. Each plugin adds functions to Praat's menus.
* To install a plugin, download its zip file and unzip it in your Praat's preference folder. If you don't know where Praat's preference folder is located, download *praatPrefDir.praat* and run it in Praat: on the *Praat* menu select *Open Praat script...*, select *praatPrefDir.praat* and click *Run* in the *Run* menu.
* Once a plugin folder is placed in Praat's preference folder, starting Praat will automatically add the functions included in the plugin to the appropriate menus of Praat.

List of plugins:
## 1) Spectral emphasis 
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

## 3) Complete analysis
* Download: plugin_CompleteAnalysis.zip
* An extensive acoustic analysis of Sound objects in the Sound editor (non-annotated sounds) or TextGrid editor (annotated sounds) of Praat.

### Description
* This script performs an extensive acoustic analysis of Sound objects in the Sound editor (non-annotated sounds) or TextGrid editor (annotated sounds) of Praat.
* It can automatically measure any number of acoustic parameters for all intervals in a given tier and also run on all TextGrid tiers.
* The result is a table containing the list of intervals and the values of the measured parameters. The name of the tier, the start time and duration of each interval are also included. The other measured parameters are taken from an external text file.
* The script is distributed as part of a plugin named "plugin_CompleteAnalysis". When the plugin is installed, it adds the command "Complete analysis" at the bottom of the "Query" menu of the Sound and TextGrid editors.

### Requirements
* The script requires a Sound (and optionally, a TextGrid) object open in the editor. In addition, the script requires three tabulated text files, which should be placed in the same folder as the script:
1. settings.txt: the file contains commands that adjust the settings of various parts of the editor (e.g., pitch floor and ceiling, number of formants, etc.). These settings will apply automatically before the analysis starts.
2. objects.txt: the file contains the commands that generate objects during the analysis (e.g., Spectrum). The acoustic parameters are obtained by querying these obejcts.
3. commands.txt: the file contains the query commands for the various acoustic paramteres.
* The above mentioned text files are distributed alongside the script, as part of the plugin. They can be edited freely (e.g., adding/removing commands, changing the input arguments of commands). The plugin also contains an Excel file named "Sound editor tables.xls", which contains these tables as separate sheets. This provides an easy way to edit the tables (after editing the file, the modified table should be saved as a Tab-delimited text file).

### Usage
* Select a part of the sound (e.g., some interval in a tier of interest, and run the script.
* You'll be presented with several dialog boxes:
1. Type of analysis: contains the following checkboxes:
   - "automatic": analyze all intervals in the selected tier. If unchecked, only the selected interval will be analyzed.
   - "all tiers": analyze all tiers in the TextGrid. If unchecked, only the selected tier will be analyzed.
	- "continued": add rows to an existing analysis table (e.g., to add previously unanalyzed tiers).
	- "appended": add columns to an existing analysis table (e.g., to add previously unqueried parameters).
2. If either "continued" or "appended" checkboxes was checked in the first dialog, you will be asked whether to load an existing analysis table from disk. If the loadTable checkbox is checked, you will be prompted to supply the file containing the results of the previous analysis. If the checkbox is unchecked, the script assumes that a Table object named "analysis" is present in Praat's objects list.
3. you will be asked if you want to select which objects to query. If the "select objects" checkbox is checked you will be presented with a list of objects. Uncheck the objects you don't want to query.
4. you will be asked if you want to select which queries to perform. If the "select queries" checkbox is checked you will be presented with one or more lists of parameters. If you unchecked one or more objects in the previous step, only the parameters relevant to the objects you selected will be displayed. Uncheck the parameters you don't want to query.

* Note: if you continue previous analysis, make sure that all the checked parameters are listed in the analysis table. If you want to query both new intervals and parameters check both the 'continued' and 'appended' checkboxes.

* The analysis will be performed and the results will be entered into a table object named "analysis".
