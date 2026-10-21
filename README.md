This is what everyone has been waiting for: A working MWW trainer notebook using the newer build of Tatertotterson's MWW model generator. 

This training notebook is currently working as of 10/21/2026.

The base model I am using can be found at: https://github.com/TaterTotterson/microWakeWords, but this version is designed to be run within a notebook rather than locally with a web GUI.

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


Using the output file in ESPHome using github:
1. You need both output files the .json and the .tflite. The model outputs 2 .json one that has tater on the front and one without. For this you are going to use the one without.
2. You want to then upload it to a github. You should upload both the .tflite and the .json.

   My personal repo for the ones I have generated is: https://github.com/Rogusliv/RogusMWW . Feel free to add to if you want the files to be publicly available. I will publish it to the repo.
   
3. On the ESPHome editor, add the following block: ESPHome_github_block.yaml
4. If you want to keep the default wake words remove: !replace
5. Edit the path to show the url of the .json of the wake word you want to use. (this should be the RAW url)
6. This should compile. I was not able to get the built in git to work using their GUI, but the manual worked well.

Using the output file in ESPHome using a local file:
1. Create a file in your machine that is visible to the ESPHome system. If you are using docker make sure it is mounted.
2. You want to use the .json without the tater prefix on the name. Drop in your .json and .tflite.
3. Edit the .json to point to your .tflite file in the new location.
4. Drop in the ESPHome_Local_block.yaml" into the config yaml
5. If you want to keep the base wake words, delete the !replace command.
6. Edit the file so the path matches the .json. Be sure to use relative pathing if running in docker.
