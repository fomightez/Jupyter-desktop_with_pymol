# Jupyter Desktop Server with PyMOL installed
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/fomightez/Jupyter-desktop_with_pymol/master?urlpath=desktop)

This was originally meant to be able to run `pymol_preview_generator.py` from [here](https://github.com/mmagnus/rna-tools/tree/master/rna_tools/tools/pymol_preview_generator); however, the XFCE desktop doesn't seem to allow the icons to be changed (even using `gio set`), and so that was **a dead-end effort for now**. However, since PyMOL does at leat work in the desktop GUI, I am leaving it in this state for now in case a use case arises later.


If you want to use PyMOL reproducibly using scripts and the API, see [here for PyMOL use via commandline on Jupyter using MyBinder](https://github.com/fomightez/pymol-binder).

-----

## Technical details

[Original source repo](https://github.com/yuvipanda/jupyter-desktop-server) allows running Run XFCE (or other desktop environments) on a JupyterHub. Source based on https://github.com/ryanlovett/nbnovnc and a fork of https://github.com/manics/jupyter-omeroanalysis-desktop .

Details on some of the underlying tech is found under 'Details' [here](https://www.ovirt.org/develop/release-management/features/virt/novnc-console.html). `pymol_preivew` added from [here](https://github.com/mmagnus/rna-tools/tree/master/rna_tools/tools/pymol_preview_generator). PyMOL added as described [here](https://github.com/fomightez/pymol-binder).

Originally, dimensions of the desktop geometry were set to '1680x1050' due to [original source repo](https://github.com/yuvipanda/jupyter-desktop-server), but PyMOL interface was overly pixelated; copied '1024x768' geometry from [here](https://github.com/manics/jupyter-omeroanalysis-desktop/blob/napari-binder/jupyter_desktop/jupyter_desktop.py).


----

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/fomightez/Jupyter-desktop_with_pymol/master?urlpath=desktop)
