# assignment-4
This is the fourth assignment of the semester for HES 505.

The fourth part of the course was designed to introduce to you to some of the principles of data visualization, especially in the spatial context, and introduce you to some of the capacity that `R` has for making publication-quality graphics. By the end of this assignment, you should be able to:

* Generate static maps of your study area and the results of your models

* Demonstrate alternative ways for visualizing spatial data.

* Build an interactive map to facilitate data exploration

* Compare and contrast the strengths and benfits of different types of visualization.

## Instructions

1. After you've joined the assignment repository, you should have this file (named Readme.md) inside of a R project named assignment-4-xx where xx is your github username (or initials).

2. Once you've verified that you've correctly cloned the assignment repository, create a new Quarto document. Name this file assignment-4-xxx.qmd and give it a title (like M Williamson Assignment 3). Make sure that you select the html output option (Quarto can do a lot of cool things, but the html format is the least-likely to cause you additional headaches). We'll be using Quarto throughout the course so it's worth checking out the other tutorials in the getting started section.

3. Copy the questions below into your document and change the color of their text.

4. Save the changes and make your first commit!

5. Answer the questions making sure save and commit at least 4 more times (having 5 commits is part of the assignment).

6. Render the document to html (you should now have at least 3 files in the repository: Readme.md, assignment-4-xx.qmd, and assignment-4-xx.html). Commit these changes and push them to the repository on GitHub. You should see the files there when you go to github.com.

## The Data

We'll be using the data and model results from assingment 3. Some of them are located on the server at `/opt/data/2022/assignment03/`. The datasets in this folder include: `celltowers.csv` (a Kaggle dataset depicting the lat/long of cell towers in the US), `cb_2018_us_ua10_500k.shp` (a shapefiled depicting urban areas in the US from the US Census), `ua_list_all.xls` (the attributes of those urban areas), `nlcd.tif` (the National Land Cover dataset for WA, OR, ID, MT, WY), and `roadskm.tif` (the distance, in km, to primary and secondary roads in the same region). In addition, you'll need to use the `tidycensus` package (which we've used in class) download the __population__ and __median income__ datasets from the 5yr American Community Survey dataset at the __block group__ level. You'll aslo need to use the `raster::getData()` function to download the elevation data for the study region and the `terra::terrain()` function to estimate the slope. Finally, load the model fit objects that you saved at the end of Assignment 3 (these are saved in the `/opt/data/2022/assignment04/` folder).

## The Assignment

1. Build a static map of your study area suitable for the Methods section of a journal article. Your map should have a basemap (using either `ggmap` or a hillshade you create, state outlines, and points for the cell phone towers. Use the `fill` aesthetic to color the points by an attribute of your choosing. Add the major cities and label them. Your map should also include a north arrow and a locator map (you'll need `patchwork` for this).  Show your code and the final map.

2. Make a multi-panel figure showing the predictions of your random forests model, your logistic regression model, and the difference between the two predictions (i.e., you should have 3 figures). Remember to include elements that help the reader orient to the map and panel labels. Show your code and the final map.

3. Now make a multipanel plot with the block groups  on the y-axis and the predicted probability of a cell phone tower (with confidence intervals) on the x-axis for both models (i.e., use fill or color to distinguish the predictions for each model). Make a separate plot for each state (i.e., using `facet_wrap` or `patchwork`).  
