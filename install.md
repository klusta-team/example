
## Installing a Python distribution for KlustaViewa

This document gives the instructions to install a Python distribution with all dependencies required by the [KlustaSuite](https://github.com/klusta-team/example).


### All systems (Linux, Mac OS X, and Windows)

**Important**: do **not** use your OS package manager (like apt-get) nor pip to install Python and its main dependencies. Use Anaconda or Miniconda instead.

1. [Download Miniconda 64-bit for Python 2.7 corresponding to your OS](http://conda.pydata.org/miniconda.html).

    You can also download the Miniconda installer from a terminal:

    ```
    wget http://repo.continuum.io/miniconda/Miniconda-3.7.0-Linux-x86_64.sh
    ```

2. Open a terminal in the directory where you downloaded Miniconda, and type the following command (the filename might be slightly different in your case). This will install Miniconda in your user account.

    ```
    sh Miniconda-3.7.0-Linux-x86_64.sh
    ```

    On Windows, you'll have to double-click on the `.exe` Miniconda installer.

    You'll be requested to answer a few questions.

    * Press `Enter` to review the license.
    * Press `Space` several times to scroll through the license.
    * Type `yes` and press `Enter`.
    * You'll be requested to choose the installation path. You can accept the default (`~/miniconda`), so just type `Enter`.
    * At the end of the installation, you'll be requested to choose whether this Python distribution should be the default one on your account. You can type `yes` and press `Enter`.
    * Congratulations! Miniconda is now installed.

3. You may need to open a new terminal so that the `conda` command-line tool is available.

4. Type the following commands to install an isolated environment (named `klusta`) of Python containing all the dependencies required by KlustaViewa. We also add extra, non-mandatory dependencies just in case you might need to compile KlustaViewa at some point. This will take several minutes because many packages will be automatically downloaded from the Internet. We specify specific versions for NumPy, pandas, and PyTables, because it has been reported that newer versions don't work with KlustaViewa.

    ```
    conda create -n klusta python=2.7 --yes
    conda install -n klusta scipy pandas=0.12 pytables=3.0 pyqt setuptools pip cython nose ipython-notebook matplotlib --yes
    conda install -n klusta numpy=1.8 --yes
    ```
    
5. Now, activate your 'klusta' environment - you will need to do this before running any application.
    ```
    source activate klusta
    ```

6. You currently have to use `pip` to install the last dependency: PyOpenGL.

    ```
    pip install pyopengl
    ```

7. Now, you can install the KlustaViewa package (that also contains SpikeDetekt) by [following the instructions here](https://github.com/klusta-team/example#linux-and-mac-os-x) (starting from (2)).

## Advanced details

### Dependencies

The following libraries are required:

  * Python 2.7
  * NumPy 1.8 (~~1.9~~ won't work)
  * Pandas = 0.12 (~~0.13 and later~~ won't work)
  * PyTables = 3.0
  * matplotlib
  * PyOpenGL
  * PyQt4


### OpenGL

KlustaViewa requires OpenGL >= 2.1. To find out which version of OpenGL is available on your system:

  * Use [OpenGL Extensions Viewer](http://www.realtech-vr.com/glview/)
  * Alternatively, on Linux, run `glxinfo`.

KlustaViewa works better with a good graphics card as it uses hardware-accelerated visualization. With a lower end graphics card, the software will work but somewhat slower.
