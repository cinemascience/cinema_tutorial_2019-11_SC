# Export a Cinema Database from ParaView 5.7 using the Nyx Tutorial Dataset

This tutorial uses a dataset from the open source Nyx cosmology simulation:

A. S. Almgren, J. B. Bell, M.J. Lijewski, Z. Lukic, E. Van Andel, "Nyx: A Massively Parallel AMR Code for Computational Cosmology" Astrophysical Journal, 765, 39, 2013.  https://amrex-astro.github.io/Nyx/index.html

## Workflow

### Setup ParaView GUI with the dataset

Get to the cinema_tutorial directory; unload/load ParaView; open ParaView with the tutorial dataset:

```
$ cd ~/cinema_tutorial/cinema_tutorial_2019-11_SC
$ module unload paraview           (if needed)
$ module load paraview/5.7.1
$ paraview --data=loadNyxDataset.pvsm
```

In the **Pipeline Browser**, click to highlight **nxy.pvd**

### Setup and export the Cinema database

- Under **View**, select **Export Inspector**  (if needed)
- Select **Export Inspector** tab
- Under **Image Extracts**, select the choices from the dropdown menus:

```
RenderView1         Cinema image database (*.cdb)
```

- Click on the checkbox to establish these choices
- Click on the ellipsis menu to bring up the **Save Screenshot Options** menu
- Use **Camera Model** dropdown menu to select **Phi-Theta**


Select **File** -> **Export Now** to export the Cinema Database.

Note: the VM delay can make it difficult to see the progress of the Cinema database export.  Watch the **Time** counter at the top.  There are 5 timesteps (0 to 4).  When the timestep counter gets to four and the frame resets, the export will be finished.  


### View the nyx.cdb in the CinemaCompare viewer

Open CinemaCompare in Firefox:

```
$ firefox materials/cinema_compare.html
```

If you did not run the workflow, you can still look at an example database:
```
$ firefox materials/example_compare.html
```

Use the sliders to explore the Nyx Cinema Database.  
