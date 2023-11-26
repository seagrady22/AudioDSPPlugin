# AudioDSPPlugin
The initial project settings for a visual FFT animator VST i am building in C++ using the juce framework

I will unfortunately not be sharing this project. It is a proprietary project I have been working on for 10+ years

I will however share that this project is a JUCE C++ audio plugin using the Steinberg VST SDK.
  -This means that the VST is platform independent and will be targeted for audio engineers using any DAW
  -For more info on VSTs please reference https://www.steinberg.net/vst-live/
  -Installation: the user will drop the .vst file into a folder and point their daw at the VST

The project will use opengl for matrix operations. I looked at a few others (opencv, eigen, OF, etc ) and will be sticking to openGL as that seems to have a lot of support and stood the test of time

This project will not use any AI. The idea is a reality synth, not growing intelligence models. Though the intelligence models based off this output will be great!

The goal of this project is to do my own DTF (Discrete Fourier Transform) to capture audio from artists to allow them to stem their art into creating visual art.
  -Allowing this in the daw of the artist choice is huge. Its so much already for artists to be working in one daw I have found most artists are not open to learning a bunch of other tools
  -For that reason it will also take the form of a visual synthizer, though really intends to be used for much much more.

With the DTF data the user will take their audio and be return high resolution spectral data from their audio.

The user can then create custom presets to create different parameterizations of the spectral data to create visual art.

The transformation from audio to visual is meant to connect the two. Too often are we left with visuals that, while appealing, have no foundation in the sound.

An end product here is the ability to write scores that generate 3d modeling that connects with audio frequencies. 




