# PD-Algo9
Pure Data harmony algorithm 

Project features basic 4 part harmony with a strictly minor melody playing over either a I, IV, or V chord.
As a result the chord progressions are very basic.

The melody generation is passable to present the concept, but not enough for actual listening.
It was made using [drunk] function, so the next note in the generation queue will be close enough to the previous one to prevent it from having that "scattered" sound that occurs when you use an unedited [rand] function. The range the melody is allowed to jump is adjustable in the master screen with the slider "melody movement".
However is no reptition or use of motifs (unlike my ChucK algorithm) so it doesn't produce anything that actual qualifies as a fully formed melody.

Modulation occurs when the algorithm finds it is on a chord that is shared by another scale and the "Ready_to_Modulate" box is checked. It then moves around the circle of fifths to either the dominant or subdominant scale of the current one. While the modulation itself isn't very interesting, the modulation cooldown feature is probably the most interesting part of the project. 

When the "Ready_to_Modulate" box is checked and the algorithm reaches a shared chord there is a chance it will modulate to another scale and start a timer. During the timer the "Cooling_Down" box will be checked instead of the RtM box, so even if the algorithm reaches a shared chord it will not be able to modulate until the timer reaches 99 and the RtM box is rechecked. This is to prevent constant modulation from happening during runtime, which produces a jarring effect for the listener. Modulation cooldown time and modulation probability are both adjustable in the master screen.

The code is unlikely to be used again but serves as a proof of concept which will aid in the creation of a more complicated PureData generative algorithm. Aside from better harmony and melody, new code should not use the obtuse "scale storage" method. It is unnecessary to store every single scale in the program. Scales can be calculated with the the basic intervals and an int value to adjust where the scale starts relative to middle C (or whichever pitch centre you use). This is covered in my "ChucKHarmonyGeneration" project.
