C-----------------------------------------------------------------------
C  			quantizerTester                  
C-----------------------------------------------------------------------
C
C  This pd patch creates "generative music" in conjunction with a Elektron 
C  Digitone synthesizer.
C
C  It uses a "quantizer" modeled after Harmonaig Instruo eurorack module. 
C  https://www.modulargrid.net/e/instruo-harmonaig
C  The Instruo module is a chord generating quantizer.
C
C  Pure Data sends the Instruo-like generated midi chords to the Elektron 
C  Digitone. The Pure Data patch generates the chords according to a Euclidian 
C  rhythm patch and randomizes the voicing and the inversions of the chords.
C
C  The Digitone synthesizes the sounds, arpeggiates the chords, and provides 
C  a midi clock to Pure Data for the Euclidian rhythm. The Digitone also 
C  synthesizes a drone note from the root of the generated chord.
C
C  Please see https://youtu.be/WFSqDPm5UyM for an example of it's use.
C
C-----------------------------------------------------------------------
C  Requirements:   Pure Data <https://puredata.info/downloads/pure-data>
C-----------------------------------------------------------------------
C
Usage:  The file quantizerTester.pd is the parent patch which contains the 
        rest of the modules.

              Explaination of the primary patches:
midiClockIn:  Gets the midi clock from the Digitone and bangs out on 1/16th note
              intervals.
euclidRhythm: Bangs out a randomly varying euclidian rhythm.  This patch uses the 
              patches eSeq, euclidR, expDist, setctl, and setctl2.
quantizer:    This patch models the Instruo by creating four note chords with various
              quality, voicing, and inversions.  The root note for the chords can 
              either be input to the patch or set in the patch. This patch uses the 
              patches quality, voicing, invert, setctl, and setctl2.

Contributing: Any contributions to this project are welcome.

Acknowledgements: I'd like to thank Acreil for sharing his Pure Data patches. Namely; 
                  pois, rseq, and euclid, to create Euclidian rhythm patches used here.

