# assignment-4
This is the fourth assignment of the semester for HES 505.

Now that you've learned a bit about _predicates_ and _measures_ it's time to practice on some vector and raster data.
By the end of this assignment, you should be able to:

* Determine whether geometries are valid before analyzing any data
* Calculate the area of a polygon in a vector data set
* Measure the distance between two different features of a vector object
* Describe how the `adjacent` function works for raster data

## Instructions

1. After you've joined the assignment repository, you should have this file (named Readme.md) inside of a R project named assignment-4-xx where xx is your github username (or initials).

2. Once you've verified that you've correctly cloned the assignment repository, create a new Quarto document. Name this file assignment-4-xxx.qmd and give it a title (like M Williamson Assignment 4). Make sure that you select the html output option (Quarto can do a lot of cool things, but the html format is the least-likely to cause you additional headaches). We'll be using Quarto throughout the course so it's worth checking out the other tutorials in the getting started section.

3. Copy the questions below into your document and change the color of their text.

4. Save the changes and make your first commit!

5. Answer the questions making sure save and commit at least 4 more times (having 3 commits is part of the assignment).

6. Render the document to html (you should now have at least 3 files in the repository: Readme.md, assignment-4-xx.qmd, and assignment-4-xx.html). Commit these changes and push them to the repository on GitHub. You should see the files there when you go to github.com.

## The Data

We will be using the landmarks data table and the shapefile from the Climate and Economic Justice Screening Tool from previous assignments. I've moved the versions for this assignment into the `/opt/data/data/assignment04/` folder to make life easier. 

## The Assignment

1. Load the `cejst_nw.shp` use the correct predicates to determine whether the geometries are valid and to check for empty geometries. If there are empty geometries, determine which rows have empty geometries (show your code).

2. Load the `landmarks_ID.csv` table and convert it to an `sf` object. Now filter to just the hospital records (`MTFCC == "K1231"`) and calculate the distance between all of the hospitals in Idaho. Note that you'll have to figure out the CRS for the landmarks dataset...

3. Filter the `cejst_nw.shp` to just those records from Ada County. Then filter again to return the row with the highest annual loss rate for agriculture (2 hints: you'll need to look at the `columns.csv` file in the data folder to figure out which column is the expected agricultural loss rate and you'll need to set `na.rm=TRUE`when looking for the maximum value). Calculate the area of the resulting polygon.

4. Finally, look at the helpfile for the `terra::adjacent` command. How do you specify which cells you'd like to get the adjacency matrix for? How do you return only the cells touching your cells of interest? Use the example in the helpfile to illustrate how you'd do this on a toy dataset - this will help you learn to ask minimally reproducible examples.

