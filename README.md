# carbonfoil

Author: Vedant K. Naik
Affiliation: Michigan State University
Position: Student Technical Assistant I, Facility for Rare Isotope Beams (FRIB)
Email: naik@frib.msu.edu
Overview
This MATLAB runtime based App analyzes energy loss data from particle beams for the Facility for Rare Isotope Beams (FRIB). It filters data, clusters r_para values, calculates various parameters like cumulative fluence and energy loss, fits a polynomial model to the data, and generates plots for each annulus region.
Flow of the code:
1.	Loads data from an Excel file.
2.	Filters out rows where the electric beam current is negative and rows where foil verticle distance is outside the 0-50 mm range.
3.	Filters rows where energy loss is between 0.4 and 0.6.
4.	Extracts the electric beam current and particle/beam charge columns and converts the current to Amperes.
5.	Clusters r_para values using k-means clustering and determines the optimal number of clusters using the silhouette method.
6.	Finds the inner and outer radii of each annulus (ring-like region) formed by the clustering.
7.	Computes the area of each annulus.
8.	Plots the silhouette scores as a function of the number of clusters.
9.	Iterates through each annulus, filters data based on the annulus' inner and outer radii, calculates the particle per second, time differences between timestamps, and cumulative fluence (particle flux).
10.	Fits a 13th-order polynomial to model the relationship between cumulative fluence and energy loss.
11.	Calculates the standard deviation of the energy loss.
12.	For each annulus, plots the polynomial trendline, as well as a shaded region representing one standard deviation above and below the trendline.
