# STIM

I did these set of python modules during my PhD at IRCAM to handle the creation and transformation of audio and video experimental stimuli.

These python modules allow to easilly handle indexing of audio/video databases, transform audio and video in different ways but also extract different audio features.

I'll do a set of tutorials soon to show how these modules work.

Some interesting modules:

## audio_analysis ##
Extracting features from audio

## super_vp_commands ##
A set of wraper functions around IRCAM super-vp library (needs audiosculpt http://forumnet.ircam.fr/product/audiosculpt-en/)

## video_processing ##
A set of functions to handle video indexing, audio replacement in video, resolution changes, and more...

## Instalation - Python Dependencies ##
These python modules depend on several externals for them to work properly. If you want to use the super_vp_commands or parse sdif files you should isntall all of the above packages.


* Install Homebrew, info [here](https://brew.sh/)

* Install libsnd: 
```
brew install libsndfile
```

* Install sckits.audiolab toolbox :
```
pip install scikits.audiolab"
```


* Install EASDIF

Now to the fun part, 
these scripts use Audiosculpt to generate and parse audio analysis. 
Thus for them to work properly, make sure you installed Audiosculpt from the [ircam forum](http://forumnet.ircam.fr/)

To parse the files generated by audiosculpt automatically with python, (.sdif files) you will need the EASDIF library, which can be installed with the following commands:

```
cvs -d:pserver:anonymous@sdif.cvs.sourceforge.net:/cvsroot/sdif login 
cvs -z3 -d:pserver:anonymous@sdif.cvs.sourceforge.net:/cvsroot/sdif co -P EASDIF_SDIF
cd EASDIF_SDIF
mkdir -p build_EASDIF_x86_64
cd build_EASDIF_x86_64
rm -f CMakeCache.txt
cmake -DEASDIF_DO_PYTHON:bool=on -DPYTHON:STRING=python ..
make install_python_easdif_module_globally
```

or if you have no right to write into your python installation

```
make install_python_easdif_module_locally
```

Now you should change your Audiosculpt Path in 




