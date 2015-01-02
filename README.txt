****************************
*** GeneralUser GS v1.44 ***
***      1/27/2012       ***
****************************

There are different versions of GeneralUser GS, each with their own requirements and recommendations.

+---------------------+
| Live/Audigy version |
+---------------------+

The Live/Audigy version is designed for use with the following SoundFont-compatible sound hardware:

 <> Sound Blaster Live! family
 <> Sound Blaster Audigy family
 <> Sound Blaster Audigy 2/NX/ZS family
 <> Sound Blaster Audigy 4 family
 <> Sound Blaster X-Fi series (untested)
 <> E-MU APS
 
See the section below for installation instructions.

+--------------------+
| FluidSynth version |
+--------------------+

The FluidSynth version is tweaked for maximum compatibility when used with FluidSynth or Qsynth (which uses FluidSynth as its backend).  FluidSynth version 1.0.9 or later is recommended; earlier versions will not reproduce all of the instruments accurately.

+-------------------+
| MuseScore version |
+-------------------+

This version is customized for use with the MuseScore notation software, and has had the instrument balance adjusted for writing orchestral music.  Additionally, the default drum kit features an orchestral bass drum, snare drum and crash cymbal in place of the standard kit sounds.  The original standard drum kit has been renamed "Standard Kit 3" and is now the third preset on the percussion channel.

To install, open Musescore and go to Display -> Synthesizer.  Click the browse icon to the right of "SoundFont" and locate the GeneralUser SoundFont file.  For the best sound, set the following settings on the "Reverb" tab:
 <> Room Size: 0.85
 <> Damp: 0.26
 <> Width: 0.94
 <> Rev: set the slider about 55%
 <> Cho: 0
 <> Vol: 15

Open the included demo file in MuseScore: "GeneralUser Orchestral Example.mscz" and press play to hear the song.  You should notice a marked improvement over MuseScore's stock instrument sounds.  An orchestral template file is also provided with this download ("Full Orchestra.mscz").  Copy this into your MuseScore templates folder to use it (usually located in C:/Program Files/MuseScore/templates).  The instruments in the template have been panned to represent their proper stage positioning within an orchestra.

+-------------------+
| Softsynth version |
+-------------------+

The Softsynth version is modified for greater compatibility with other software synthesizers, particularly those that don't support all of the SoundFont 2.1 modulators, among other things.


*********************************************
**  NOTE: The remainder of this document   **
** applies only to the Live/Audigy version **
*********************************************

+---------------+
| Installation  |
| (Live/Audigy) |
+---------------+
To install GeneralUser GS on a Sound Blaster sound card under Windows, follow these steps:
  1) Open "Creative AudioHQ" (it should be in the "Creative" folder in your Start menu) and double-click on the "SoundFont" applet.  
  2) Select the "Options" tab.
  3) Set your SoundFont cache to at least 64 MB in size.
  4) Under "SoundFont Device" Select "XXX Synth A" where XXX is the name of your sound card. (NOTE: older driver versions do not feature this option, in which case, please ignore this step.)
  5) Select the "Configure Bank" tab.
  6) Click the existing bank in the bank stack (usually "[2GMGSMT Rev N++]") and click "Clear".  Your bank stack should now be empty.  Click the "Load" button and find "GeneralUser GS 1.4.sf2".  After selecting it, you should see "[GeneralUser GS 1.4]" in the bank stack window.
  7) If you were able to select "XXX Synth A" in step 4, then go back to step 4 and select "XXX Synth B".  Repeat steps 5 and 6 for synth B, then click close.

For GNU/Linux distributions, you can use the asfxload tool to load GeneralUser GS as the default GM bank.  I do not know how well the Linux X-Fi drivers work with SoundFonts, but I know the Live! and Audigy both work quite well using asfxload.

Installation on other cards or synths may vary, but will likely be a similar process.  Please refer to your sound card's documentation for help.


+-----------------------------+
| MIDI FX Setup (Live/Audigy) |
+-----------------------------+
GeneralUser GS will not sound correct without first customizing the MIDI reverb and chorus effects.  Without Reverb and Chorus effects, MIDI files will sound very dry.  Unfortunately, Creative sound cards are not set up by default to allow the use of these effects.  Reverb and Chorus is controlled by Creative's Environmental Audio technology (or EAX for short).

To set up Reverb and Chorus for MIDI, follow these steps:
  1) Open "Creative AudioHQ" and double-click on the "EAX Control Panel" applet (or "Environmental Audio" on some systems).
  2) Click the "Import Environment" button.  (HINT: it looks like a piece of paper with a red arrow pointing to it)
  3) Select the file "MIDI Playback EAX Preset-XXX.Aup" where XXX is your sound card and click "Open".  Unless you get an error message, the EAX preset should now be installed.  If you get an error message, go to step 4.  Otherwise, select "GeneralUser GS 1.4 MIDI Playback" from the audio effects drop-box at the top of the window, close the EAX control panel and move on to the Self-Test Mode (next section below).
  4) If the EAX preset fails to import, you have the following options:
     a)  Try importing another preset from the GeneralUser GS folder
     b)  See if a compatible EAX preset is available for download from my website: http://www.schristiancollins.com/generaluser.php
     c)  Create the EAX preset from scratch (not as hard as it sounds).  This will be necessary to provide the maximum sound quality from GeneralUser GS.  To create the EAX preset, follow the directions in "EAX Preset.txt".

NOTE #1: Setting the Reverb and Chorus effects for MIDI will interfere with EAX functionality in games.  If you want to play an EAX game, please go into the EAX Control Panel and select (No Effects) before launching the game.  When you want to play MIDI music or compose, change it back to "GeneralUser GS 1.4 MIDI Playback"

NOTE #2: If you are using an older version of the GeneralUser EAX preset, you will need to replace it with the new one.  Version 1.4 and later of GeneralUser GS uses 100% of the EAX preset's effects instead of only 20% in versions 1.39 and earlier.  As a result, version 1.43 will sound too "verby" with the old preset.  If you prefer using your own custom reverb/chorus settings, you may want to set the master sliders for both reverb and chorus to -12 dB to keep the sound from being drenched by the effects.

NOTE #3: Linux users will not have reverb/chorus effects available when playing through the Live/Audigy's built in SoundFont synth.  This is because as of this writing, those features haven't been incorporated into the ALSA drivers yet.  Linux users may prefer to use FluidSynth (Qsynth for GUI) to get reverb/chorus effects.


+----------------+
| Self-Test Mode |
+----------------+
To test the installation, double-click on "GUTest.mid" in the GeneralUser GS folder.  You should begin to hear a voice talking.  If you don't hear anything, verify that you installed the SoundFont correctly.  If the SoundFont is installed correctly and you still don't hear the voice, make sure the correct MIDI synth is set as the default MIDI device.  To do this, go into the Windows Control Panel and open the "Sounds and Audio Devices" applet (it's called "Multimedia" on older versions of Windows).  Select the "Audio" tab and make sure the default MIDI playback device is something like "SB Audigy Synth A" or "SB Live! MIDI synth".

Here is an explanation of the self test:
  "GeneralUser GS installed version 1.44" - tells what version is installed
  "Sample offset, supported/not supported" - some instruments use sample offset, but it isn't supported in older audio driver versions.  Lack of sample offset support will slightly decrease the realism of a few instruments.
  "Custom velocity scale, supported/not supported" - if supported, some instruments will respond differently to how hard you press the keys (example: Harpsichords and Organs), - if not supported, all instruments will respond the same, which may affect instrument balance somewhat.
  "Reverb, testing" - if you properly set up the custom EAX preset, you should hear the reverb effect when I say this.
  "Chorus, testing" - if you properly set up the custom EAX preset, you should hear the chorus effect when I say this.


+-------------+
| Odds & Ends |
+-------------+
Instrument list files are currently provided for Cakewalk (Windows) and Rosegarden (Linux) sequencers in the "instrument lists" folder.  If you create an instrument list for any other sequencers, please e-mail them to me at s_chriscollins@hotmail.com and I will include them in the next release package.

I have also provided some free MIDI files in the "demo MIDIs" folder for your listening enjoyment.  Please feel free to send me more of those as well :)


---------------------------------------------------
Q&A

Q: Why do I get an error when I try to import the EAX preset?
A: Because EAX presets made on one version of the EAX control panel are not compatible with others.  Try updating your audio card drivers and the EAX control panel by visiting http://www.soundblaster.com.

Q: Why did you increase the effects sensitivity in GeneralUser 1.4?
A: The two primary reasons are:
  1)  increased compatibility with non-SoundBlaster SoundFont hardware/software
  2)  improved signal-to-noise ratio (when the reverb master slider is set to maximum in the EAX Control Panel on some systems, it introduces noticeable hiss into the audio signal--when set to -12 dB instead, the noise is minimal)

Q: Where Can I find updates, and how can I contact you?
A: You can find updates to GeneralUser GS, the EAX preset and more of my SoundFonts at http://www.schristiancollins.com.  I can be reached at s_chriscollins@hotmail.com, but please use good judgement when asking questions--check your sound card's manual first.  I won't have time to answer every question that I receive.

Thank you!
-~Chris Collins
