# AudioDSPPlugin
The initial project settings for a visual FFT animator VST i am building in C++ using the juce framework

I will unfortunately not be sharing this project. It is a proprietary project I have been working on for 10+ years

I will however share that this project is a JUCE C++ audio plugin using the Steinberg VST SDK.
  
  -This means that the VST is platform independent and will be targeted for audio engineers using any DAW
  
  -For more info on VSTs please reference https://www.steinberg.net/vst-live/
  
  -Installation: the user will drop the .vst file into a folder and point their daw at the VST

The project will use opengl for matrix operations. I looked at a few others (opencv, eigen, OF, etc ) and will be sticking to openGL as that seems to have a lot of support and stood the test of time

The goal of this project is to do my own DTF (Discrete Fourier Transform) to capture audio from artists to allow them to stem their art into creating visual art.
  
  -Allowing this in the daw of the artist choice is huge. Its so much already for artists to be working in one daw I have found most artists are not open to learning a bunch of other tools
  
  -For that reason it will also take the form of a visual synthizer, though really intends to be used for much much more.

With the DTF data the user will take their audio and be return high resolution spectral data from their audio.

The user can then create custom presets to create different parameterizations of the spectral data to create visual art.

The transformation from audio to visual is meant to connect the two. Too often are we left with visuals that, while appealing, have no foundation in the sound.

An end product here is the ability to write scores that generate 3d modeling that connects with audio frequencies. 


TODOs:
Current:
Buffer management: the biggest piece I'm currently working on is an effective algorithm to manage the threading taking place for passing the audio buffer to the visualization thread.  The processAudioBlock function essentially gives me a FIFO that is connected to the audio stream, so missing or dropping packets will be adversely affect the frames that are going to be subsequently drawn

The goal of the dtf algoirthm is to push the audio result into a buffer and let the visualization stay up to data as it can. 
Sometimes vertices will have to be deleted for example, which could cost memory, as more audio information is coming in, these problems present interesting solution spaces

opengl vertex shaders: This is the goal, from what I have seen doing this right looks phenominal. Leveraging GPU support from opengl is a must here at some point but currently am not there yet

front end using JUCE: juce offers such a great API and documentation for using lazy ui updates that do not adversely affect the audio buffer. The goal again is to always be reading the audio buffer, using the ui should always be lock free in that way and should prioritize the DTF and fifo management of the buffer.

Nice-to-haves for the future:
Adding layers of DSP to this so and audio-visual synth would be awesome. It would allow the audio to take shape, and then allow the user to see how adding DSP changing like saturation affects the visual feedback of the sound.


