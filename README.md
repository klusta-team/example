The **KlustaSuite** is an open source spike sorting software suite designed for extracellular recordings obtained with large multielelectrode arrays (with hundreds of channels).

The KlustaSuite contains three programs:

* **SpikeDetekt** for detecting and extracting spikes from raw recordings (written in Python).
* **KlustaKwik** for automatically clustering the detected spikes (written in C++).
* **KlustaViewa** for manually processing the results of the automatic step (written in Python).

It is developed in the [Cortical Processing Laboratory](http://www.ucl.ac.uk/cortexlab) at UCL by:

* Cyrille Rossant (KlustaViewa)
* Shabnam Kadir (SpikeDetekt and KlustaKwik, firstname at cortexlab.net)
* Dan Goodman
* Max Hunter

Please send feedback to Kenneth Harris (firstname at cortexlab.net).

Subscribe to our googlegroups by sending an email to: klustaviewas+subscribe 'at' googlegroups.com


## Repositories

Here are two public Google Drive repositories where we store our software installers and example datasets.

* [Software repository](https://github.com/klusta-team/klustaviewa/releases)
* [Example data repository](https://drive.google.com/folderview?id=0BwTrbfNJNihcaHZjTXEwdk44cFE&usp=sharing)


## Installation instructions

Make sure you have access to the two repositories (see above).

The installation instructions differ according to your operating system.

### Windows users

1. Download and run the all-in-one installer for Windows 64-bit `klustaviewa-setup.exe` [here](https://docs.google.com/uc?export=download&confirm=BXw-&id=0BwTrbfNJNihcY0Rja0xidWgtem8). You may need to restart your computer afterwards to ensure that your system PATH is updated.

2. Download the example package (150MB) `klusta-example.zip` in the **example data repository** and extract it in a directory.

3. Open a terminal and go to that directory.

4. Run the automatic spike detection and clustering (~15 min running time) by typing in the console:

        klusta params.prm

   The PRM file is a text file (written in Python) containing all parameters the KlustaSuite requires in order to spike sort the data. You will see a PRB file too: this text file (written in Python) contains information about the probe. See below for more details.

5. Then, double-click on the KlustaViewa icon on your desktop and do `File > Open` and select `test_hybrid_120sec.kwik`.

6. To update the program, download `klustaviewa<...>.exe` in the **software repository**.


### Linux and Mac OS X

1. Download and install a Python 2.7 distribution (see [further instructions here](install.md)).

2. [Download and extract the KlustaViewa ZIP package here (GREEN .ZIP BUTTON)](https://github.com/klusta-team/klustaviewa/releases/).

3. Open a terminal and type:

        python setup.py install

4. [Install klustakwik](https://github.com/klusta-team/klustakwik#installation) and put its location in your system PATH.

5. Download the example package (150MB) `klusta-example.zip` in the **example data repository** and extract it in a directory.

6. Run the automatic spike detection and clustering (~15 min running time) by typing in the terminal (you need to be in the directory where you extracted the example package):

        klusta params.prm

   The PRM file is a text file (written in Python) containing all parameters the KlustaSuite requires in order to spike sort the data. You will see a PRB file too: this text file (written in Python) contains information about the probe. See below for more details.

7. Run KlustaViewa to open the processed dataset and proceed to the manual step:

        klustaviewa

8. In KlustaViewa, do `File > Open` and select `test_hybrid_120sec.kwik`.

9. To update the program, perform 2 and 3 again.




## Overview of the Kwik format

Our software suite currently accepts a raw data file in [`.dat`](http://neuroscope.sourceforge.net/UserManual/data-files.html) format or `.raw.kwd` format. It creates a set of files in the **Kwik** format.

Let's say you give the name `20140606-007-experiment` to your experiment. The data will be stored in the following files:

    20140606-007-experiment.kwik
    20140606-007-experiment.kwx
    20140606-007-experiment.raw.kwd
    20140606-007-experiment.low.kwd

These files contains data from all shanks.

* The **kwik** file contains all metadata, the spike times (previously `.res`), the clusters (previously `.clu`). It is a relatively small file (a few MB in general).
* The **kwx** file contains the features (previously `.fet`), the masks (previously `.fmask`), the waveforms (previously `.spk`).
* The **raw.kwd** file contains the raw recordings.
* The **low.kwd** file contains the low-pass filtered recordings (LFP).

The **kwik** file contains all scientific information you need in general (spike times and clusters). The **kwx** file contains large volumes of data related to spike sorting (features and waveforms). The **kwd** files contains raw data.

For spike sorting, you can discard the **kwd** files.

You can open these files in MATLAB or any other language with HDF5 support (in Python, with h5py or PyTables). You can export to the old Klusters format with `kwikkonvert`.

See also [the full specification of the format here](https://github.com/klusta-team/kwiklib/wiki/Kwik-format).


## Information about the PRM file

The parameter file (with a name something like myexperiment.PRM) contains further information about how to detect spikes. See the default PRM file [here](https://github.com/klusta-team/kwiklib/blob/master/kwiklib/utils/params_default.py).

[More details here](https://github.com/klusta-team/kwiklib/wiki/Kwik-format#prm).


## Information about the PRB file

[See here](https://github.com/klusta-team/kwiklib/wiki/Kwik-format#prb).


## Details on the test dataset

2 minutes recording, 32 channels at 20kHz, 150MB.


## How to debug SpikeDetekt

If SpikeDetekt is giving strange results, run the debug module to visualize the problem. To do so:

* Download the debug module in this repository (TODO: link)
* Save it somewhere on your computer and note the full path to this file
* Open it in a text editor, and edit it according to the comments
* In your PRM file, add `diagnostics_script_path = "/path/to/debugmodule.py"`
* Run SpikeDetekt as usual.


## Contact

If you have any trouble, bug, comment or suggestion:

  * You can [send a message on the Google group](https://groups.google.com/forum/?fromgroups#!forum/klustaviewas).
  * You can [send us an e-mail](mailto:cyrille.rossant-AT-gmail-com,shabnam-AT-cortexlab-net,kenneth.harris-AT-ucl-ac-uk).

## How to cite

If you have used KlustaKwik for a scientific publication, please cite our paper,
'High-dimensional cluster analysis with the Masked EM Algorithm' by Shabnam N. Kadir, Dan F.M. Goodman and Kenneth D. Harris (2014) Neural Computation, 26:2379-2394.

If you have used SpikeDetekt and/or KlustaViewa, please cite "Spike sorting for large, dense electrode arrays" by Cyrille Rossant, Shabnam N Kadir, Dan F. M. Goodman , John Schulman , Mariano Belluscio , Gyorgy Buzsaki , Kenneth D. Harris (2015). bioRxiv http://dx.doi.org/10.1101/015198
