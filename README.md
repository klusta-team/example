Example showing how to run the KlustaSuite on a raw dataset.

**Warning**: this repository concerns the upcoming version of the suite that has not been publicly released yet.



## Installation

### Windows users

1. Download and run the [all-in-one installer for Windows 64-bit](TODO). You may need to restart your computer to ensure that your system PATH is updated.

2. Download the [example package (150MB)](TODO) and extract it in a directory.

3. Open a terminal and go in that directory.

4. Run the automatic spike detection and clustering (~15 min running time) by typing in the console:

        klusta params.prm

5. Then, double-click on the KlustaViewa icon on your desktop and do `File > Open` and select `test_hybrid_120sec.kwik`.


### Linux and Mac OS X

1. Download and install a Python distribution (see [further instructions here](TODO)).

2. Download and extract the [software package](TODO).

3. Open a terminal and type:
        
        python setup.py install

4. Download the [example package (150MB)](TODO) and extract it in a directory.

5. Run the automatic spike detection and clustering (~15 min running time) by typing in the terminal (you need to be in the directory where you extracted the example package):

        klusta params.prm

6. Run KlustaViewa to open the processed dataset and proceed to the manual step:

        klustaviewa

7. In KlustaViewa, do `File > Open` and select `test_hybrid_120sec.kwik`.



## Test dataset

2 minutes recording, 32 channels at 20kHz, 150MB.
