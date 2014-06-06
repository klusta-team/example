Example showing how to run the KlustaSuite on a raw dataset.

**Warning**: this repository concerns the upcoming version of the suite that has not been publicly released yet.



## Installation

### Repositories

* [Software repository](https://drive.google.com/folderview?id=0BwTrbfNJNihcd25Cc2xNN1IwZGM&usp=sharing)
* [Example data repository](https://drive.google.com/folderview?id=0BwTrbfNJNihcaHZjTXEwdk44cFE&usp=sharing)


### Windows users

1. Download and run the all-in-one installer for Windows 64-bit `klustaviewa-setup.exe` in the **software repository**. You may need to restart your computer afterwards to ensure that your system PATH is updated.

2. Download the example package (150MB) `klusta-example.zip` in the **example data repository** and extract it in a directory.

3. Open a terminal and go to that directory.

4. Run the automatic spike detection and clustering (~15 min running time) by typing in the console:

        klusta params.prm

5. Then, double-click on the KlustaViewa icon on your desktop and do `File > Open` and select `test_hybrid_120sec.kwik`.

6. To update the program, download `klustaviewa-0.3.0.beta1.win-amd64-py2.7.exe` in the **software repository**.


### Linux and Mac OS X

1. Download and install a Python distribution (see [further instructions here](install.md)).

2. Download and extract the software package `klustaviewa-0.3.0.beta1.zip` in the **software repository**.

3. Open a terminal and type:
        
        python setup.py install

4. Download the example package (150MB) `klusta-example.zip` in the **example data repository** and extract it in a directory.

5. Run the automatic spike detection and clustering (~15 min running time) by typing in the terminal (you need to be in the directory where you extracted the example package):

        klusta params.prm

6. Run KlustaViewa to open the processed dataset and proceed to the manual step:

        klustaviewa

7. In KlustaViewa, do `File > Open` and select `test_hybrid_120sec.kwik`.

8. To update the program, perform 2 and 3 again.


## Test dataset

2 minutes recording, 32 channels at 20kHz, 150MB.
