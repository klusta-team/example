
## Installation instructions

This document gives the instructions to install a Python distribution with all dependencies required by the [KlustaSuite](https://github.com/klusta-team/example).



### Windows

We recommend that you install [our Windows package installer that comes with a Python distribution + our software suite](https://github.com/klusta-team/example).



### Linux

**Important**: please avoid using `apt-get` to install Python and the packages. Use Anaconda instead.

  * Step 1: [install Anaconda](http://continuum.io/downloads).
  
      * Download the adequate version (64 bits if possible).
      * Execute the installer. On Linux, you need to type a command similar to:
            
            $ bash Anaconda-1.6.1-Linux-x86_64.sh
      
      * You will need to press Enter or 'yes' at some steps.
  
  * Step 2: execute the following commands:

        $ conda uninstall pandas
        $ conda install pandas=0.12
        $ pip install pyopengl
        $ conda install -c http://conda.binstar.org/asmeurer pyside
        



### Mac OS X

Run the following commands:

    ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
    brew doctor
    brew install python
    brew update
    pip install numpy
    brew install gfortran
    pip install scipy
    brew install pyqt
    brew install freetype
    brew link freetype --force
    ln -s /usr/local/opt/freetype/include/freetype2 /usr/local/include/freetype
    pip install matplotlib
    pip install pandas==0.12
    pip install numexpr
    pip install cython
    brew tap homebrew/science
    brew install hdf5
    pip install tables
    pip install pyopengl

See more details on [this thread in the mailing list](https://groups.google.com/forum/?fromgroups#!topic/klustaviewas/8f173wDGZCw).


## Advanced details

### Dependencies
  
The following libraries are required:
  
  * Python 2.7
  * Numpy
  * Pandas <= 0.12
  * PyTables >= 3.0
  * Matplotlib
  * PyOpenGL
  * either PyQt4 or PySide with OpenGL bindings


### OpenGL
  
KlustaViewa requires OpenGL >= 2.1. To find out which version of OpenGL is available on your system:

  * Use [OpenGL Extensions Viewer](http://www.realtech-vr.com/glview/)
  * Alternatively, on Linux, run `glxinfo`.

KlustaViewa works better with a good graphics card as it uses hardware-accelerated visualization. With a lower end graphics card, the software will work but somewhat slower.
