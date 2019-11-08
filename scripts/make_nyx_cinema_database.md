# Export a Cinema Database from ParaView 5.7.0 using the Nyx Tutorial Dataset

This tutorial uses a dataset from the open source Nyx cosmology simulation:

A. S. Almgren, J. B. Bell, M.J. Lijewski, Z. Lukic, E. Van Andel, "Nyx: A Massively Parallel AMR Code for Computational Cosmology" Astrophysical Journal, 765, 39, 2013.  https://amrex-astro.github.io/Nyx/index.html

## Workflow

### Setup ParaView GUI with the dataset

Get to the cinema_tutorial directory; unload/load ParaView; open ParaView with the tutorial dataset:

```
$ cd ~/cinema_tutorial
$ module unload paraview
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
- Back on the Export Inspector tab, under **Root Directory**, input the full path and name for the output Cinema database:

```
/home/in-situ-user/cinema_tutorial/cinema_compare/data/nyx.cdb
```

- Check the **Save Cinema D table** checkbox
- Select **File** -> **Export Now** to export the Cinema Database


### View the nyx.cdb in the CinemaCompare viewer

Open CinemaCompare in Firefox:

```
firefox cinema_compare/cinema_compare.html
```

Use the sliders to explore the Nyx Cinema Database.  
