---
URL: https://www.bespokesynth.com/docs/index.html#video
thumbnail: 
site: "[[]]"
date: 2024-08-23T14:35:42
duration: 49
topics: 
done: false
cover: 
---
[[Read it Later|Read it Later]] [[../../../01 Maps/Themes/Article|Article]] 
# Bespoke Synth Reference

Description::   

## overview video

Here is a video detailing basic usage of Bespoke, including a bunch of less-obvious shortcuts and workflow features.

There are some things in this video that are slightly out of date (I should make a new video!), but there is still plenty of useful information in there.

## basics

Navigation \* space bar + move mouse to pan, or right-click drag in empty space \* space bar + mousewheel/trackpad-scroll to zoom, or scroll in empty space \* if you get lost, press ~ to bring up the console, type "home", and press enter to reset to the initial position and zoom \* if you have enabled the minimap in the settings, you can click on the minimap to directly go to a location -at the bottom of the mimimap you can click on 9 bookmark buttons -hold shift while clicking will store your current location into that bookmark button -use shift+\[num\] to go to the specified bookmark Creating Modules \* drag items out of the top bar menus OR \* right-click and select from the popup menu OR \* right-click and start typing the name of the module you want, then drag it out of the popup menu OR \* hold the first letter of a module and drag them out of the popup menu OR \* drag a cable into space and spawn a connecting module from the popup \* to delete a module, lasso select + backspace OR use the triangle menu and choose "delete module" \* to duplicate a module, hold alt/option and drag from the title bar Patching \* drag the circle from the bottom of a module to the target OR click the circle then click the target to patch \* drag a cable and press backspace to unpatch \* hold shift while grabbing a patch cable circle to split \* hold shift while releasing a patch cable on a target to insert \* while holding shift, drag a module by the title bar and touch its circle to another module, or the mouse pointer to another module's circle, to quick patch UI Controls \* click or drag a slider to adjust its value \* hold shift to fine-tune \* while hovered: -use mousewheel/trackpad-scroll to adjust (shift to fine-tune) -type a value into a slider (such as 1.5) and press enter -type an expression into a slider (such as 1/16 or +=10) and press enter -press up or down to increase the value by 1 (hold shift for .01) -press \[ or \] to halve or double the value -press \\ to reset to the initial value \* hold alt/option and drag to adjust slew amount (smoothing) \* right click a slider to add an LFO -click and drag a green modulated slider vertically to adjust the modulation min, and horizontally to adjust the modulation max \* hold ctrl/command and click the lower or upper half of a slider to adjust that slider's minimum or maximum value, to give it increased or reduced range (warning! increasing range can lead to unpredictable behavior in some cases) \* press tab to cycle through controls on a module \* press ctrl/command+arrows to navigate around controls on a module Saving \* "write audio" button: write the last 30 minutes of audio to the /data/recordings folder, perfect for making sure you don't miss any cool moments \* "save state" button: save the current layout to a file. shortcut: ctrl-s \* "load state" button: load previously saved layouts. shortcut: ctrl-l Key Commands \* ctrl/command-'s': save \* ctrl/command-'l': load \* shift-'p': pause audio processing. this will stop all audio output. press shift-'p' again to resume \* F2: toggle displaying all ADSR controls as sliders

## instruments

  
**circlesequencer**  
![](https://www.bespokesynth.com/docs/screenshots/circlesequencer.png)  
polyrhythmic sequencer that displays a loop as a circle

**length\***: number of steps in this ring  
**note\***: pitch to use for this ring  
**offset\***: timing offset for this ring

  
**drumsequencer**  
![](https://www.bespokesynth.com/docs/screenshots/drumsequencer.png)  
step sequencer intended for drums. hold shift when dragging on the grid to adjust step velocity.

**r lock\***: lock this row so it doesn't get randomized  
**repeat**: repeat input notes at this rate  
**offsets**: show "offsets" sliders  
**column**: current column, to use for visualizing the step on a midi controller  
**randomize**: randomize the sequence  
**clear**: clear sequence  
**measures**: length of the sequence in measures  
**metastep**: patch a grid in here from a "midicontroller" module to control the "meta step". I forget what this does. oops.  
**r den**: density of the randomizer output. the higher this is, the busier the random output will be.  
**r amt**: the chance that each step will change when being randomized. low values will only change a small amount of the sequence, high values will replace more of the sequence.  
**step**: length of each step  
**grid**: patch a grid in here from a "midicontroller" module  
**yoff**: vertical offset for grid controller's view of the pattern  
**velocity**: patch a grid in here from a "midicontroller" module to control the velocity  
**rowpitch\***: output pitch for this row  
**vel**: velocity to use when setting a step  
**random\***: randomize this row  
**<**: shift whole pattern one step earlier  
**offset\***: shift row forward/backward in time. try making your snares a little early, your hats a little late, etc.  
**\>**: shift whole pattern one step later

accepts:

pulses notes  
**fouronthefloor**  
![](https://www.bespokesynth.com/docs/screenshots/fouronthefloor.png)  
sends note 0 every beat, to trigger a kick drum

**two**: sends note only every two beats

  
**gridkeyboard**  
![](https://www.bespokesynth.com/docs/screenshots/gridkeyboard.png)  
grid-based keyboard, intended primarily for 64-pad grid controllers

**layout**: keyboard style  
**p.root**: for chorder, make root note always play  
**arrangement**: what style of layout should we use?  
**grid**: patch a grid in here from a "midicontroller" module  
**octave**: base octave  
**latch**: latch key presses, so you press once to play a note, and press again to release a note  
**ch.latch**: latch chord button presses

  
**keyboarddisplay**  
![](https://www.bespokesynth.com/docs/screenshots/keyboarddisplay.png)  
displays input notes on a keyboard, and allows you to click the keyboard to create notes

accepts:

notes  
**m185sequencer**  
![](https://www.bespokesynth.com/docs/screenshots/m185sequencer.png)  
sequencer using the unique paradigm of the m185 or intellijel metropolis

**gate\***: behavior for each row: "repeat" plays every step, "once" plays just the first step, "hold" holds across all steps, "rest" plays no steps  
**pitch\***: pitch to use for this row  
**interval**: interval per step  
**pulses\***: number of steps this row should last  
**reset step**: resets counter to first step

accepts:

pulses  
**midicontroller**  
![](https://www.bespokesynth.com/docs/screenshots/midicontroller.png)  
get midi input from external devices. to get a nice display in the "layout" view, create a .json file with the same name as your controller to describe your controller's layout, and place it in your "data/controllers" directory. look at the other files in that directory for examples.

**control**: pitch or control to refer to  
**feedback**: which cc or note should we send the feedback to?  
**blink**: when the targeted control is enabled, send alternating on/off messages, to blink the associated LED  
**controltype**: how this control should modify the target. -slider: set the value interpolated between "midi off" and "midi on" to the slider's value -set: set the specified value directly when this button is pressed -release: set the specified value directly when this button is released -toggle: toggle the control's value to on/off when this button is pressed -direct: set the control to the literal midi input value  
**increment**: when "controltype" is "set" or "release", the targeted control is incremented by this amount (and the "value" field is ignored). when "controltype" is "slider", the targeted control is changed by this amount in the direction the control was changed (this setting is useful for "infinite encoders")  
**scale**: should the output of this midi slider be scaled between "midi off" and "midi on"?  
**layout**: which layout file should we use for this controller? these can be created in your Documents/BespokeSynth/controllers folder.  
**messagetype**: type of midi message  
**add**: add a mapping manually  
**midi on**: the upper end of the midi range. send this value when the targeted control is on. if "scale" is enabled, this also controls the upper end of the slider range, and you can set midi off to be higher than midi on to reverse a slider's direction.  
**osc input port**: port to use for osccontroller input  
**channel**: which channel to pay attention to  
**midi off**: the lower end of the midi range. send this value when the targeted control is off. if "scale" is enabled, this also controls the lower end of the slider range, and you can set midi off to be higher than midi on to reverse a slider's direction.  
**pageless**: should this connection work across all pages of the midicontroller?  
**path**: path to the control that should be affected. you can also enter "hover" here, to affect whichever control the mouse is hovering over.  
**bind (hold shift)**: when this is enabled, you can map a midi input to a UI control by hovering over a UI control, holding shift, and then using desired midi input  
**copy**: duplicate this connection  
**monome**: which monome should we use?  
**mappingdisplay**: which mapping view to see  
**x** : delete this connection  
**controller**: midi device to use  
**value**: the value to set  
**twoway**: should we send feedback to the controller? (to control the LEDs associated with the button/knob)  
**page**: select which page of midi controls to use. each page acts like an independent midi controller, so you can use pages to allow one midi controller to switch between controlling many things

  
**notecanvas**  
![](https://www.bespokesynth.com/docs/screenshots/notecanvas.png)  
looping note roll

**scrollv**: vertical scrollbar  
**canvas**: canvas of notes. canvas controls: -shift-click to add a note -hold shift and drag a note to duplicate -hold alt to drag a note without snapping -hold ctrl while dragging to snap to an interval -hold shift and scroll to zoom -hold alt and grab empty space to move slide the canvas view -hold ctrl and grab empty space to zoom the canvas view  
**measures**: loop length  
**drag mode**: direction that elements can be dragged  
**view rows**: number of visible rows  
**loadtrack**: which track number to import when using "load midi"  
**timeline**: control loop points  
**clear**: delete all elements  
**interval**: interval to quantize to  
**play**: play notes on canvas  
**quantize**: quantize selected notes to interval  
**save midi**: export canvas contents to a midi file  
**load midi**: import canvas contents from a midi file  
**rec**: record input notes to canvas  
**show chord intervals**: show brackets to indicate chord relationships  
**free rec**: enable record mode, and extend canvas if we reach the end  
**scrollh**: horizontal scrollbar  
**delete**: delete highlighted elements

accepts:

notes  
**notechain**  
![](https://www.bespokesynth.com/docs/screenshots/notechain.png)  
trigger a note, followed by a pulse to trigger another note after a delay

**duration**: duration of note, in measures  
**trigger**: play note for this chain node  
**pitch**: pitch to play  
**velocity**: velocity for note  
**next**: interval until sending pulse

accepts:

pulses  
**notecounter**  
![](https://www.bespokesynth.com/docs/screenshots/notecounter.png)  
advance through pitches sequentially. useful for driving the "notesequencer" or "drumsequencer" modules.

**interval**: rate to advance  
**random**: output random pitches within the range, rather than sequential  
**sync**: if the output pitch should be synchronized to the global transport  
**start**: pitch at the start of the sequence  
**length**: length of the sequence  
**div**: measure division, when using "div" as the interval

accepts:

pulses  
**notecreator**  
![](https://www.bespokesynth.com/docs/screenshots/notecreator.png)  
create a one-off note

**duration**: note length when "trigger" button is used  
**on**: turn on to start note, turn off to end note  
**trigger**: press to trigger note for specified duration  
**velocity**: note velocity  
**pitch**: output note pitch

accepts:

pulses  
**notelooper**  
![](https://www.bespokesynth.com/docs/screenshots/notelooper.png)  
note loop recorder with overdubbing and replacement functionality

**canvas**: canvas of recorded notes  
**load\***: restore pattern  
**clear**: clear pattern  
**del/mute**: if "write" is enabled, erase notes as the playhead passes over them. otherwise, just mute them.  
**write**: should input should be recorded?  
**store\***: save pattern  
**num bars**: set loop length in measures

accepts:

notes  
**notesequencer**  
![](https://www.bespokesynth.com/docs/screenshots/notesequencer.png)  
looping sequence of notes at an interval. pair with a "pulser" module for more interesting step control. hold "shift" to adjust step length.

**len\***: length for this column  
**random**: randomize pitch, length, and velocity of all steps.  
**y offset**: y offset of attached grid controller  
**pitch**: randomize pitches in the sequence. hold shift to constrain the randomization to only pick roots and fifths.  
**rand vel density**: when clicking the random velocity button, what are the chances that a step should have a note?  
**x offset**: x offset of attached grid controller  
**rand pitch chance**: when clicking the random pitch button, what is the chance that a step gets changed?  
**rand vel chance**: when clicking the random velocity button, what is the chance that a step gets changed?  
**tone\***: pitch for this column  
**rand len range**: when clicking the random length button, how much will the length change?  
**rand len chance**: when clicking the random length button, what is the chance that a step gets changed?  
**vel**: randomize the velocity of each step's note.  
**<**: shift the sequence to the left  
**\>**: shift the sequence to the right  
**vel\***: velocity for this column  
**len**: randomize the length of each step's note.  
**grid**: patch a grid in here from a "midicontroller" module  
**loop reset**: when sequence loops, reset to here instead. send a "downbeat"-style message from a pulser to restart the sequence from the first step.  
**octave**: octave of the bottom pitch of this sequence  
**notemode**: which set of pitches should the rows represent?  
**clear**: clear all steps  
**interval**: note length  
**rand pitch variety**: how many different random pitches should we generate?  
**length**: length that the sequence below should play. the overall grid length can be changed by adjusting "gridsteps" in the triangle menu.

accepts:

pulses notes  
**notesinger**  
![](https://www.bespokesynth.com/docs/screenshots/notesinger.png)  
output a note based on a detected pitch

**oct**: octave to adjust output pitch by

accepts:

audio  
**playsequencer**  
![](https://www.bespokesynth.com/docs/screenshots/playsequencer.png)  
drum sequencer that allows you to punch in to record and overdub steps, inspired by the pulsar-23 drum machine

**load\***: load the sequence stored in this slot  
**link columns**: if the mute/delete control should be shared across the entire column  
**interval**: the step size  
**measures**: the loop length  
**write**: if the current input should be written to the sequence. this will also delete steps if mute/delete is enabled for this row  
**note repeat**: if held notes should repeat every step  
**grid**: patch a grid in here from a "midicontroller" module  
**mute/delete\***: if write is disabled, mute this row. if write is enabled, clear the steps as the playhead passes them  
**store\***: store the current sequence to this slot

accepts:

notes  
**polyrhythms**  
![](https://www.bespokesynth.com/docs/screenshots/polyrhythms.png)  
looping sequence with lines on different divisions

**length\***: number of steps for this line  
**note\***: pitch to use for this line

  
**randomnote**  
![](https://www.bespokesynth.com/docs/screenshots/randomnote.png)  
play a note at a given interval with a random chance

**probability**: the chance that a note will play each interval  
**skip**: after a note plays, don't play a note the next n-1 times that it would have played  
**interval**: the note length  
**offset**: the amount of time to offset playback within the interval  
**pitch**: the pitch to use  
**velocity**: the velocity to use

  
**slidersequencer**  
![](https://www.bespokesynth.com/docs/screenshots/slidersequencer.png)  
trigger notes along a continuous timeline

**division**: rate to progress  
**note\***: pitch for this element  
**playing\***: is this element playing?  
**vel\***: velocity of this element  
**time\***: time to trigger this element

## note effects

  
**arpeggiator**  
![](https://www.bespokesynth.com/docs/screenshots/arpeggiator.png)  
arpeggiates held notes. there are several vestigial features in this module that should be cleaned up.

**step**: direction and distance to step through arpeggiation. a value of zero is "pingpong".  
**interval**: arpeggiation rate  
**octaves**: how many octaves to step through

accepts:

notes  
**capo**  
![](https://www.bespokesynth.com/docs/screenshots/capo.png)  
shifts incoming notes by semitones

**capo**: number of semitones to shift  
**retrigger**: immediately replay current notes when changing the capo amount  
**diatonic**: should we keep transposed notes in the scale?

accepts:

notes  
**chorddisplayer**  
![](https://www.bespokesynth.com/docs/screenshots/chorddisplayer.png)  
display which chord is playing, in the context of the current scale

accepts:

notes  
**chorder**  
![](https://www.bespokesynth.com/docs/screenshots/chorder.png)  
takes an incoming pitch and plays additional notes to form chords

**inversion**: inversion presets  
**chord**: chord presets  
**diatonic**: should the grid be chromatic, or locked to the scale only?

accepts:

notes  
**chordholder**  
![](https://www.bespokesynth.com/docs/screenshots/chordholder.png)  
keeps any notes pressed at the same time sustaining, until new notes are pressed

**pulse to play**: when enabled, input notes aren't played immediately, but instead wait for an input pulse before playing  
**stop**: stop notes from playing

accepts:

pulses notes  
**gridnotedisplayer**  
![](https://www.bespokesynth.com/docs/screenshots/gridnotedisplayer.png)  
use with a gridkeyboard to display currently playing notes, to visualize chords, arpeggiation, etc.

accepts:

notes  
**midicc**  
![](https://www.bespokesynth.com/docs/screenshots/midicc.png)  
outputs midi control change messages to route to a "midioutput" module

**control**: CC control number  
**value**: outputs a CC value when this changes

accepts:

notes  
**midioutput**  
![](https://www.bespokesynth.com/docs/screenshots/midioutput.png)  
send midi to an external destination, such as hardware or other software

**controller**: where to send midi to

accepts:

notes  
**modulationvizualizer**  
![](https://www.bespokesynth.com/docs/screenshots/modulationvizualizer.png)  
display MPE modulation values for notes

accepts:

notes  
**modwheel**  
![](https://www.bespokesynth.com/docs/screenshots/modwheel.png)  
adds an expression value to a note

**modwheel**: expression level

accepts:

notes  
**modwheeltopressure**  
![](https://www.bespokesynth.com/docs/screenshots/modwheeltopressure.png)  
swaps expression input to midi pressure in the output

accepts:

notes  
**modwheeltovibrato**  
![](https://www.bespokesynth.com/docs/screenshots/modwheeltovibrato.png)  
convert note mod wheel input rhythmic pitch bend

**vibrato**: amount of pitch bend  
**vibinterval**: rate of vibrato

accepts:

notes  
**mpesmoother**  
![](https://www.bespokesynth.com/docs/screenshots/mpesmoother.png)  
smooth out MPE parameters

**modwheel**: amount to smooth incoming modwheel  
**pressure**: amount to smooth incoming pressure  
**pitch**: amount to smooth incoming pitchbend

accepts:

notes  
**mpetweaker**  
![](https://www.bespokesynth.com/docs/screenshots/mpetweaker.png)  
adjust incoming MPE modulation values

**pressure mult**: amount to multiply incoming pressure  
**modwheel offset**: amount to offset incoming modwheel  
**pitchbend mult**: amount to multiply incoming pitchbend  
**pitchbend offset**: amount to offset incoming pitchbend  
**modwheel mult**: amount to multiply incoming modwheel  
**pressure offset**: amount to offset incoming pressure

accepts:

notes  
**notechance**  
![](https://www.bespokesynth.com/docs/screenshots/notechance.png)  
randomly allow notes through

**\***: generate a new random seed  
**beat length**: restart the deterministic random sequence at this interval  
**deterministic**: allow for randomness to be repeated over an interval  
**chance**: probability that a note is allowed  
**seed**: number that determines the random sequence  
**<**: go to next seed

accepts:

notes  
**notedelayer**  
![](https://www.bespokesynth.com/docs/screenshots/notedelayer.png)  
delay input notes by a specified amount

**delay**: amount of time to delay, in measures

accepts:

notes  
**notedisplayer**  
![](https://www.bespokesynth.com/docs/screenshots/notedisplayer.png)  
show input note info

accepts:

notes  
**noteduration**  
![](https://www.bespokesynth.com/docs/screenshots/noteduration.png)  
sets the length a note will play, ignoring the note-off message

**duration**: length of the note in measures

accepts:

notes  
**noteecho**  
![](https://www.bespokesynth.com/docs/screenshots/noteecho.png)  
output incoming notes at specified delays

**delay \***: amount of time to delay this output, in measures

accepts:

notes  
**noteexpression**  
![](https://www.bespokesynth.com/docs/screenshots/noteexpression.png)  
control where notes are routed based upon evaluated expressions. the variable "p" represents pitch, and "v" represents velocity

**expression\***: expression to evaluate for this cable. example expression to route notes with pitch greater than 80 and velocity less than 60: "p > 80 && v < 60"

accepts:

notes  
**notefilter**  
![](https://www.bespokesynth.com/docs/screenshots/notefilter.png)  
only allow a certain pitches through

accepts:

notes  
**noteflusher**  
![](https://www.bespokesynth.com/docs/screenshots/noteflusher.png)  
send a note-off for all notes

**flush**: click to flush notes

accepts:

notes  
**notegate**  
![](https://www.bespokesynth.com/docs/screenshots/notegate.png)  
allow or disallow notes to pass through

**open**: if notes are allowed to pass

accepts:

notes  
**notehocket**  
![](https://www.bespokesynth.com/docs/screenshots/notehocket.png)  
sends notes to random destinations

**weight \***: chance that note goes to this destination  
**\***: generate a new random seed  
**seed**: number that determines the random sequence  
**<**: go to next seed  
**beat length**: restart the deterministic random sequence at this interval

accepts:

notes  
**notehumanizer**  
![](https://www.bespokesynth.com/docs/screenshots/notehumanizer.png)  
add randomness to timing and velocity

**velocity**: amount of velocity randomness  
**time**: amount of timing randomness, in milliseconds.

accepts:

notes  
**notelatch**  
![](https://www.bespokesynth.com/docs/screenshots/notelatch.png)  
use note on messages to toggle notes on and off

accepts:

notes  
**noteoctaver**  
![](https://www.bespokesynth.com/docs/screenshots/noteoctaver.png)  
transpose a note by octaves

**retrigger**: immediately replay current notes when changing the transpose amount  
**octave**: number of octaves to raise or lower

accepts:

notes  
**notepanalternator**  
![](https://www.bespokesynth.com/docs/screenshots/notepanalternator.png)  
sets a note's pan, alternating between two values, for the internal synths that support panned notes

**two**: pan position, .5 is centered  
**one**: pan position, .5 is centered

accepts:

notes  
**notepanner**  
![](https://www.bespokesynth.com/docs/screenshots/notepanner.png)  
sets a note's pan, for the internal synths that support panned notes

**pan**: pan position, .5 is centered

accepts:

notes  
**notepanrandom**  
![](https://www.bespokesynth.com/docs/screenshots/notepanrandom.png)  
sets a note's pan to random values, for the internal synths that support panned notes

**spread**: amount of randomness  
**center**: center pan position

accepts:

notes  
**noterangefilter**  
![](https://www.bespokesynth.com/docs/screenshots/noterangefilter.png)  
only allows notes through within a certain pitch range

**wrap**: instead of rejecting notes outside of this range, should we wrap them to the range instead?  
**max**: maximum pitch allowed  
**min**: minimum pitch allowed

accepts:

notes  
**noteratchet**  
![](https://www.bespokesynth.com/docs/screenshots/noteratchet.png)  
rapidly repeat an input note over a duration

**duration**: total length of time repeats should last  
**skip first**: don't replay input note. this allows you to more easily separate the initial note from the ratcheted notes.  
**subdivision**: length of each repeat

accepts:

notes  
**noterouter**  
![](https://www.bespokesynth.com/docs/screenshots/noterouter.png)  
allows you to control where notes are routed to using a UI control. to add destinations to the list, patch them as a target

**route**: the noterouter's destination module

accepts:

notes  
**notesorter**  
![](https://www.bespokesynth.com/docs/screenshots/notesorter.png)  
separate notes by pitch. any unmapped pitches go through the standard outlet.

**pitch \***: pitch to use for this outlet

accepts:

notes  
**notestepper**  
![](https://www.bespokesynth.com/docs/screenshots/notestepper.png)  
output notes through a round robin of patch cables, to create sequential variety

**reset**: reset to the start  
**length**: length of the sequence

accepts:

notes  
**notestream**  
![](https://www.bespokesynth.com/docs/screenshots/notestream.png)  
view a stream of notes as they're played

**reset**: reset the pitch range

accepts:

notes  
**notestrummer**  
![](https://www.bespokesynth.com/docs/screenshots/notestrummer.png)  
send a chord into this, and move a slider to strum each note of the chord

**strum**: move the slider past each note to strum it

accepts:

notes  
**notetable**  
![](https://www.bespokesynth.com/docs/screenshots/notetable.png)  
map a pitch (starting from zero) to a scale pitch

**x offset**: x offset of attached grid controller  
**rand pitch chance**: when clicking the random pitch button, what is the chance that a step gets changed?  
**clear**: clear grid  
**y offset**: y offset of attached grid controller  
**tone\***: pitch for this column  
**rand pitch range**: when clicking the random pitch button, how far will the pitch change?  
**length**: the number of pitches  
**grid**: patch a grid in here from a "midicontroller" module  
**octave**: octave of the bottom pitch of this sequence  
**random pitch**: randomize pitches in the sequence. hold shift to constrain the randomization to only pick roots and fifths.  
**notemode**: which set of pitches should the rows represent?

accepts:

notes  
**notewrap**  
![](https://www.bespokesynth.com/docs/screenshots/notewrap.png)  
wrap an input pitch to stay within a desired range

**range**: number of semitones before wrapping back down to min pitch  
**min**: bottom of pitch range

accepts:

notes  
**pitchbender**  
![](https://www.bespokesynth.com/docs/screenshots/pitchbender.png)  
add pitch bend to notes

**bend**: bend amount, in semitones

accepts:

notes  
**pitchdive**  
![](https://www.bespokesynth.com/docs/screenshots/pitchdive.png)  
use pitchbend to settle into an input pitch from a starting offset

**start**: semitone offset to start from  
**time**: time in milliseconds to ramp from pitch offset into input pitch

accepts:

notes  
**pitchpanner**  
![](https://www.bespokesynth.com/docs/screenshots/pitchpanner.png)  
add pan modulation to notes based upon input pitch, so low pitches are panned in one direction and high pitches are panned in another

**right**: pitch that represents full right pan  
**left**: pitch that represents full left pan

accepts:

notes  
**pitchremap**  
![](https://www.bespokesynth.com/docs/screenshots/pitchremap.png)  
remap input pitches to different output pitches

**to\***: desired pitch  
**from\***: pitch to change

accepts:

notes  
**pitchsetter**  
![](https://www.bespokesynth.com/docs/screenshots/pitchsetter.png)  
set an incoming note to use a specified pitch

**pitch**: the pitch to use

accepts:

notes  
**portamento**  
![](https://www.bespokesynth.com/docs/screenshots/portamento.png)  
only allows one note to play at a time, and uses pitch bend to glide between notes

**mode**: always: always glide to new notes retrigger held: bend to notes if the prior note is held, and retrigger bend held: bend to notes if the prior note is held, without retriggering  
**glide**: time to glide, in milliseconds

accepts:

notes  
**pressure**  
![](https://www.bespokesynth.com/docs/screenshots/pressure.png)  
add pressure modulation to notes

**pressure**: pressure amount

accepts:

notes  
**pressuretomodwheel**  
![](https://www.bespokesynth.com/docs/screenshots/pressuretomodwheel.png)  
takes midi pressure modulation input and changes it to modwheel modulation

accepts:

notes  
**pressuretovibrato**  
![](https://www.bespokesynth.com/docs/screenshots/pressuretovibrato.png)  
takes midi pressure modulation input and changes it to vibrato, using pitch bend

**vibrato**: amount of vibrato  
**vibinterval**: vibrato speed

accepts:

notes  
**previousnote**  
![](https://www.bespokesynth.com/docs/screenshots/previousnote.png)  
when receiving a note on, output the prior note on that we received

accepts:

notes  
**quantizer**  
![](https://www.bespokesynth.com/docs/screenshots/quantizer.png)  
delay inputs until the next quantization interval

**quantize**: the quantization interval  
**repeat**: when holding a note, should we repeat it every interval?

accepts:

pulses notes  
**scaledegree**  
![](https://www.bespokesynth.com/docs/screenshots/scaledegree.png)  
transpose input based on current scale

**retrigger**: immediately replay current notes when changing the transpose amount  
**diatonic**: should we keep transposed notes in the scale?  
**degree**: amount to transpose

accepts:

notes  
**scaledetect**  
![](https://www.bespokesynth.com/docs/screenshots/scaledetect.png)  
detect which scales fit a collection of entered notes. the last played pitch is used as the root.

**matches**: matching scales for this root  
**reset**: reset the input collection of notes

accepts:

notes  
**sustainpedal**  
![](https://www.bespokesynth.com/docs/screenshots/sustainpedal.png)  
keeps input notes sustaining

**sustain**: should we hold the input notes?

accepts:

notes  
**transposefrom**  
![](https://www.bespokesynth.com/docs/screenshots/transposefrom.png)  
transpose input from a specified root to the root of the current scale. the primary usage of this would be to allow you to play a keyboard in C, but it gets transposed to the current scale.

**root**: root to transpose from  
**retrigger**: immediately replay current notes when changing the transpose root or the scale

accepts:

notes  
**unstablemodwheel**  
![](https://www.bespokesynth.com/docs/screenshots/unstablemodwheel.png)  
mutate MPE slide with perlin noise

**amount**: amount of mutation  
**noise**: fast-later mutation rate  
**warble**: slow-layer mutation rate

accepts:

notes  
**unstablepitch**  
![](https://www.bespokesynth.com/docs/screenshots/unstablepitch.png)  
mutate MPE pitchbend with perlin noise

**amount**: amount of mutation  
**noise**: fast-later mutation rate  
**warble**: slow-layer mutation rate

accepts:

notes  
**unstablepressure**  
![](https://www.bespokesynth.com/docs/screenshots/unstablepressure.png)  
mutate MPE pressure with perlin noise

**amount**: amount of mutation  
**noise**: fast-later mutation rate  
**warble**: slow-layer mutation rate

accepts:

notes  
**velocitycurve**  
![](https://www.bespokesynth.com/docs/screenshots/velocitycurve.png)  
adjust velocity based upon a curve mapping

accepts:

notes  
**velocityscaler**  
![](https://www.bespokesynth.com/docs/screenshots/velocityscaler.png)  
scale a note's velocity to be higher or lower

**scale**: amount to multiply velocity by

accepts:

notes  
**velocitysetter**  
![](https://www.bespokesynth.com/docs/screenshots/velocitysetter.png)  
set a note's velocity to this value

**rand**: randomness to reduce output velocity by  
**vel**: velocity to use

accepts:

notes  
**velocitystepsequencer**  
![](https://www.bespokesynth.com/docs/screenshots/velocitystepsequencer.png)  
adjusts the velocity of incoming notes based upon a sequence

**downbeat**: should we reset the sequence every downbeat?  
**interval**: speed to advance sequence  
**vel\***: velocity for this step  
**len**: length of sequence

accepts:

notes  
**velocitytochance**  
![](https://www.bespokesynth.com/docs/screenshots/velocitytochance.png)  
use a note's velocity to determine the chance that the note plays

**\***: generate a new random seed  
**seed**: number that determines the random sequence  
**<**: go to next seed  
**beat length**: restart the deterministic random sequence at this interval  
**full velocity**: set velocity to full for notes that pass through

accepts:

notes  
**vibrato**  
![](https://www.bespokesynth.com/docs/screenshots/vibrato.png)  
add rhythmic oscillating pitch bend to notes

**vibrato**: amount of pitch bend to add  
**vibinterval**: speed of pitch bend oscillation

accepts:

notes  
**volcabeatscontrol**  
![](https://www.bespokesynth.com/docs/screenshots/volcabeatscontrol.png)  
outputs MIDI data to control various aspects of the KORG volca beats drum machine

accepts:

notes  
**whitekeys**  
![](https://www.bespokesynth.com/docs/screenshots/whitekeys.png)  
remap the white keys that correspond to the C major scale to instead play the current global scale

accepts:

notes

## synths

  
**beats**  
![](https://www.bespokesynth.com/docs/screenshots/beats.png)  
multi-loop player, for mixing sample layers together

**double\***: enable this to play at double speed  
**delete \***: remove the current sample from the list  
**filter\***: layer filter. negative values bring in a low pass, positive values bring in a high pass.  
**selector\***: which sample should we play in this slot? drag samples onto here to add them to this slot.  
**pan\***: layer panorama  
**volume\***: layer volume  
**bars\***: how many measures long are the samples in this slot?

  
**drumplayer**  
![](https://www.bespokesynth.com/docs/screenshots/drumplayer.png)  
sample player intended for drum playback

**shuffle**: random is samples, speeds, and pans  
**hitcategory\***: folder to choose from, when clicking the "random" button. these folders are found in the data/drums/hits/ directory  
**speed rnd**: global sample speed randomization amount  
**test \***: play this sample  
**quantize**: quantize input to this interval  
**start \***: start offset percentage of sample  
**speed**: global sample speed multiplier  
**envelopedisplay \*D**: envelope decay  
**aud**: scroll to audition samples in the current pad's head category, or a directory last dropped onto a pad  
**envelopedisplay \*A**: envelope attack  
**vol \***: volume of sample  
**vol**: the output volume  
**view ms \***: envelope view length in milliseconds  
**envelopedisplay \*R**: envelope release  
**envelopedisplay \*S**: envelope sustain  
**random \***: choose a random sample from the selected hitcategory  
**repeat**: if quantizing, should held notes repeat at that interval?  
**widen \***: stereo delay of sample to create width  
**grab \***: grab this sample  
**grid**: patch a grid in here from a "midicontroller" module  
**next \***: choose the next sample from the selected hitcategory  
**envelope \***: should we apply a volume envelope to the sample?  
**linkid \***: if linkid is not -1, silence any other sample with a matching linkid (useful for linking open and closed hats)  
**edit**: show pads for editing  
**mono**: force output to mono  
**pan \***: stereo pan position of sample  
**speed \***: speed of sample  
**single out \***: should the sample have its own individual output?  
**prev \***: choose the previous sample from the selected hitcategory  
**full vel**: always play drum hits at full velocity

accepts:

notes  
**drumsynth**  
![](https://www.bespokesynth.com/docs/screenshots/drumsynth.png)  
oscillator+noise drum synth

**vol**: the output volume  
**type\***: oscillator type  
**cutoffmax\***: filter start cutoff frequency  
**q\***: filter resonance  
**freqmin\***: oscillator end frequency  
**freqmax\***: oscillator start frequency  
**oversampling**: oversampling amount. increases sound quality, but also increases cpu usage.  
**vol\***: oscillator volume  
**edit**: display parameters for each hit  
**cutoffmin\***: filter end cutoff frequency  
**noise\***: noise volume

accepts:

notes  
**fmsynth**  
![](https://www.bespokesynth.com/docs/screenshots/fmsynth.png)  
polyphonic fm synthesis

**harmratio**: harmonic ratio of first-order modulator to input pitch  
**vol**: the output volume  
**tweak**: multiplier to harmonic ratio for first-order modulator  
**tweak2**: multiplier to harmonic ratio for second-order modulator  
**mod2**: amount to modulate second-order modulator  
**mod**: amount to modulate first-order modulator  
**harmratio2**: harmonic ratio of second-order modulator to input pitch  
**phase1**: phase offset for first-order modulator  
**phase0**: phase offset for base oscillator  
**phase2**: phase offset for second-order modulator

accepts:

notes  
**karplusstrong**  
![](https://www.bespokesynth.com/docs/screenshots/karplusstrong.png)  
polyphonic plucked string physical modeling synth

**x freq**: frequency of excitation audio  
**vel2vol**: how much velocity should affect voice volume  
**feedback**: amount of feedback for resonance  
**vol**: output volume  
**invert**: should the feedback invert?  
**x att**: fade in time for excitation audio  
**filter**: amount to filter resonance  
**pitchtone**: adjust how pitch influences filter amount. a value of zero gives even filtering across the entire pitch range, higher values filter high pitches less, low values filter low pitches less.  
**x dec**: fade out time for excitation audio  
**source type**: audio to use for excitation  
**lite cpu**: only recalculate some parameters once per buffer, to reduce CPU load. can make pitch bends and rapid modulation sound worse in some scenarios.  
**vel2env**: how much velocity should affect excitation attack time

accepts:

notes audio  
**metronome**  
![](https://www.bespokesynth.com/docs/screenshots/metronome.png)  
beeps to the beat

**vol**: metronome volume

  
**oscillator**  
![](https://www.bespokesynth.com/docs/screenshots/oscillator.png)  
polyphonic enveloped oscillator. modulations (with MPE support): modwheel closes filter further (if filter is enabled), pressure decreases detune amount

**unison**: how many oscillators to play for one note  
**envfilterA**: filter envelope attack  
**shuffle**: stretches and squeezes every other cycle of the waveform  
**envfilterD**: filter envelope decay  
**envS**: volume envelope sustain  
**envR**: volume envelope release  
**sync**: turns on "sync" mode, to reset the phase at syncf's frequency  
**soften**: soften edges of square and saw waveforms  
**envfilterS**: filter envelope sustain  
**envfilterR**: filter envelope release  
**osc**: oscillator type  
**envA**: volume envelope attack  
**envD**: volume envelope decay  
**vel2vol**: how much should the input velocity affect the output volume?  
**pw**: pulse width (or shape for non-square waves)  
**width**: controls how voices are panned with unison is greater than 1  
**vol**: this oscillator's volume  
**syncf**: frequency to reset the phase, when "sync" is enabled  
**lite cpu**: only recalculate some parameters once per buffer, to reduce CPU load. can make pitch bends and rapid modulation sound worse in some scenarios.  
**fmax**: frequency cutoff of lowpass filter at the max of the envelope. set this slider to the max to disable the filter  
**phase**: phase offset of oscillator, and phase offset between unison voices. useful to patch into with a very fast modulator, to achieve phase modulation.  
**vel2env**: how much should the input velocity affect the speed of the volume and filter envelopes?  
**mult**: multiply frequency of incoming pitch  
**adsr len**: view length of ADSR controls  
**q**: resonance of lowpass filter  
**detune**: when unison is 1, detunes oscillator by this amount. when unison is 2, one oscillator is tuned normally and the other is detuned by this amount. when unison is >2, oscillators are randomly detuned within this range.  
**fmin**: frequency cutoff of lowpass filter at the min of the envelope

accepts:

notes  
**samplecanvas**  
![](https://www.bespokesynth.com/docs/screenshots/samplecanvas.png)  
sample arranging view

**scrollv**: vertical scrollbar  
**canvas**: canvas of samples. drag and drop samples onto here. canvas controls: -hold shift and drag a sample to duplicate -hold alt to drag a sample without snapping -hold ctrl while dragging to snap to an interval -hold shift and scroll to zoom -hold alt and grab empty space to move slide the canvas view -hold ctrl and grab empty space to zoom the canvas view  
**interval**: grid subdivision interval  
**drag mode**: direction that elements can be dragged  
**timeline**: control loop points  
**clear**: delete all elements  
**measures**: length of canvas in measures  
**view rows**: number of visible rows  
**scrollh**: horizontal scrollbar  
**delete**: delete highlighted elements

  
**sampleplayer**  
![](https://www.bespokesynth.com/docs/screenshots/sampleplayer.png)  
sample playback with triggerable cue points, clip extraction, and youtube search/download functionality. resize this module larger to access additional features. if you have a youtube URL in your clipboard, a button will appear to allow you to download the audio.

**load**: show a file chooser to load a sample  
**trim**: discard all audio outside the current zoom range  
**select played**: when true, any cue point played via incoming notes will become the current cue  
**cue len**: length in seconds of the current cue. a value of zero will play to the end of the sample.  
**append to rec**: when recording, append to the previous recording, rather than clearing the sample first  
**cue start**: start point in seconds of the current cue  
**play cue**: play the current cue  
**threshold**: volume threshold to open up the gate for recording  
**speed**: current playback speed  
**pause**: pause playing and leave playhead where it is  
**cue stop**: stop playing this cue if a note-off is received  
**attack**: speed at which gate blends open  
**4**: auto-slice 4 slices  
**8**: auto-slice 8 slices  
**save**: save this sample to a file  
**playhovered**: play this cue  
**play**: start playing from the current playhead  
**click sets cue**: when true, clicking on the waveform will set the start position of the current cue  
**stop**: stop playing and reset playhead  
**volume**: output gain  
**searchresult\***: click to download this youtube search result. downloading long videos may take a while.  
**record as clips**: when recording, only record when there is enough input to open the gate, and mark up each recorded segment with cue points  
**grabhovered**: grab a sample of this cue to drop onto another module  
**cuepoint**: sets the current cue to edit  
**yt:**: search youtube for this string  
**16**: auto-slice 16 slices  
**32**: auto-slice 32 slices  
**youtube**: download the audio of the youtube URL currently on your clipboard  
**record**: record audio input into our sample buffer. clears the current sample.  
**cue speed**: playback speed of the current cue  
**release**: speed at which gate blends closed  
**show grid**: show a quarter note grid (when zoomed in far enough)  
**loop**: wrap playhead to beginning when it reaches end

accepts:

pulses notes audio  
**sampler**  
![](https://www.bespokesynth.com/docs/screenshots/sampler.png)  
very basic polyphonic pitched sample player and recorder. send audio in, and use note input to play the recorded audio.

**envS**: volume envelope sustain  
**envR**: volume envelope release  
**pitch**: should we attempt pitch-correct the audio?  
**vol**: output volume  
**thresh**: when recording is enabled, exceed this threshold with input audio to begin recording  
**env**: volume envelope  
**passthrough**: should input audio pass through as we're recording?  
**rec**: enable to clear the current recording, and record new audio once the input threshold is reached  
**envA**: volume envelope attack  
**envD**: volume envelope decay

accepts:

notes audio  
**seaofgrain**  
![](https://www.bespokesynth.com/docs/screenshots/seaofgrain.png)  
granular synth, playable with sliders or MPE input

**load**: load a sample file  
**pos r \***: randomization of grain start point  
**pos \***: position of this voice within the sample  
**speed r \***: randomization of grain speed  
**pan \***: stereo panorama of grain placement  
**offset**: where to start view of the sample  
**speed \***: speed of grain playback  
**keyboard num pitches**: amount of pitches to assign across the sample  
**volume**: output volume  
**len ms \***: length of each grain in milliseconds  
**overlap \***: number of overlapping grains  
**spacing r\***: randomization of time between grains  
**display length**: amount of sample to view  
**gain \***: volume of this voice  
**keyboard base pitch**: midi pitch that represents the start of the sample  
**octaves \***: should we add octaves and fifths?  
**width \***: stereo width of grain placement  
**record**: record input as the granular buffer, to use seaofgrain a live granular delay

accepts:

notes audio  
**signalgenerator**  
![](https://www.bespokesynth.com/docs/screenshots/signalgenerator.png)  
basic oscillator signal. send a note into it to set the frequency, and send a pulse to reset the phase.

**syncf**: frequency to reset the phase, when "sync" is enabled  
**shuffle**: stretches and squeezes every other cycle of the waveform  
**pw**: pulse width (or shape for non-square waves)  
**slider**: slider to interpolate between last two input pitches  
**vol**: output volume  
**ramp**: amount of time to ramp to input frequency  
**sync**: turns on "sync" mode, to reset the phase at syncf's frequency  
**freq mode**: what mode should we use for input notes? "instant" changes to the input note's frequency instantly, "ramp" ramps to the frequency over time, and "slider" allows you to use a slider to interpolate between the last two input notes  
**soften**: soften edges of square and saw waveforms  
**detune**: amount to detune from specified frequency  
**phase**: phase offset  
**freq**: signal frequency  
**osc**: oscillator type  
**mult**: multiplier for frequency

accepts:

pulses notes

## audio effects

  
**audiometer**  
![](https://www.bespokesynth.com/docs/screenshots/audiometer.png)  
sets a slider to an audio level's volume. useful to map a midi display value to.

**level**: the input audio level. hook this up to an LED-display midi control to see the value displayed on your controller.

accepts:

audio  
**audiorouter**  
![](https://www.bespokesynth.com/docs/screenshots/audiorouter.png)  
selector for switching where audio is routed to. connect to targets to add them to the list.

**route**: audio destination

accepts:

audio  
**buffershuffler**  
![](https://www.bespokesynth.com/docs/screenshots/buffershuffler.png)  
use notes to play back slices of a constantly-recording live input buffer. input notes trigger slices, with the pitch mapping to slice index. you can also click with a mouse to trigger slices.

**freeze input**: retain the current buffer, without writing in new input  
**playback style**: how to play clicked slices. or, with input notes, velocity range determines playback style.  
**interval**: slice size  
**num bars**: number of bars to capture

accepts:

notes audio  
**dcoffset**  
![](https://www.bespokesynth.com/docs/screenshots/dcoffset.png)  
add a constant offset to an audio signal

**offset**: amount of offset to add

accepts:

audio  
**effectchain**  
![](https://www.bespokesynth.com/docs/screenshots/effectchain.png)  
container to hold a list of effects, applied in series. the effects can be easily reordered with the < and > buttons, and deleted with the x button. hold shift to expose a x button for all effects.

**spawn**: spawn the currently highlighted effect  
**volume**: output gain  
**effect**: select which effect to add  
**exit effect**: on push2, back effect control out to the main effectchain controls  
**mix\***: wet/dry slider for this effect  
**x**: delete this effect  
**<**: move this effect to earlier in the chain  
**\>**: move this effect to later in the chain

accepts:

audio  
**eq**  
![](https://www.bespokesynth.com/docs/screenshots/eq.png)  
multi-band equalizer, to adjust output levels at frequency ranges

**q\***: resonance for this band  
**f\***: frequency cutoff for this band  
**enabled\***: enable this band?  
**g\***: gain for this band  
**type\***: what type of filter should this band use

accepts:

audio  
**feedback**  
![](https://www.bespokesynth.com/docs/screenshots/feedback.png)  
feed delayed audio back into earlier in the signal chain. use the "feedback out" connector for sending the audio back up the chain, and the primary output connector for sending the resulting audio forward. using feedback can often lead to extreme and difficult-to-control results!

**limit**: clip the feedback audio to this range, to avoid issues with feedback blowing out too intensely.

accepts:

audio  
**fftvocoder**  
![](https://www.bespokesynth.com/docs/screenshots/fftvocoder.png)  
FFT-based vocoder

**cut**: how many bass partials to remove  
**phase off**: how much we should offset the phase of the carrier signal's partials  
**whisper**: how much the carrier signal partial's phases should be randomized, which affects how whispery the output sound is  
**dry/wet**: how much original input vs vocoded signal to output  
**volume**: output gain  
**fric thresh**: fricative detection sensitivity, to switch between using the carrier signal and white noise for vocoding  
**carrier**: carrier signal gain  
**input**: input signal gain

accepts:

audio  
**freqdelay**  
![](https://www.bespokesynth.com/docs/screenshots/freqdelay.png)  
delay effect with delay length based upon input notes

**dry/wet**: how much of the effect to apply

accepts:

notes audio  
**gain**  
![](https://www.bespokesynth.com/docs/screenshots/gain.png)  
adjusts volume of audio signal

**gain**: amount to adjust signal. a value of 1 will cause no change to the signal.

accepts:

audio  
**input**  
![](https://www.bespokesynth.com/docs/screenshots/input.png)  
get audio from input source, like a microphone

**ch**: which channel (or channels, if you want stereo) to use

accepts:

audio  
**inverter**  
![](https://www.bespokesynth.com/docs/screenshots/inverter.png)  
multiply a signal by -1. enables some pretty interesting effects when used with sends, to subtract out parts of signals when recombined.

accepts:

audio  
**lissajous**  
![](https://www.bespokesynth.com/docs/screenshots/lissajous.png)  
draw input audio as a lissajous curve. turn off "autocorrelation" in the module's triangle menu to use stereo channels to show stereo width.

**scale**: visual scale of lissajous image

accepts:

audio  
**looper**  
![](https://www.bespokesynth.com/docs/screenshots/looper.png)  
loop input audio. use with a "looperrecorder" for full functionality.

**fourtet**: use a textural trick I saw four tet illustrate in a video once: slice the audio into chunks, and for each chunk it at double speed followed by playing it in reverse at double speed. this slider adjusts the mix between the original audio and this "fourtetified" audio.  
**.5x**: make loop play at half speed  
**mute**: silence this looper  
**passthrough**: should we pass incoming audio through to the output? turn off to mute incoming audio.  
**pitch**: amount to pitch shift looper output  
**apply**: shift the contents of the looper so the current offset is the start of the buffer  
**scr**: allow loop to be scratched by adjusting "scrspd"  
**decay**: amount to lower volume each loop  
**write**: write input audio to loop buffer  
**swap**: swap the contents of this looper and with another. click this button on two loopers to swap them.  
**save**: save this loop to a wav file  
**m** : take the contents of this looper and merge it into another. click this button on the merge source, then on the merge target.  
**extend**: make loop twice as long  
**capture**: when the next loop begins, record input for the duration of the loop  
**auto**: should pitch shift auto-adjust as the transport tempo adjusts?  
**undo**: undo last loop commit  
**offset**: amount to offset looper's playhead from transport position  
**copy**: take the contents of this looper and copy it onto another. click this button on the copy source, then on the copy target.  
**num bars**: loop length in measures  
**resample for tempo**: this button appears when the current global tempo no longer matches the tempo that the buffer was recorded at. click this to resample the buffer to match the new tempo.  
**volume**: output volume  
**b**: bake current volume into waveform  
**clear**: clear the loop audio  
**2x**: make loop play at double speed  
**scrspd**: playback speed, used with "scr" is enabled. modulate quickly for a vinyl-like scratching effect.  
**fourtetslices**: chunk size to use for "fourtet" effect  
**commit**: commit the current looperrecorder buffer to this loop

accepts:

notes audio  
**looperrecorder**  
![](https://www.bespokesynth.com/docs/screenshots/looperrecorder.png)  
command center to manage recording into multiple loopers, and allow retroactive loop capture (i.e., always-on recording)

**orig speed**: reset looper to tempo that loops were recorded at  
**target**: looper to commit audio to when using the on-buffer capture buttons to the left  
**2xtempo**: double global transport tempo, while keeping connected loopers sounding the same  
**cancel free rec**: if "free rec" is enabled, cancel recording without setting the loop length  
**clear**: clear the recorded buffer  
**snap to pitch**: snap tempo to nearest value that matches a key  
**1**: capture the last measure to the currently-targeted looper  
**length**: length in measures to use when connected loopers use the "commit" button  
**2**: capture the last 2 measures to the currently-targeted looper  
**free rec**: enable to start recording a loop with no predetermined length. disable to end recording, adjust global transport to match the loop length, and switch the recorder's mode to "loop"  
**4**: capture the last 4 measures to the currently-targeted looper  
**resample**: resample all connected loopers to new tempo  
**.5tempo**: halve global transport tempo, while keeping connected loopers sounding the same  
**resample & set key**: snap tempo to nearest value that matches a key (based upon the current key and the tempo change), resample all connected loopers to that new tempo, and change global scale to the new key  
**8**: capture the last 8 measures to the currently-targeted looper  
**auto-advance**: automatically advance to the next looper when committing  
**mode**: recorder mode: use "record" to record input and allow it to be committed to buffers when you're ready to loop, use "overdub" to record input and play the loop at our specified length, and use "loop" to play the current loop without adding input

accepts:

audio  
**looperrewriter**  
![](https://www.bespokesynth.com/docs/screenshots/looperrewriter.png)  
rewrites the contents of a looper with received input, to help you resample your own loops. attach the grey dot to a "looper" module. the ideal way to use this module is to hook the "looper" directly up to a "send", hook the leftmost outlet of the "send" up to your effects processing (like an "effectchain"), hook the effect processing up to this "rewriter", and then also connect the rightmost outlet of the "send" up to this "rewriter"

**go**: rewrite the connected looper, and if that looper is connected to a send, set that send to output only to the right outlet  
**new loop**: start recording a dynamic loop length. press "go" when you want to rewrite it to the looper. this will also change bespoke's global tempo to match this new loop, so it's quite powerful and scary! click it again to cancel.

accepts:

audio  
**multitapdelay**  
![](https://www.bespokesynth.com/docs/screenshots/multitapdelay.png)  
delay with multiple tap points

**dry**: how much dry signal to allow through  
**pan \***: stereo pan for this tap  
**delay \***: tap delay time, in milliseconds  
**display length**: length of buffer display, in seconds  
**feedback \***: how much delayed audio from this tap should feed back in to the input  
**gain \***: tap delay amount

accepts:

notes audio  
**output**  
![](https://www.bespokesynth.com/docs/screenshots/output.png)  
route audio in here to send it to an output channel (your speakers or audio interface)

**ch**: channel (or channels, if you want stereo) to send audio to

accepts:

audio  
**panner**  
![](https://www.bespokesynth.com/docs/screenshots/panner.png)  
pan audio left and right. also, converts a mono input to a stereo output.

**widen**: delay a channel by this many samples. results in a pan-like effect where the sound seems to come from from a direction.  
**pan**: amount to send signal to the left and right channels. a value of 0 is centered.

accepts:

audio  
**ringmodulator**  
![](https://www.bespokesynth.com/docs/screenshots/ringmodulator.png)  
modulate a signal's amplitude at a frequency

**volume**: volume output  
**freq**: frequency to use. can also be set by patching a note input into this module.  
**dry/wet**: how much of the original audio to use vs modulated audio  
**glide**: how long an input note should take to glide to the desired frequency

accepts:

notes audio  
**samplergrid**  
![](https://www.bespokesynth.com/docs/screenshots/samplergrid.png)  
record input onto pads, and play back the pads. intended to be used with an 64-pad grid controller.

**vol**: the output volume  
**end**: sample end  
**edit**: enable controls to adjust recorded sample for last pressed grid square  
**passthrough**: should the incoming audio pass through to the output?  
**clear**: when enabled, clears any pressed grid squares  
**start**: sample start  
**duplicate**: what enabled, duplicates last pressed sample onto any pressed grid squares  
**grid**: patch a grid in here from a "midicontroller" module

accepts:

notes audio  
**send**  
![](https://www.bespokesynth.com/docs/screenshots/send.png)  
duplicate a signal and send it to a second destination

**amount**: amount to send out the right-side cable  
**crossfade**: when true, output of the left-side cable is reduced as "amount" increases

accepts:

audio  
**signalclamp**  
![](https://www.bespokesynth.com/docs/screenshots/signalclamp.png)  
clamps an audio signal's value within a range

**max**: maximum output value  
**min**: minimum output value

accepts:

audio  
**spectrum**  
![](https://www.bespokesynth.com/docs/screenshots/spectrum.png)  
display audio signal's spectral data

accepts:

audio  
**splitter**  
![](https://www.bespokesynth.com/docs/screenshots/splitter.png)  
splits a stereo signal into two mono signals, or duplicates a mono signal

accepts:

audio  
**stutter**  
![](https://www.bespokesynth.com/docs/screenshots/stutter.png)  
captures and stutters input

**free length**: length in seconds for "free" stutter mode  
**reverse**: reversed half note stutter  
**half speed**: stutter at half speed, low pitched  
**ramp in**: stutter with speed climbing up from zero to one  
**triplets**: stutter on a triplet interval  
**32nd**: 32nd note stutter  
**64th**: 64th note stutter  
**tumble up**: accelerating stutter  
**half note**: half note stutter  
**tumble down**: decelerating stutter  
**grid**: patch a grid in here from a "midicontroller" module  
**free**: stutter with the settings specified by the following sliders  
**dotted eighth**: stutter on a dotted eighth interval  
**free speed**: rate for "free" stutter mode  
**double speed**: stutter at double speed, high pitched  
**quarter**: quarter note stutter  
**ramp out**: stutter with speed quickly falling to zero  
**16th**: 16th note stutter  
**8th**: 8th note stutter

accepts:

notes audio  
**vocoder**  
![](https://www.bespokesynth.com/docs/screenshots/vocoder.png)  
frequency band-based vocoder. this must be paired with a "vocodercarrier" module. voice should be routed into this module, and a synth should be patched into the vocodercarrier.

**volume**: output gain  
**max band**: volume limit for each frequency band  
**bands**: how many frequency bands to use  
**spacing**: how frequency bands should be spaced  
**f base**: frequency for lowest band  
**q**: resonance of the bands  
**mix**: how much original input vs vocoded signal to output  
**carrier**: carrier signal gain  
**f range**: frequency range to highest band  
**input**: input signal gain  
**ring**: how long it should take the bands to "cool down"

accepts:

audio  
**vocodercarrier**  
![](https://www.bespokesynth.com/docs/screenshots/vocodercarrier.png)  
connect to "vocoder" or "fftvocoder" modules. send the synth audio into this module, and the voice audio into the vocoder module.

accepts:

audio  
**waveformviewer**  
![](https://www.bespokesynth.com/docs/screenshots/waveformviewer.png)  
waveform display

**length**: number of samples to capture  
**draw gain**: adjust waveform display scale  
**freq**: frequency to sync display to. gets automatically set if you patch a note input into this module

accepts:

notes audio  
**waveshaper**  
![](https://www.bespokesynth.com/docs/screenshots/waveshaper.png)  
waveshaping with expressions

**a**: variable to use in expressions  
**c**: variable to use in expressions  
**b**: variable to use in expressions  
**e**: variable to use in expressions  
**d**: variable to use in expressions  
**rescale**: rescales input before feeding it into expression  
**y=**: waveshaping expression. try something like "x+sin(x\*pi\*a)". available variables: a,b,c,d,e = the sliders below. t = time. x1,x2,y1,y2 = biquad state storage.

accepts:

audio

## modulators

  
**accum**  
![](https://www.bespokesynth.com/docs/screenshots/accum.png)  
accumulate a value over time

**velocity**: amount to accumulate  
**value**: output value

  
**add**  
![](https://www.bespokesynth.com/docs/screenshots/add.png)  
outputs the result of value 1 plus value 2. value 1 and value 2 are intended to be patch targets for modulators.

**value 1**: value to sum  
**value 2**: value to sum

  
**addcentered**  
![](https://www.bespokesynth.com/docs/screenshots/addcentered.png)  
outputs the result of value 1 plus value 2, multiplied by range 2. optimized for using to modulation value 1 by range 2 at a frequency. value 1 or value 2 are intended to be patch targets for modulators.

**range 2**: modulation amount  
**value 1**: center value  
**value 2**: modulation value

  
**audiotocv**  
![](https://www.bespokesynth.com/docs/screenshots/audiotocv.png)  
use an audio signal to modulate a control. allow for audio-rate modulation, to achieve effects such as FM.

**max**: maximum output value  
**gain**: multiply incoming audio  
**min**: minimum output value

accepts:

audio  
**controlsequencer**  
![](https://www.bespokesynth.com/docs/screenshots/controlsequencer.png)  
modulate a control step-wise at an interval

**random**: randomize sequence values  
**length**: length of the sequence  
**interval**: rate to advance  
**step \***: value for this step

accepts:

pulses notes  
**curve**  
![](https://www.bespokesynth.com/docs/screenshots/curve.png)  
remap an input over its range with a curve. double-click on the curve to add points, right click on points to remove them, drag on lines to bend them.

**input**: input value (intended as a modulation target)

  
**curvelooper**  
![](https://www.bespokesynth.com/docs/screenshots/curvelooper.png)  
modulate a value over time with a looping curve

**length**: length of the loop  
**randomize**: create a random curve

  
**envelope**  
![](https://www.bespokesynth.com/docs/screenshots/envelope.png)  
modulate a value with a triggered envelope

**has sustain**: should this envelope have a sustain stage?  
**adsrD**: envelope decay  
**adsrA**: envelope attack  
**use velocity**: should envelope output be scaled by input velocity?  
**max sustain**: what's the maximum length of the sustain, in milliseconds? a value of -1 indicates no maximum  
**sustain stage**: which step of the envelope should have the sustain?  
**high**: output high value  
**length**: length of envelope display  
**low**: output low value  
**adsrS**: envelope sustain  
**adsrR**: envelope release  
**adsr**: envelope view  
**advanced**: switch to advanced envelope editor (allows for a more complicated envelope than just an ADSR). double-click on an advanced envelope line to add stages, right click on points to remove them, drag on lines to bend them.

accepts:

pulses notes  
**expression**  
![](https://www.bespokesynth.com/docs/screenshots/expression.png)  
shape modulation with a text-based mathematical expression

**a**: variable to use in expressions  
**c**: variable to use in expressions  
**b**: variable to use in expressions  
**e**: variable to use in expressions  
**d**: variable to use in expressions  
**y=**: expression to modify input. try something like "x+sin(x\*pi\*a)". available variables: a,b,c,d,e = the sliders below. t = time.  
**input**: input to use as x variable

  
**fubble**  
![](https://www.bespokesynth.com/docs/screenshots/fubble.png)  
draw on an X/Y pad and replay the drawing to modulate values. based on a concept proposed by olivia jack

**mutate amount**: amount to affect drawing by perlin noise field  
**mutate warp**: scale of perlin noise field  
**speed**: speed up or slow down playback  
**clear**: clear the drawing  
**quantize**: should we quantize playback to a specified rhythmic interval?  
**length**: the interval to quantize to  
**mutate noise**: rate to move through perlin noise field  
**reseed**: jump to a different location in the perlin noise field

  
**gravity**  
![](https://www.bespokesynth.com/docs/screenshots/gravity.png)  
make a modulation value rise and fall with physics

**kick amt**: the amount of upward force to apply when kicking  
**drag**: the resistance force to apply opposite the velocity  
**gravity**: the gravitational force to apply downwards  
**kick**: click to apply kick force (or, pulse this module for the same result)

accepts:

pulses  
**gridsliders**  
![](https://www.bespokesynth.com/docs/screenshots/gridsliders.png)  
use a grid controller to control multiple sliders

**direction**: should the grid display the sliders vertically, or horizontally?  
**grid**: patch a grid in here from a "midicontroller" module

  
**leveltocv**  
![](https://www.bespokesynth.com/docs/screenshots/leveltocv.png)  
output a modulation value based on the level of incoming audio

**release**: decay from the input level at this rate  
**max**: output when level is one  
**attack**: rise to the input level at this rate  
**gain**: multiply the input audio by this value  
**min**: output when level is zero

accepts:

audio  
**lfo**  
![](https://www.bespokesynth.com/docs/screenshots/lfo.png)  
modulates a slider with a low-frequency oscillator

**enable**: turn on/off modulation  
**shuffle**: adjust the waveoform to have a fast and slow cycle  
**pin**: make LFO window remain visible  
**interval**: length of oscillation period  
**soften**: smooth out the hard edges of square and saw waveforms  
**high**: output value at waveform's high point  
**free rate**: rate of oscillator running in non-clock-synced time  
**length**: proportion of time that should be spent on the waveform cycle  
**bias**: bias the waveform towards the low or high point  
**low**: output value at waveform's low point  
**offset**: phase offset, to make oscillation earlier/later  
**lite cpu**: only recalculate some parameters once per buffer, to reduce CPU load. can sound worse in some scenarios, especially with rapid modulation.  
**osc**: type of oscillation waveform  
**spread**: spread the waveform out to be closer to the low and high points

  
**macroslider**  
![](https://www.bespokesynth.com/docs/screenshots/macroslider.png)  
take a value and send scaled versions of that value to multiple destinations

**start\***: the output value at the bottom of the input's range  
**input**: the input value. intended to be a modulation patch target.  
**end\***: the output value at the top of the input's range

  
**modwheeltocv**  
![](https://www.bespokesynth.com/docs/screenshots/modwheeltocv.png)  
take a note's modwheel value and convert it to a modulation value

**max**: output for modwheel value 127  
**min**: output for modwheel value 0

accepts:

notes  
**mult**  
![](https://www.bespokesynth.com/docs/screenshots/mult.png)  
outputs the result of value 1 multiplier by value 2. value 1 and value 2 are intended to be patch targets for modulators.  
**notetofreq**  
![](https://www.bespokesynth.com/docs/screenshots/notetofreq.png)  
takes an input note, and outputs that note's frequency in hertz

accepts:

notes  
**notetoms**  
![](https://www.bespokesynth.com/docs/screenshots/notetoms.png)  
takes an input note, and outputs the period of that note's frequency in milliseconds. useful for setting delay lines to create specific pitches.

accepts:

notes  
**pitchtocv**  
![](https://www.bespokesynth.com/docs/screenshots/pitchtocv.png)  
take a note's pitch and convert it to a modulation value

**max**: output for pitch 127  
**min**: output for pitch 0

accepts:

notes  
**pitchtospeed**  
![](https://www.bespokesynth.com/docs/screenshots/pitchtospeed.png)  
convert an input pitch to a speed ratio. you could use this to control a sample's playback speed and make it playable with a keyboard.

**ref freq**: the output is the input frequency divided by this number

accepts:

notes  
**pressuretocv**  
![](https://www.bespokesynth.com/docs/screenshots/pressuretocv.png)  
take a note's pressure and convert it to a modulation value

**max**: output for pressure 127  
**min**: output for pressure 0

accepts:

notes  
**ramper**  
![](https://www.bespokesynth.com/docs/screenshots/ramper.png)  
blend a control to a specified value over a specified time

**start**: begin blending (or, send a pulse to this module for the same result)  
**length**: length of time to blend over  
**target**: the value to arrive at when the ramp is over

accepts:

pulses  
**smoother**  
![](https://www.bespokesynth.com/docs/screenshots/smoother.png)  
outputs a smoothed value of the input

**input**: set a value to smooth, patch a modulator into here  
**smooth**: amount of smoothing to apply

  
**subtract**  
![](https://www.bespokesynth.com/docs/screenshots/subtract.png)  
outputs the result of value 2 subtracted from value 1. value 1 and value 2 are intended to be patch targets for modulators.  
**valuesetter**  
![](https://www.bespokesynth.com/docs/screenshots/valuesetter.png)  
set a specified value on a targeted control

**slider**: value to set  
**set**: click here to send the value (or, send a pulse to this module for the same result)  
**value**: value to set

accepts:

pulses  
**velocitytocv**  
![](https://www.bespokesynth.com/docs/screenshots/velocitytocv.png)  
take a note's velocity and convert it to a modulation value

**max**: output for velocity 127  
**0 at note off**: output zero when note is released  
**min**: output for velocity 0

accepts:

notes  
**vinylcontrol**  
![](https://www.bespokesynth.com/docs/screenshots/vinylcontrol.png)  
modulator which outputs a speed value based upon control vinyl input audio. provide it with a stereo signal from control vinyl (like you'd use to control serato) patched in from an "input" module.

**control**: enable/disable transport control. when you enable it, it will use the current speed as the reference speed (so, the output will output a value of 1 until you change the vinyl's speed)

accepts:

audio

## pulse

  
**audiotopulse**  
![](https://www.bespokesynth.com/docs/screenshots/audiotopulse.png)  
sends a pulse when the audio level surpasses a specified threshold

**release**: the cooldown time for the audio signal before a pulse can be triggered again  
**threshold**: send a pulse when the signal hits this threshold

accepts:

audio  
**boundstopulse**  
![](https://www.bespokesynth.com/docs/screenshots/boundstopulse.png)  
sends a pulse when its input slider hits its max or min limit

**input**: the slider to check bounds on

  
**notetopulse**  
![](https://www.bespokesynth.com/docs/screenshots/notetopulse.png)  
trigger a pulse whenever a note is received

accepts:

notes  
**pulsebutton**  
![](https://www.bespokesynth.com/docs/screenshots/pulsebutton.png)  
trigger a pulse with a button press

**pulse**: trigger a pulse

  
**pulsechance**  
![](https://www.bespokesynth.com/docs/screenshots/pulsechance.png)  
randomly allow pulses through, based on chance

**deterministic**: allow for randomness to be repeated over an interval  
**chance**: chance that pulses are allowed through  
**\***: generate a new random seed  
**seed**: number that determines the random sequence. send reset pulses to restart the deterministic random sequence.  
**<**: go to next seed

accepts:

pulses  
**pulsedelayer**  
![](https://www.bespokesynth.com/docs/screenshots/pulsedelayer.png)  
delay pulses

**delay**: time to delay, in fractions of a measure

accepts:

pulses  
**pulsedisplayer**  
![](https://www.bespokesynth.com/docs/screenshots/pulsedisplayer.png)  
see what flags are on pulses

accepts:

pulses  
**pulseflag**  
![](https://www.bespokesynth.com/docs/screenshots/pulseflag.png)  
set properties on pulses

**flag**: property to add  
**replace**: if disabled, the above flag is appended to the pulse's flags. if enabled, the pulse's flags are replaced by the above flag.

accepts:

pulses  
**pulsegate**  
![](https://www.bespokesynth.com/docs/screenshots/pulsegate.png)  
control if pulses are allowed through

**allow**: can pulses pass through?

accepts:

pulses  
**pulsehocket**  
![](https://www.bespokesynth.com/docs/screenshots/pulsehocket.png)  
sends pulses to randomized destinations

**weight \***: chance that pulse goes to this destination  
**\***: generate a new random seed  
**seed**: number that determines the random sequence. send reset pulses to restart the deterministic random sequence.  
**<**: go to next seed

accepts:

pulses  
**pulser**  
![](https://www.bespokesynth.com/docs/screenshots/pulser.png)  
send pulse messages at an interval

**reset**: length of sequence before sending reset pulse  
**interval**: rate to send pulses  
**random**: tell pulsed modules to randomize their position  
**t**: pulse interval in milliseconds  
**offset**: pulse time offset, in fractions of the interval  
**div**: measure division, when using "div" as the interval  
**timemode**: when to send downbeat pulses, or set to "free" for pulses not locked to the transport

  
**pulsesequence**  
![](https://www.bespokesynth.com/docs/screenshots/pulsesequence.png)  
defines a looping sequence of pulses

**length**: length of the sequence  
**interval**: length of each step within the sequence  
**<**: shift sequence to the left  
**\>**: shift sequence to the right

accepts:

pulses  
**pulsetrain**  
![](https://www.bespokesynth.com/docs/screenshots/pulsetrain.png)  
defines a list of pulses to execute, once pulsed

**length**: length of the sequence  
**interval**: length of each step within the sequence

accepts:

pulses

## effect chain

  
**basiceq**  
![](https://www.bespokesynth.com/docs/screenshots/basiceq.png)  
simple multiband EQ

**even**: reset EQ

accepts:

audio  
**biquad**  
![](https://www.bespokesynth.com/docs/screenshots/biquad.png)  
filter using biquad formula

**Q**: resonance  
**type**: filter type  
**G**: gain  
**F**: frequency cutoff

accepts:

audio  
**bitcrush**  
![](https://www.bespokesynth.com/docs/screenshots/bitcrush.png)  
reduce sample resolution and sample rate for lo-fi effects

**crush**: sample resolution reduction  
**downsamp**: sample rate reduction

accepts:

audio  
**butterworth**  
![](https://www.bespokesynth.com/docs/screenshots/butterworth.png)  
filter using the butterworth formula

**Q**: resonance  
**F**: frequency cutoff

accepts:

audio  
**compressor**  
![](https://www.bespokesynth.com/docs/screenshots/compressor.png)  
try to keep volume at a certain level

**ratio**: how much gain reduction to apply when the single passes the threshold  
**lookahead**: how much time to "look ahead" to adjust the compression envelope. this necessarily introduces a delay into your output, which could be compensated for by running sequencers slightly early.  
**drive**: rescale input to affect how much compression affects it  
**mix**: amount of compression. lower this value for a "parallel compression" effect. you should use this mix slider instead of the effectchain's mix slider, to compensate for lookahead.  
**attack**: speed to apply gain reduction  
**threshold**: threshold where gain should start to be reduced  
**release**: speed to remove gain reduction  
**output**: makeup gain, to increase volume

accepts:

audio  
**dcremover**  
![](https://www.bespokesynth.com/docs/screenshots/dcremover.png)  
high pass filter with a 10hz cutoff to remove DC offset, to keep signal from drifting away from zero

accepts:

audio  
**delay**  
![](https://www.bespokesynth.com/docs/screenshots/delay.png)  
echoing delay

**dry**: should the dry signal pass through, or just the delayed signal?  
**short**: shortcut to shrink the range of the delay slider, to allow for audible-rate delays and comb filter sounds  
**feedback**: should the output audio feed back into the delay?  
**invert**: should the delayed audio have its signal inverted? this can give a different sound, and also cancel out DC offset to prevent it from accumulating with feedback.  
**interval**: sets delay length to a musical duration  
**delay**: delay in milliseconds  
**amount**: amount of delay that returns  
**input**: should we accept input into the delay?

accepts:

audio  
**distortion**  
![](https://www.bespokesynth.com/docs/screenshots/distortion.png)  
waveshaping distortion

**preamp**: signal gain before feeding into distortion  
**fuzz**: push input signal off-center to distort asymmetrically  
**type**: style of distortion to apply  
**clip**: cutoff point of distortion, lower values result in more extreme distortion  
**center input**: remove dc offset from input signal to distort in a more controlled way

accepts:

audio  
**freeverb**  
![](https://www.bespokesynth.com/docs/screenshots/freeverb.png)  
reverb using the "freeverb" algorithm

**dry**: amount of untouched signal  
**room size**: controls the length of the reverb, a higher value means longer reverb  
**damp**: high frequency attenuation; a value of zero means all frequencies decay at the same rate, while higher settings will result in a faster decay of the high frequency range  
**width**: stereo width of reverb  
**wet**: amount of reverb signal

accepts:

audio  
**gainstage**  
![](https://www.bespokesynth.com/docs/screenshots/gainstage.png)  
control volume within an effectchain

**gain**: volume multiplier

accepts:

audio  
**gate**  
![](https://www.bespokesynth.com/docs/screenshots/gate.png)  
only allow signal in when it's above a certain threshold. useful to eliminate line noise, or just as an effect.

**release**: speed at which gate blends closed  
**threshold**: volume threshold to open up the gate  
**attack**: speed at which gate blends open

accepts:

audio  
**granulator**  
![](https://www.bespokesynth.com/docs/screenshots/granulator.png)  
granulate live input

**dry**: amount of dry signal to allow through  
**spd r**: randomization of grain speed  
**g oct**: should we add octaves and fifths?  
**pos r**: randomization of grain start point  
**pos**: playback position within the buffer  
**autocapture**: freeze input at this interval  
**spa r**: randomization of time between grains  
**width**: stereo width of grain placement  
**overlap**: number of overlapping grains  
**frz**: freeze the current recorded buffer  
**speed**: speed of grain playback  
**len ms**: length of each grain in milliseconds

accepts:

audio  
**muter**  
![](https://www.bespokesynth.com/docs/screenshots/muter.png)  
mute an incoming signal

**ms**: ramp time to mute/unmute signal  
**pass**: when true, the signal is allowed through

accepts:

audio  
**noisify**  
![](https://www.bespokesynth.com/docs/screenshots/noisify.png)  
multiply input signal by white noise

**width**: how frequently a new noise sample should be chosen  
**amount**: amount of noise to apply

accepts:

audio  
**pitchshift**  
![](https://www.bespokesynth.com/docs/screenshots/pitchshift.png)  
shifts a signal's pitch

**ratioselector**: shortcuts to useful pitch ratios  
**ratio**: amount to pitchshift by (a value of 1 indicates no shift)

accepts:

audio  
**pumper**  
![](https://www.bespokesynth.com/docs/screenshots/pumper.png)  
dip the volume of a signal rhythmically, to emulate a "pumping sidechain" effect

**length**: length of pump  
**amount**: amount to lower volume  
**interval**: the rate to pump  
**curve**: how the volume returns  
**attack**: how sharply the volume drops

accepts:

audio  
**tremolo**  
![](https://www.bespokesynth.com/docs/screenshots/tremolo.png)  
modulate signal's volume rhythmically

**duty**: pulse width of LFO  
**amount**: amount to lower volume  
**interval**: speed of LFO  
**osc**: LFO oscillator type  
**offset**: offsets LFO phase

accepts:

audio

## other

  
**abletonlink**  
![](https://www.bespokesynth.com/docs/screenshots/abletonlink.png)  
synchronizes transport with software and devices that support ableton link

**reset next downbeat**: resets measure count on the next downbeat, to help synchronize to desired phase in session  
**offset ms**: offset in milliseconds to tweak synchronization

  
**clockin**  
![](https://www.bespokesynth.com/docs/screenshots/clockin.png)  
reads in clock pulses from external midi devices to control bespoke's transport

**device**: device to receive from  
**rounding**: precision to round incoming tempo data  
**start offset ms**: offset in milliseconds to tweak synchronization between bespoke and gear  
**smoothing**: how much to smooth incoming tempo

  
**clockout**  
![](https://www.bespokesynth.com/docs/screenshots/clockout.png)  
sends out clock pulses to synchronize external midi devices

**device**: device to target  
**send start**: send a signal to reset the gear to the start of its sequence  
**multiplier**: tempo multiplier for how the gear should respond to the signals

  
**comment**  
![](https://www.bespokesynth.com/docs/screenshots/comment.png)  
a box to display some text, to explain a section of a patch

**comment**: type text here

  
**eventcanvas**  
![](https://www.bespokesynth.com/docs/screenshots/eventcanvas.png)  
schedule values to set over time

**canvas**: canvas of events. canvas controls: -shift-click to add an event -hold shift and drag an event to duplicate -hold alt to drag an event without snapping -hold ctrl while dragging to snap to an interval -hold shift and scroll to zoom -hold alt and grab empty space to move slide the canvas view -hold ctrl and grab empty space to zoom the canvas view  
**interval**: grid for snapping events to  
**drag mode**: direction that elements can be dragged  
**record**: record connected values as they change  
**timeline**: control loop points  
**clear**: delete all elements  
**measures**: length of loop  
**quantize**: quantizes events to grid  
**view rows**: number of visible rows  
**scrollh**: horizontal scrollbar  
**delete**: delete highlighted elements

  
**globalcontrols**  
![](https://www.bespokesynth.com/docs/screenshots/globalcontrols.png)  
interface controls, intended to allow you to use midi controllers to navigate the canvas. controlling these sliders directly with the mouse is not recommended.

**background r**: amount of red in background color  
**scroll x**: emulate horizontal mouse scrolling  
**lissajous g**: amount of green in background lissajous curve  
**lissajous b**: amount of blue in background lissajous curve  
**scroll y**: emulate vertical mouse scrolling  
**zoom**: zoom level  
**background b**: amount of blue in background color  
**x pos**: horizontal panning position  
**background g**: amount of green in background color  
**lissajous r**: amount of red in background lissajous curve  
**y pos**: vertical panning position

  
**grid**  
![](https://www.bespokesynth.com/docs/screenshots/grid.png)  
generic grid, to be used by "script" module, to assist in writing scripts that use grid-based midi controllers

**grid**: patch a grid in here, from a "midicontroller" module  
**momentary**: should clicks be treated as momentary inputs?

accepts:

notes  
**groupcontrol**  
![](https://www.bespokesynth.com/docs/screenshots/groupcontrol.png)  
connect to several checkboxes, and control them all with one checkbox

**group enabled**: controls the connected checkboxes

  
**loopergranulator**  
![](https://www.bespokesynth.com/docs/screenshots/loopergranulator.png)  
use with a "looper" module to play the contents with granular synthesis

**spacing rand**: randomization of time between grains  
**on**: use granular synthesis for looper playback  
**octaves**: should we add octaves and fifths?  
**speed rand**: randomization of grain speed  
**overlap**: number of overlapping grains  
**freeze**: stop advancing looper time  
**width**: stereo width of grain placement  
**loop pos**: playback position within loop  
**pos rand**: randomization of grain start point  
**speed**: speed of grain playback  
**len ms**: length of each grain in milliseconds

  
**multitrackrecorder**  
![](https://www.bespokesynth.com/docs/screenshots/multitrackrecorder.png)  
record several synchronized tracks of audio, to write to disk for mixing in an external DAW

**add track**: add an additional track  
**clear**: clear the audio in the tracks  
**bounce**: write the tracks to your recordings directory  
**record**: record input to the tracks

  
**notetoggle**  
![](https://www.bespokesynth.com/docs/screenshots/notetoggle.png)  
turn a control on or off depending on if there are any input notes

accepts:

notes  
**oscoutput**  
![](https://www.bespokesynth.com/docs/screenshots/oscoutput.png)  
send OSC messages when slider values change or when notes are received

**note out address**: label to send input notes. the message will be sent in the format /bespoke/\[label\] \[pitch\] \[velocity\]  
**slider\***: sends a value to the address. try patching a modulator into this, such as a leveltocv module to send audio levels.  
**label\***: label to send slider value. the message will be sent in the format /bespoke/\[label\] \[value\]  
**osc out address**: destination to send OSC messages to  
**osc out port**: port to send OSC messages to

accepts:

notes  
**prefab**  
![](https://www.bespokesynth.com/docs/screenshots/prefab.png)  
create a collection of modules that can be loaded from the "prefabs" menu. drag and drop modules onto here to add them to the prefab. drag the grey cable to any modules you want to remove from the prefab.

**load**: load a .pfb  
**save**: save as a .pfb file  
**disband**: free all modules from this prefab

  
**push2control**  
![](https://www.bespokesynth.com/docs/screenshots/push2control.png)  
use an ableton push 2 to control bespoke's interface  
**radiosequencer**  
![](https://www.bespokesynth.com/docs/screenshots/radiosequencer.png)  
sequence to only enable one value at a time. patch it to the "enabled" checkbox on several modules to only enable one module at a time. works well in conjunction with "groupcontrol" module.

**length**: length of sequence  
**interval**: rate to advance  
**grid**: patch a grid in here from a "midicontroller" module

accepts:

pulses notes  
**samplebrowser**  
![](https://www.bespokesynth.com/docs/screenshots/samplebrowser.png)  
browse your system for samples. drag samples from here to your desired targets (sampleplayer, drumplayer, seaofgrain, etc)

**\>** : next page  
**<** : previous page

  
**scale**  
![](https://www.bespokesynth.com/docs/screenshots/scale.png)  
controls the global scale used by various modules

**scale**: which set of notes to use  
**tuning**: what frequency does the pitch defined in "note" represent?  
**load KBM**: load KBM file to determine keyboard mapping  
**PPO**: pitches per octave  
**note**: the pitch that maps to the frequency defined in "tuning"  
**load SCL**: load SCL file to determine scale  
**intonation**: which method to use to tune the scale  
**root**: root note of the scale

  
**script**  
![](https://www.bespokesynth.com/docs/screenshots/script.png)  
python scripting for livecoding notes and module control

**a**: variable for the script to use, can be modulation by other sources. access via me.get("a")  
**load**: load selected script  
**c**: variable for the script to use, can be modulation by other sources. access via me.get("c")  
**b**: variable for the script to use, can be modulation by other sources. access via me.get("b")  
**run**: click here to execute the code, or press ctrl-R  
**d**: variable for the script to use, can be modulation by other sources. access via me.get("d")  
**stop**: cancel any events scheduled by this script  
**style**: choose a text theme, from script\_styles.json  
**code**: write code here. press ctrl-R to execute the code, or ctrl-shift-R to just execute the current block.  
**save as**: save the current script  
**loadscript**: choose a script from here, then press "load"  
**?**: show scripting reference

accepts:

pulses notes  
**scriptstatus**  
![](https://www.bespokesynth.com/docs/screenshots/scriptstatus.png)  
shows everything in the current python scope, for debugging

**reset all**: resets scope variables

  
**selector**  
![](https://www.bespokesynth.com/docs/screenshots/selector.png)  
radio button control to only enable one value at a time. patch it to the "enabled" checkbox on several modules to only enable one module at a time. works well in conjunction with "groupcontrol" module.

**selector**: which value should be set to 1

accepts:

notes  
**snapshots**  
![](https://www.bespokesynth.com/docs/screenshots/snapshots.png)  
save and restore sets of values. connect the grey circle to modules to affect all controls on that module. connect the purple circle to a control to affect only that control. shift-click on the grid to store a preset to that square, and click on a grid square to load that preset.

**snapshot label**: assign a label to this snapshot  
**auto-store on switch**: when switching to a new slot, automatically store state in the current slot  
**clear**: clear all snapshots  
**random**: randomize connected controls  
**add**: snapshot the currently connected controls to the next available snapshot slot  
**snapshot**: jump to a snapshot  
**blend**: length of time in milliseconds over which to blend snapshot values  
**store**: when clicking/selecting a snapshot, store into that slot (alternately: hold the shift key)  
**delete**: when clicking/selecting a snapshot, delete that slot (alternately: hold the alt/option key)

accepts:

notes  
**songbuilder**  
![](https://www.bespokesynth.com/docs/screenshots/songbuilder.png)  
large-scale organizer to arrange settings into scenes and then sequence them. this is bespoke's "song mode"

**move left**: move this target left in the scene  
**play from\***: play sequence from this step  
**add target**: add a targeted control for scenes to affect  
**stop**: stop the sequence  
**activate first scene on stop**: when stopping, activate the first scene. it is recommended that you use the first scene as an "off" scene, and have it disable all song elements.  
**pause**: hold the sequence on the current scene  
**loop end**: loop step index that the loop ends  
**move right**: move this target right in the scene  
**value\***: value to use for target in this scene  
**context\***: options for this scene  
**scene\***: name of scene for this step  
**type**: change the control display type for this target  
**bars\***: length in bars that this scene should play for  
**checkbox\***: value to use for target in this scene  
**loop start**: loop step index to start the loop on  
**name\***: name of this scene  
**dropdown\***: value to use for target in this scene  
**change quantize**: when a change should happen after pressing the play button on a scene. "switch" changes immediately, and "jump" changes immediately and also resets the global transport.  
**play**: play the sequence  
**contextmenu\***: options for this step  
**go\***: play this scene  
**use sequencer**: show scene sequencer  
**loop**: enable a loop within the sequence

accepts:

pulses notes  
**timelinecontrol**  
![](https://www.bespokesynth.com/docs/screenshots/timelinecontrol.png)  
control global transport position

**reset**: reset to beginning  
**loop end**: measure end of loop  
**loop start**: measure start of loop  
**dock**: should we dock this module to the UI layer?  
**length**: length of timeline display, in measures  
**measure**: current position. click to jump around.  
**loop**: should we have a looping section?

  
**timerdisplay**  
![](https://www.bespokesynth.com/docs/screenshots/timerdisplay.png)  
displays a timer to indicate how long a patch has been running

**reset**: reset timer to zero

  
**transport**  
![](https://www.bespokesynth.com/docs/screenshots/transport.png)  
controls tempo and current time position

**reset**: reset timeline to zero  
**\+** : increase tempo by one  
**\-** : decrease tempo by one  
**<** : nudge current time backward  
**tempo**: global tempo, in beats per minute  
**swing**: where the halfway point of musical time within the swing interval should fall. a value of .5 represents no swing.  
**timesigtop**: time signature top value  
**timesigbottom**: time signature bottom value  
**swing interval**: interval over which to apply swing  
**play/pause**: stop all audio processing (shift-p)  
**\>** : nudge current time forward

  
**valuestream**  
![](https://www.bespokesynth.com/docs/screenshots/valuestream.png)  
displays a control's value over time. connect the cable to a UI control to see how it is changing.

**speed**: how quickly display should scroll

