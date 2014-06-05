Example showing how to run the KlustaSuite on a raw dataset.

**Warning**: this repository concerns the upcoming version of the suite that has not been publicly released yet.



## Installation

### Windows users

TODO

### Linux and Mac OS X

TODO



## Running the suite on the test dataset

1. Clone this repository:

        git clone https://github.com/klusta-team/example.git

2. Download the test dataset: 2 minutes recording, 32 channels at 20kHz, 150MB (TODO: link).

3. Run the automatic spike detection and clustering (~15 min fo:

        spikedetekt params.prm
        
4. Run KlustaViewa to open the processed dataset and proceed to the manual step:

        klustaviewa
        
5. In KlustaViewa, do `File > Open` and select `test_hybrid_120sec.kwik`.



