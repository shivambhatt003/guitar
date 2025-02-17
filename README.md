
Guitar
======

It's a virtual guitar record-a-synthesize-amatronic web application.

[![Demo animation](https://i.imgur.com/afoMtR3.gif)][app]

[Try it out here.][app]

You can copy and paste entire webpages containing guitar tabs and it'll try to load all it can.

Play back notes by pressing "almost any" key (at least on US keyboards),
with the fretboard focused (or no control focused).
You can rock back and forth between different fingers on different keys, or just pick one, whatever feels natural.

Record notes by clicking on the fretboard.
Secondary click is a shortcut to an open string. You can do this easily in real life from any position, so it makes sense to be able to do it from any position on the virtual guitar too.
Tertiary mouse button (middle mouse button) does a bend, although bends are not recorded yet.
Timing is also not recorded yet.
So it's not very useful for recording tabs, although you could certainly use it as an interactive chart at least.

You can choose any scale to highlight,
a feature I first implemented in [Tri-Chromatic Keyboard][].
It should be much more useful here, since you can learn how to play the guitar with it!
(as opposed to an instrument that virtually no-one has, including me)

----

Uses [tuna][] audio effects library.
The guitar synthesis algorithm is from [guitar-synth](https://github.com/getinstinct/guitar-synth).

The tablature parser created for the app is available separately as a module [here][tablature-parser].


## TODO

* Better mobile support.

    - Play back recorded notes with a button.
    
    - Multitouch.

* Make web application self-explanatory and test accessibility.

* Make bending (MMB) less ridiculous.

* Record chords.
  (with multitouch or a modifier key, maybe also have some sort of toggle)

* Strum chords in playback, maybe have up/down arrows for up/down strumming.

* Source mapping, so you can see and keep the rhythm, articulations, and comments as context.

* Record, parse, and play back articulations.
  such as slides, bends, vibratos, hammer-ons, and pull-offs.

* Different sound for sliding than for plucking/picking.

* Different sound in general, ha, since it's not great...

* Support for different tunings.

* Allow configuring the effects chain.
  (at least toggle distortion on/off)

* Clear way set focus to the fretboard for playback (unfocusing the tablature editor), via the keyboard.

* Tablature editor
    
    - Scroll with the playback position.
    
    - Make the playback position indicator different while playing, so it's clearer whether its showing what's playing or what's next.
    
    - Set the position in the song when you click in the tablature editor.
    
    - Handle multi-digit numbers when highlighting notes.
    
    - Insert and overwrite notes with the virtual guitar fretboard (as opposed to just appending (which is a specific form of inserting)).
    
    - Multi-String Cursor mode.
        
        + Shift+click to select from the existing selection anchor
        
        + Disable or override double-click and triple-click... and [quad-click (yeah, for real)](https://github.com/ajaxorg/ace/blob/b8e3198ba8e9fe98cdda85e90f517b94d4452b5e/lib/ace/mouse/default_handlers.js#L226)
        
        + Why does the selection style change on mouseup?
    
    - Clearer overwrite mode cursor
    
    - Custom syntax highlighting
        
        + Highlight tablature with articulations and everything
        
        + Highlight `<<` misalignment markers as erroneous
    
    - Maybe add some padding with `renderer.setPadding`?

    - Paste from `contentEditable` to detect a `<pre>` containing the tabs? Just to eliminate noise, and if it keeps surrounding text (context) while editing, extra output in what you might save / the work in removing it.

* MusicXML? MIDI?


[app]: https://1j01.github.io/guitar/
[tuna]: https://github.com/Dinahmoe/tuna
[tablature-parser]: https://github.com/1j01/tablature-parser
[Tri-Chromatic Keyboard]: https://github.com/1j01/tri-chromatic-keyboard
