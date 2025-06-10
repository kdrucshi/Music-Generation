# Music-Generation
## Pre-processing
Just like human language, music is also a language composed of various components that effects its production, each component plays its own role in music production. Components such as notes, chords, keys, pitch, duration etc., effects music differently. Notes are music objects [3], that can be fed to algorithms as language in form of notes or sequences (chords). In our study we have extracted such components using python libraries in order to train our deep learning algorithms.
Dataset used- POP909.
Libraries used- music21, Fluidsynth, pretty_midi.
All these libraries have been used for necessary data pre-processing before generating automated music. Thus, for extracting necessary information from MIDI files these libraries are essential.
Music21
Music21 is a python-based toolkit for computer aided musicology, it helps to understand large datasets, to generate music, to understand music etc., main objective of this library is to extract music notation from dataset.


## Fluidsynth
Fluidsynth is a sound synthesizer that allows to generate audio signals or waveforms from MIDI files, it works in Sound Font technology. It can also be used to play MIDI format music files.
pretty_midi
pretty midi is another MIDI file manipulation library that can be used to extract information from big datasets such as POP909. It provides with powerful tools to extract various essential components of music files.
These libraries have been used since:
•	They are python compatible.
•	They are pretty robust.
•	Supports working on large datasets and MIDI files information Extraction.
•	These can help in building plots that are necessary for comparison in our study.
## Notes-
•	A note is a representation for a sound [6].
•	That can be further divided into pitch and duration that forms it.
•	Chords are sequences of notes played on same instrument (monophonic music), consisting of various pitches (frequencies), that when heard together form music. 
•	Thus, in our study note is the basic entity that must be extracted from various MIDI files in order to attain information about the file.
•	All the libraries shown above allows us to extract such information, that is later fed as training data.
### Notes Extraction from midi files
Midi files contains various information about annotations such as note name, pitch, duration, and steps etc. these has to extracted from midi files as they comprise musical grammar. In our study we have used various python libraries to extract this information from midi files. 
Pretty midi is one of the most used libraries for extracting this information, steps involved:
Instrument identification: we have to identify various instruments from the files to make music monophonic. Monophonic music is easily understandable by various deep algorithms.
Midi to notes: pretty midi allows to extract notes from midi files thus we made a function that allows to convert all the midi files to notes and extract essential information i.e., annotations from notes.
 
In this study we have used pitches and durations from files to get train notes and train durations. These are converted to a series of sequences of size 32 to be fed to deep learning algorithms.

Post processing:
After training deep learning models, we receive a sequence, that is composed of array of pitches or note number. Each note number represent a corresponding note name. A generator function has been developed that converts each such note number to corresponding name and add it to the stream of notes. 

Autoencoders
Autoencoders uses unsupervised learning techniques to learn from data, these networks consist of units of inputs and a data reconstruction layer also known as decoders that are fully connected to the hidden layer units [6]. In autoencoders the inputs are encoded to some representation and the decoded to generate information from learnt facts. This technique is also known as representation learning [13]. 
 
Fig: Model summary of Autoencoders
Decoder- it upscales the data or decompresses it to extract information.
Encoder- inputs are passed to encoders also known as latent vector that converts input in the form of a representation.
So basically, autoencoders are to be trained on data reconstruction. We impose a bottleneck on the network that encodes and decodes the data accordingly.

<p align="center">![image](https://github.com/user-attachments/assets/8c99443a-34d2-49cf-b85d-201ee193e479)
<p align="center">Fig: Bottleneck in Autoencoders [14].



