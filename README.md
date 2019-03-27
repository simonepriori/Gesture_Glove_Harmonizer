# GESTURE GLOVE HARMONIZER

The WebApp has the purpose of adding to the fundamental MIDI note some harmonics that are chosen from the user according to the movement of the hand through the use of the BBC micro:bit.
The sound is synthesized directly by the WebApp which has its own timbra library.  
The WebApp can be also used without the connection of the BBC micro:bit.


### Prequisites:
- Ultimate Gesture GLOVE white version (aka BBC micro:bit)
- MIDI Keyboard

### Installing:

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

## Components
### Audio part
- MIDI sound generation
- Audio synthesis part

### Graphic part
- Vue JS components
  - ADSR scheme
- Three JS part
- Frenquency peaks canvas

### BBC micro:bit bluetooth communication
From 2017,thanks to the Web Bluetooth API of Google Chrome it is possible to connect to an application a BLE (Bluetooth Low Energy) device reading information from the it and receivings notifications when certain values change. The connection to the device is only possible as a  result of a voluntary action by the user (as in this case a click on the proper button on the graphical interface).
- https://www.html.it/articoli/introduzione-alle-web-bluetooth-api/
In particular, in order to transmit data to handle the harmonics to be reproduced, the accellerometer service has been used. It is worth mentioning the fact that a BLE service eats too much RAM memory to let the button service from be used simultaneously with it without causing an overflow error. This would have prevented activating and deactivating the microprocessor without the need of shutting it down and pairing it again. Anyway accellerometer values on the three cartesian axis (properly converted into roll and pitch informations) are sufficient for our task.The bluetooth code pairing implementation has been developed by Bitty Software:
- http://www.bittysoftware.com/downloads.html
The code executed by the BBC micro:bit can be found here:
- https://makecode.microbit.org/_e9J5fpT64DJ5

## Future implementations
One next step will be to integrate in this project a client-side JavaScript implementation, in a browser environment, of the Pitch shifting operation for a human voice recorded directly from a live input such as a microphone. Pitch shifting is a widely used operation, as an example, in all major commercial and open source Digital Audio Workstations and Mixing Softwares. There are algorithms that work in time domain, like Overlap and Add (OLA), Waveform Similarity based OLA (WSOLA) and delay line modulation, and others that work in the frequency domain, like the Phase Vocoder and Spectral Modelling. At the moment, ScriptProcessorNodes and AudioWorkers are operating on the time domain buffer data, on which FFT is computed. For what concerns frequency operations, like pitch shifting, the burden of the computational cost is due to the javascript implementation of FFT. A well-done improvement of this work would surely consist in analyzing computational costs and existence of audio artefacts in the implementation of such algorithms in the Web-audio-API itself. A simple pitch detection algorithm for voice input, as a starting point, is shown hereafter. 
- Code:
https://github.com/manukko/pitch_detection_future_work?fbclid=IwAR1jirUJ5YyZACAgVgIpi74W2hIuCxlgXkoYg0ED2AnhgUOZZNeTjbY_OXQ
- Try it:
https://manukko.github.io/pitch_detection_future_work/?fbclid=IwAR0VBmscqbVY3mNi3FPgexqmfSUKxLOySTJZA2QutbPY_liTolFjLiIYsko

## Framework used
- https://threejs.org/
- https://vuejs.org/

## PROMO Video (in italian)
https://1drv.ms/v/s!AnnhkH9OXjhOh91YWXE5xGYWvUX_gg
