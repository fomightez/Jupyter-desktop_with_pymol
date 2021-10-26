# Jupyter Desktop Server with PyMOL installed
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/fomightez/Jupyter-desktop_with_pymol/master?urlpath=desktop)

## How to start a remote computing session and open & use PyMOL on the remote desktop

To get started, click on `launch binder` badge at the top of bottom of this page.

After launch, when the linux desktop comes up, choose 'Use default config' button on the left.

In the upper left of the desktop screen, click on `Applications` > select `Run Program...` from the top of the list, and enter `pymol` (all lowercase). Click the `Launch` button below where you entered `pymol`
That will Launch PyMOL on a remote, temporary computer streaming in your browser.

Choose `Skip Activation` at the bottom the dialog box that comes up as PyMOL starts.

Adjust the width of the PyMOL window, if you like, by dragging on the bottom right corner.

Next to any `PyMOL>` prompt you see on the screen, type `fetch` followed by a PDB id and you'll be viewing your choice of molecule.

If you end up making anything useful, such as a session file (ending in `.pse`) or image file, you'll want to download it to your local machine. You'll need to do that from a different interface with the remote machine. Look at the URL of your PyMOL session screen and copy it. It will look similar to the following but be unique in some ways, such as the part in front of `mybinder` may be different depending on where in the global network the remote machine is:

```
https://hub.gke.mybinder.org/user/fomightez-jupyt-ktop_with_pymol-r7gbgfa3/desktop/?token=zdDDLXhXTzSw7Xcg0g1zfg
```

You want to look for `desktop` in front of `/?token..` and copy everything in front of `desktop` to **ANOTHER browser window** and add on `lab` at the end. This will result in something like this example below that's built on the example above:

```
https://hub.gke.mybinder.org/user/fomightez-jupyt-ktop_with_pymol-r7gbgfa3/lab
```

Hit return to load the page. Your generated PyMOL session file (ending in `.pse`) or image file should appear in the list of files in the file navigation panel in the upper. Right-click on the file in the list, and select `Download` from the middle of the list of possible actions.

----

## How to use the PyMOL GUI in general

I list a number of resources for using PyMOL [here](https://github.com/fomightez/pymol-binder#resources).  
There are several tutorials listed towards that bottom of that list that use the graphical user interface for interacting with PyMOL. **Using PyMOL via a mouse and display is how people tpyically use PyMOL.** Those steps should work in sessions launched from here.  However, the top of that list emphasizes using the commands and scripts to interact with PyMOL and allow one to work more reproducibly or accomplish repetitive tasks. 

-----

## How to use PyMOL using scripts and the API

**While using PyMOL via a mouse and display is how people tpyically use PyMOL, it isn't the only way.**  
If you want to use PyMOL reproducibly or do repetitive tasks using scripts and the API, see [here for PyMOL use via commandline on Jupyter using MyBinder](https://github.com/fomightez/pymol-binder).



-----

## Technical details

This repo was originally meant to be able to run `pymol_preview_generator.py` from [here](https://github.com/mmagnus/rna-tools/tree/master/rna_tools/tools/pymol_preview_generator); however, the XFCE desktop doesn't seem to allow the icons to be changed (even using `gio set`), and so that was **a dead-end effort for now**. However, since PyMOL did at leat work in the desktop GUI, I left it in this state and a use case arose later where I could use it for training.

Presently, PyMOL installed here has the [psico](https://pymolwiki.org/index.php/Psico) python module that extends PyMOL with several commands. For example, presenelt [load_aln](https://pymolwiki.org/index.php/Load_aln) and [xfit](https://pymolwiki.org/index.php/xfit) are ready-to-use. Note that the addition of this module means `save` and `fetch` become 'overloaded with extra abilities as described [here](https://pymolwiki.org/index.php/Psico#Initialization) unless you use the `psico.init` approach specified there when importing. The fact psico doesn't even carry all the abilities needed, for example, `xfit` requirs the dependency csb is a reason I like using Binder when installing various combinations of 'extras' to test. This way I know my local installation will remain intact and I can just easily roll the repo back if something breaks, with no effect on anything else.


[Original source repo](https://github.com/yuvipanda/jupyter-desktop-server) allows running Run XFCE (or other desktop environments) on a JupyterHub. Source based on https://github.com/ryanlovett/nbnovnc and a fork of https://github.com/manics/jupyter-omeroanalysis-desktop .

Details on some of the underlying tech is found under 'Details' [here](https://www.ovirt.org/develop/release-management/features/virt/novnc-console.html). `pymol_preivew` added from [here](https://github.com/mmagnus/rna-tools/tree/master/rna_tools/tools/pymol_preview_generator). PyMOL added as described [here](https://github.com/fomightez/pymol-binder).

Originally, dimensions of the desktop geometry were set to '1680x1050' due to [original source repo](https://github.com/yuvipanda/jupyter-desktop-server), but PyMOL interface was overly pixelated; copied '1024x768' geometry from [here](https://github.com/manics/jupyter-omeroanalysis-desktop/blob/napari-binder/jupyter_desktop/jupyter_desktop.py).


This had stopped working apparently when they updated behind-the-scenes of Binder in late summer/eary Fall 2021. Luckily, the headless one [here](https://github.com/fomightez/pymol-binder) continued to work and show it had PyQt5 installed and working which is what I thought was the issue with this one as a I attempted to fix before realizing PyQt5 worked there. And after much fussing around in October 2021, I got it back to working based on that repositories `apt.txt` and `environment.yml` as the basis.

----

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/fomightez/Jupyter-desktop_with_pymol/master?urlpath=desktop)
