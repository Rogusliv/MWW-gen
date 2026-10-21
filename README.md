This is what everyone has been waiting for: A working MWW trainer notebook using the newer build of Tatertotterson's MWW model generator. 

The model I am using can be found at: https://github.com/TaterTotterson/microWakeWords

To use this model generator:
1. Download the notebook file from this git
2. Go to https://colab.research.google.com/ to create a notebook in which to run the program
3. Go create a new notebook.
4. Under File, upload the notebook file.
5. Follow the instructions at the top.

Some tips on using self recorded audio-files in order to improve sensitivity to your voice.
1. Record a ton of files. The more files the more it is tested against your voice in various scenarios. Try different pitches, volumes, tones.
2. Bring the file into your favorite audio editor to break it into individual .wav files. I used audacity due to its free nature and ability to mass export.
3. These should be saved in the following format: .wav 16k mono


Using the output in ESPHome using github:
1. You need both output files the .json and the .tflite. The model outputs 2 .json one that has tater on the front and one without. For this you are going to use the one without.
2. You want to then upload it to a github. My personal repo for the ones I have generated is: https://github.com/Rogusliv/RogusMWW . Feel free to add to if you want the files to be publicly available. 
3. On the ESPHome editor, add the following block:
     
How to incorporate the files into your smart home if using ESPHome satelites:
