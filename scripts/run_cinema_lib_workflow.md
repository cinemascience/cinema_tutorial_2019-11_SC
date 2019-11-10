# Analyze a Cinema database using cinema_lib command line tools

In this example, we will use cinema_lib command line tools to find contours in slices of Nyx data.  These contours correspond to dark matter halos and connecting filaments.  

## Workflow

### Setup cinema_lib command line tools

```
$ cd ~/cinema_tutorial/cinema_tutorial_2019-11_SC
$ module load cinema
$ cinema --help
```

### Check and validate the database (verbosely)

```
$ cd ~/materials/data/nyx
$ cinema -itvq -d nyxSlice.cdb
```

Take note of the column names (timestep, slice, FILE) and associated column numbers.


### Run the analysis workflow

This workflow will use the command line tools library, cinema_lib, to extract statistical properties from the data and to find and draw isolines to identify features - halos - in the data.  

The computer vision based operations use openCV.  The -cv-grey option takes the column number of the image as its argument.  This database has three columns:

```
timestep,slice,FILE
```

First convert the database image to greyscale.  Note from validating the database that FILE has column=2:

```
$ cinema -d nyxSlice.cdb --cv-grey 2
```

You can check the database column headers if you want.  Notice the added column with the greyscale image.

```
$ cinema -i -d nyxSlice.cdb
```

Each command line directive adds an output column to the Cinema database, creating an updated data.csv.

Now run a series of statistical calculations, each adding a column and moving the FILE column farther down:

```
$ cinema -d nyxSlice.cdb --image-mean 3
$ cinema -d nyxSlice.cdb --image-stddev 4
$ cinema -d nyxSlice.cdb --image-entropy 5
```
Now run the contour finding algorithm.  This takes two arguments: the column number of the FILE image and a contour threshold.  Run it twice to compare different thresholds:

```
$ cinema -d nyxSlice.cdb --cv-contour-threshold 5 70
$ cinema -d nyxSlice.cdb --cv-contour-threshold 5 45
```

### View the nyx.cdb in the CinemaExplorer viewer

Open CinemaCompare in Firefox:
```
$ firefox ~/cinema_tutorial/cinema_tutorial_2019-11_SC/materials/cinema_explorer.html
```

Use the parallel coordinates to select on the different parameters and explore the output database.   
