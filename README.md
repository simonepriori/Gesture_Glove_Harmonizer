# GESTURE GLOVE HARMONIZER

The WebApp has the purpose of adding to the fundamental MIDI note some harmonics that are chosen from the user according to the movement of the hand through the use of the BBC micro:bit.
The sound is synthesized directly by the WebApp which has its own timbra library.  
The WebApp can be also used without the connection of the BBC micro:bit.


## Prequisites:
- Ultimate Gesture GLOVE white version (aka BBC micro:bit)
- MIDI Keyboard

## Running the app
To properly interface with the WebApp before opening it the MIDI keyboard must be connected to the PC. If we want to disconnect the keyboard we need to reload again the page. 
After having connected the MIDI keyboard and opened the WebApp, it is possible to proceed connecting the BBC micro:bit using bluetooth.
Press the key 'PAIR' to select the device to be connected: near that key the status of the BBC micro:bit device is shown.

When the BBC micro:bit is connected, the user can choose the harmonics he wants to add to the fundamental, according to the movement of the hand.
'LEFT' and 'RIGHT' are referred to the BBC micro:bit roll movement
'UP' and 'DOWN'are referred to the BBC micro:bit pitch movement
Each 'OCTAVE' button below each of the movement button allow the user to choose to which octave the harmonization above is referred:
-1 for the lower octave, 0 for the actual octave, 1 for the upper octave.

In the lower screen it is possible to modify the volumes of the master ('MASTER') and the two selectable harmonics: 'L/R HARM' (roll)
e 'U/D HARM' (pitch). Therefore is possible to select maximum two harmonics at time.

It is possible to change the timbre of the sound with the tools library pressing the key 'SOUND'.
It is possible to modify the Attack Decay Sustain Release (ADSR) of each musical instrument using the sliders
under the ADSR.

In the lower right canvas it is represented the spectrum of the audio signal generated by the WebApp.

## Framework used
- https://threejs.org/
- https://vuejs.org/

## PROMO Video (in italian)
https://1drv.ms/v/s!AnnhkH9OXjhOh91YWXE5xGYWvUX_gg
