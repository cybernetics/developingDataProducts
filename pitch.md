Developing Data Products Course Project
========================================================
author: Xing Su
date: February 19, 2015

Estimating Variance
========================================================
transition: rotate
**Variance** is a statistical measure of spread of a given distribution.

For a discrete variable $X$, variance is calculated by

$$\sigma^2 =\frac{1}{n}\sum_{i=1}^n (X_i - \bar X)^2$$

where $X_i$ represents the observations, $\bar X$ represents the mean, and $n$ represents number of observations.

Since we rarely know the population statistics and are often provided with only a sample, we can estimate it using the ~~sample statistics~~.

Why does dividing by n-1 make the estimator unbiased?
========================================================

There are **two** ways of estimating the population variance using a sample:

$$S^2_{unbiased} = \frac{\sum_{i=1}^n (X_i - \bar X)^2}{n-1} ~~~\mbox{and}~~~ S^2_{biased} = \frac{\sum_{i=1}^n (X_i - \bar X)^2}{n}$$

The **unbiased estimator** is more commonly used and is a ~~better~~ estimate. The only difference between the two calculations is the denominator--so ***why does dividing by $n-1$ make the estimator unbiased and better?***

To show this empirically, we will leverage a [Shiny Application](https://sxing.shinyapps.io/courseProject/) to simulate and analyze the variance estimates.


Shiny App
========================================================

The ~~Simulation Experiment~~ will perform the following:

<small>1. create a population distribution by drawing a number of observations from values 1 to 20</small>
<small>2. draw a number of samples of specified size from the population</small>
<small>3. compare the individual sample variances and the true population variance</small>
<small>4. show the effects of sample size vs accuracy of variance estimated</small>

The user will be able to control the **number of oberservations**, **number of samples**, and **sample size** to generate relevant plots using `ggplot2` and Google visualiztions.

Graphing Example
========================================================
**Google Visualization Plot Example from Shiny App:**
<!-- Histogram generated in R 3.1.2 by googleVis 0.5.8 package -->
<!-- Thu Feb 19 23:27:44 2015 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataHistogramID1bb639b888bd () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 26.69 
],
[
 18.49 
],
[
 19.25 
],
[
 24.89 
],
[
 28.01 
],
[
 29.85 
],
[
 14.81 
],
[
 39.44 
],
[
 30.89 
],
[
 25.61 
],
[
 36.44 
],
[
 38.69 
],
[
 51.16 
],
[
 30.21 
],
[
 35.4 
],
[
 19.81 
],
[
 27.05 
],
[
 30.4 
],
[
 25.84 
],
[
 27 
],
[
 32.76 
],
[
 36.16 
],
[
 33.41 
],
[
 7.61 
],
[
 34.29 
],
[
 28.16 
],
[
 33.05 
],
[
 28.04 
],
[
 39.25 
],
[
 22.69 
],
[
 30.21 
],
[
 36.96 
],
[
 45.84 
],
[
 22.41 
],
[
 35.24 
],
[
 38.09 
],
[
 36.04 
],
[
 43.8 
],
[
 27.84 
],
[
 28.61 
],
[
 18.24 
],
[
 9.69 
],
[
 33.49 
],
[
 28.36 
],
[
 32.41 
],
[
 40.44 
],
[
 25.85 
],
[
 31.16 
],
[
 21.05 
],
[
 19.21 
],
[
 29.09 
],
[
 31.41 
],
[
 12.2 
],
[
 21.09 
],
[
 26.44 
],
[
 24.64 
],
[
 27.89 
],
[
 19.69 
],
[
 33.16 
],
[
 43.16 
],
[
 13.49 
],
[
 23.24 
],
[
 20.25 
],
[
 18.04 
],
[
 48.84 
],
[
 23.96 
],
[
 30.85 
],
[
 34.16 
],
[
 46.41 
],
[
 38.8 
],
[
 37.89 
],
[
 38.21 
],
[
 28.76 
],
[
 36.29 
],
[
 29.29 
],
[
 33.96 
],
[
 16.56 
],
[
 20.21 
],
[
 48.81 
],
[
 25.36 
],
[
 19.96 
],
[
 19.24 
],
[
 18.64 
],
[
 31.49 
],
[
 33.29 
],
[
 32.96 
],
[
 28.05 
],
[
 25.89 
],
[
 28.04 
],
[
 46.21 
],
[
 28.56 
],
[
 34 
],
[
 31.6 
],
[
 38.65 
],
[
 35.96 
],
[
 22.65 
],
[
 23.89 
],
[
 22.84 
],
[
 28.21 
],
[
 19.41 
],
[
 28.45 
],
[
 29.09 
],
[
 30.01 
],
[
 19.44 
],
[
 30.24 
],
[
 27.01 
],
[
 34.2 
],
[
 19.84 
],
[
 19.01 
],
[
 34.21 
],
[
 18.84 
],
[
 26.29 
],
[
 24.44 
],
[
 33.69 
],
[
 24.8 
],
[
 41.49 
],
[
 27.36 
],
[
 20.41 
],
[
 41.09 
],
[
 16.25 
],
[
 14.04 
],
[
 18.56 
],
[
 16.36 
],
[
 29.61 
],
[
 20.6 
],
[
 18.45 
],
[
 9.89 
],
[
 30.4 
],
[
 23.04 
],
[
 30.65 
],
[
 31.44 
],
[
 14.85 
],
[
 47.89 
],
[
 20.49 
],
[
 36.8 
],
[
 25.36 
],
[
 31.6 
],
[
 38.76 
],
[
 32.04 
],
[
 24.05 
],
[
 28.01 
],
[
 24.76 
],
[
 9.21 
],
[
 43.24 
],
[
 34.45 
],
[
 25.36 
],
[
 24.24 
],
[
 34.36 
],
[
 43.76 
],
[
 24.81 
],
[
 32.04 
],
[
 18.29 
],
[
 29.16 
],
[
 48.69 
],
[
 13.84 
],
[
 44.36 
],
[
 31.81 
],
[
 35.16 
],
[
 31.36 
],
[
 39.29 
],
[
 37.41 
],
[
 16.8 
],
[
 33.65 
],
[
 20.81 
],
[
 29.49 
],
[
 37.89 
],
[
 30.2 
],
[
 30.29 
],
[
 43.8 
],
[
 26.84 
],
[
 16 
],
[
 26.36 
],
[
 42.04 
],
[
 13.01 
],
[
 27.84 
],
[
 18.96 
],
[
 37.56 
],
[
 25.69 
],
[
 35.04 
],
[
 33.8 
],
[
 15.04 
],
[
 28.21 
],
[
 56.76 
],
[
 16.2 
],
[
 37.89 
],
[
 34.04 
],
[
 37.24 
],
[
 30.29 
],
[
 19.16 
],
[
 45.56 
],
[
 35.29 
],
[
 25.45 
],
[
 45.41 
],
[
 20.29 
],
[
 22.81 
],
[
 49.96 
],
[
 23.09 
],
[
 28.21 
],
[
 33.56 
],
[
 10.76 
],
[
 50.61 
],
[
 25.81 
],
[
 34.25 
],
[
 26.44 
],
[
 17.6 
],
[
 26.49 
],
[
 26.56 
],
[
 20.89 
],
[
 43.49 
],
[
 36.56 
],
[
 21.76 
],
[
 48.36 
],
[
 17.84 
],
[
 15.21 
],
[
 29.56 
],
[
 38.69 
],
[
 32.61 
],
[
 30.64 
],
[
 10.05 
],
[
 30.21 
],
[
 19.76 
],
[
 23.01 
],
[
 8.81 
],
[
 27.4 
],
[
 26.69 
],
[
 25.89 
],
[
 14.09 
],
[
 19.44 
],
[
 43.84 
],
[
 31.89 
],
[
 22.56 
],
[
 26.2 
],
[
 10.65 
],
[
 20.56 
],
[
 30.01 
],
[
 16.45 
],
[
 29.61 
],
[
 26.81 
],
[
 27.25 
],
[
 44 
],
[
 28.69 
],
[
 37.01 
],
[
 23.01 
],
[
 32.69 
],
[
 18.56 
],
[
 30.49 
],
[
 28.69 
],
[
 22.84 
],
[
 41.85 
],
[
 23.4 
],
[
 25.29 
],
[
 21.65 
],
[
 33.76 
],
[
 40 
],
[
 34.64 
],
[
 29.29 
],
[
 22.45 
],
[
 22.24 
],
[
 16.76 
],
[
 15.21 
],
[
 33.01 
],
[
 35.64 
],
[
 30.09 
],
[
 42.69 
],
[
 21.09 
],
[
 14.04 
],
[
 42.29 
],
[
 56.04 
],
[
 41.8 
],
[
 30.61 
],
[
 29.49 
],
[
 25.04 
],
[
 37.29 
],
[
 47.16 
],
[
 41.04 
],
[
 29.29 
],
[
 21.81 
],
[
 23.01 
],
[
 22.2 
],
[
 26.01 
],
[
 37.4 
],
[
 23.2 
],
[
 27.65 
],
[
 35.8 
],
[
 41.36 
],
[
 34.36 
],
[
 36.01 
],
[
 25.25 
],
[
 28.4 
],
[
 45.8 
],
[
 43.44 
],
[
 18.84 
],
[
 24.2 
],
[
 41.96 
],
[
 23.44 
],
[
 22.81 
],
[
 30.16 
],
[
 20.01 
],
[
 15.44 
],
[
 30.61 
],
[
 28.6 
],
[
 34.45 
],
[
 28.01 
],
[
 24.76 
],
[
 25.96 
],
[
 21.69 
],
[
 18.84 
],
[
 30.8 
],
[
 30.04 
],
[
 59.16 
],
[
 51.85 
],
[
 32.65 
],
[
 16.09 
],
[
 41.01 
],
[
 29.29 
],
[
 28.69 
],
[
 14.89 
],
[
 23.89 
],
[
 35.81 
],
[
 34.09 
],
[
 42.44 
],
[
 26.56 
],
[
 35.45 
],
[
 13.6 
],
[
 25.16 
],
[
 45.04 
],
[
 13.21 
],
[
 34.89 
],
[
 20.16 
],
[
 32.29 
],
[
 26.41 
],
[
 41.05 
],
[
 18.61 
],
[
 26.65 
],
[
 25.84 
],
[
 36.49 
],
[
 43.96 
],
[
 9.61 
],
[
 25.81 
],
[
 47.05 
],
[
 48.21 
],
[
 23.49 
],
[
 44.96 
],
[
 10.36 
],
[
 33.84 
],
[
 25.84 
],
[
 18.6 
],
[
 42.69 
],
[
 38.09 
],
[
 20.24 
],
[
 27.76 
],
[
 38.2 
],
[
 40.09 
],
[
 38.69 
],
[
 30.2 
],
[
 25.8 
],
[
 27.36 
],
[
 26.16 
],
[
 41.84 
],
[
 24.29 
],
[
 28.09 
],
[
 47.56 
],
[
 31.69 
],
[
 28 
],
[
 39.61 
],
[
 36.36 
],
[
 33.61 
],
[
 35.16 
],
[
 34.89 
],
[
 27.61 
],
[
 30.96 
],
[
 23.04 
],
[
 24.49 
],
[
 32.09 
],
[
 36.64 
],
[
 29.56 
],
[
 30.89 
],
[
 30.49 
],
[
 30.24 
],
[
 23.01 
],
[
 23.2 
],
[
 48.49 
],
[
 28.6 
],
[
 30.49 
],
[
 9.89 
],
[
 23.44 
],
[
 16.64 
],
[
 37.65 
],
[
 18.69 
],
[
 20.24 
],
[
 39.04 
],
[
 33.56 
],
[
 30.69 
],
[
 21.61 
],
[
 38.56 
],
[
 23.56 
],
[
 24.69 
],
[
 23.8 
],
[
 31.56 
],
[
 30.89 
],
[
 21.61 
],
[
 19.21 
],
[
 16.01 
],
[
 15.04 
],
[
 26.56 
],
[
 21.76 
],
[
 37.49 
],
[
 14.44 
],
[
 21.56 
],
[
 22.81 
],
[
 44.25 
],
[
 24.65 
],
[
 43.09 
],
[
 26.89 
],
[
 19.29 
],
[
 25.24 
],
[
 35.29 
],
[
 37.96 
],
[
 53.84 
],
[
 30.09 
],
[
 24.25 
],
[
 25.64 
],
[
 45.24 
],
[
 12.41 
],
[
 34.56 
],
[
 30.44 
],
[
 22.65 
],
[
 40.69 
],
[
 23.89 
],
[
 22.8 
],
[
 40.36 
],
[
 45.24 
],
[
 30.29 
],
[
 34.09 
],
[
 30.81 
],
[
 21.56 
],
[
 14.21 
],
[
 33.81 
],
[
 43.56 
],
[
 45.25 
],
[
 8.21 
],
[
 28.45 
],
[
 45.8 
],
[
 35.61 
],
[
 27.44 
],
[
 25.96 
],
[
 14.61 
],
[
 19.2 
],
[
 31.21 
],
[
 25.21 
],
[
 26.89 
],
[
 37.89 
],
[
 38.41 
],
[
 32.29 
],
[
 11.84 
],
[
 34.56 
],
[
 22.76 
],
[
 31.16 
],
[
 17.29 
],
[
 36.45 
],
[
 29.96 
],
[
 25.65 
],
[
 27.76 
],
[
 26.64 
],
[
 23.96 
],
[
 32.69 
],
[
 43.56 
],
[
 29.89 
],
[
 28.96 
],
[
 35.64 
],
[
 28.56 
],
[
 21.6 
],
[
 33.21 
],
[
 15.96 
],
[
 32.49 
],
[
 19.61 
],
[
 49.45 
],
[
 24.2 
],
[
 25.04 
],
[
 22.96 
],
[
 35.89 
],
[
 28.36 
],
[
 12.44 
],
[
 19.56 
],
[
 19.8 
],
[
 35.89 
],
[
 27.64 
],
[
 27.24 
],
[
 33.4 
],
[
 36.49 
],
[
 46.44 
],
[
 33 
],
[
 29.21 
],
[
 34.69 
],
[
 34.89 
],
[
 19.56 
],
[
 21.89 
],
[
 34.16 
],
[
 42.29 
],
[
 35.61 
],
[
 44.84 
],
[
 28.64 
],
[
 26.16 
],
[
 30.24 
],
[
 30.25 
],
[
 26.96 
],
[
 48.36 
],
[
 39.61 
],
[
 16.44 
],
[
 25.41 
],
[
 30.44 
],
[
 28.09 
],
[
 35.4 
],
[
 21.61 
],
[
 20.81 
],
[
 36.84 
],
[
 39.85 
],
[
 31.21 
],
[
 37.09 
],
[
 30.76 
],
[
 21.61 
],
[
 29.09 
],
[
 20.01 
],
[
 21.76 
],
[
 34.16 
],
[
 30.44 
],
[
 49.04 
],
[
 32.16 
],
[
 16.84 
],
[
 31.76 
],
[
 25.64 
],
[
 38.49 
],
[
 33.29 
],
[
 13.96 
],
[
 23.81 
],
[
 30.36 
],
[
 27.44 
],
[
 26.05 
],
[
 33.04 
],
[
 36.96 
],
[
 18 
],
[
 36.69 
],
[
 40.65 
],
[
 39.96 
],
[
 21.44 
],
[
 32.69 
],
[
 32.49 
],
[
 25.2 
],
[
 13.69 
],
[
 47.89 
],
[
 44.01 
],
[
 15.25 
],
[
 34.21 
],
[
 38.49 
],
[
 30.6 
],
[
 22.16 
],
[
 23.61 
],
[
 17.09 
],
[
 26.49 
],
[
 34.16 
],
[
 25 
],
[
 47.05 
],
[
 28.89 
],
[
 39.89 
],
[
 36.56 
],
[
 22.16 
],
[
 17.69 
],
[
 13.85 
],
[
 28.16 
],
[
 14.89 
],
[
 29.65 
],
[
 31.29 
],
[
 31.76 
],
[
 31.16 
],
[
 29.29 
],
[
 35.49 
],
[
 25.29 
],
[
 34.64 
],
[
 30.29 
],
[
 28.36 
],
[
 33.29 
],
[
 39.01 
],
[
 33.65 
],
[
 12.49 
],
[
 36.64 
],
[
 34.96 
],
[
 17.29 
],
[
 27.01 
],
[
 15.85 
],
[
 29.96 
],
[
 18.61 
],
[
 28.21 
],
[
 38.04 
],
[
 35.29 
],
[
 9.21 
],
[
 29.56 
],
[
 25.69 
],
[
 47.45 
],
[
 30.49 
],
[
 48.84 
],
[
 29.41 
],
[
 24.84 
],
[
 10.49 
],
[
 12.8 
],
[
 34.84 
],
[
 50.81 
],
[
 12.96 
],
[
 29.6 
],
[
 31.64 
],
[
 20.09 
],
[
 36.49 
],
[
 32.01 
],
[
 31.09 
],
[
 31.04 
],
[
 29.01 
],
[
 41.85 
],
[
 20.56 
],
[
 26.85 
],
[
 40.09 
],
[
 51.04 
],
[
 15.81 
],
[
 34.8 
],
[
 45.04 
],
[
 32.04 
],
[
 26.04 
],
[
 24.16 
],
[
 33.6 
],
[
 33.4 
],
[
 20.44 
],
[
 21.05 
],
[
 22.04 
],
[
 29.69 
],
[
 43.29 
],
[
 20.6 
],
[
 28.16 
],
[
 24.45 
],
[
 31.84 
],
[
 29.44 
],
[
 26.21 
],
[
 16.24 
],
[
 28.01 
],
[
 27.61 
],
[
 47.61 
],
[
 31.16 
],
[
 21.24 
],
[
 56.36 
],
[
 29.64 
],
[
 32.61 
],
[
 31.65 
],
[
 35.76 
],
[
 33.61 
],
[
 23.24 
],
[
 19.29 
],
[
 29.44 
],
[
 44.84 
],
[
 26.85 
],
[
 34.36 
],
[
 37.8 
],
[
 27.96 
],
[
 36.24 
],
[
 35.61 
],
[
 29.41 
],
[
 23.85 
],
[
 23.41 
],
[
 23.84 
],
[
 33.24 
],
[
 31.25 
],
[
 43.44 
],
[
 39.64 
],
[
 19.69 
],
[
 26.36 
],
[
 12.49 
],
[
 26.81 
],
[
 34.21 
],
[
 30.84 
],
[
 39.96 
],
[
 68.2 
],
[
 34.36 
],
[
 22.2 
],
[
 23.61 
],
[
 33.29 
],
[
 33.64 
],
[
 25.41 
],
[
 22.45 
],
[
 28.69 
],
[
 38.49 
],
[
 25.36 
],
[
 33.84 
],
[
 29.05 
],
[
 23.84 
],
[
 27.24 
],
[
 18.6 
],
[
 27.96 
],
[
 42.69 
],
[
 47.8 
],
[
 19.41 
],
[
 38.85 
],
[
 18.69 
],
[
 16.96 
],
[
 46.96 
],
[
 23.4 
],
[
 28.56 
],
[
 42.76 
],
[
 33.36 
],
[
 20.41 
],
[
 62.49 
],
[
 27.16 
],
[
 24.65 
],
[
 30.04 
],
[
 13.65 
],
[
 26.09 
],
[
 39.44 
],
[
 41.16 
],
[
 45.36 
],
[
 38.24 
],
[
 14.96 
],
[
 30.8 
],
[
 38.81 
],
[
 27.84 
],
[
 36.16 
],
[
 23.84 
],
[
 9.49 
],
[
 33.89 
],
[
 42.36 
],
[
 8.24 
],
[
 37.64 
],
[
 39.29 
],
[
 33.45 
],
[
 7.76 
],
[
 25.44 
],
[
 35.81 
],
[
 28.69 
],
[
 16.45 
],
[
 24.36 
],
[
 42.09 
],
[
 32.41 
],
[
 27.56 
],
[
 21.76 
],
[
 48.76 
],
[
 35.81 
],
[
 23.21 
],
[
 31.41 
],
[
 42.84 
],
[
 34.29 
],
[
 22.6 
],
[
 47.69 
],
[
 25.24 
],
[
 18.21 
],
[
 37.04 
],
[
 16.45 
],
[
 46.29 
],
[
 27.69 
],
[
 30.96 
],
[
 44.61 
],
[
 40.01 
],
[
 20.64 
],
[
 29 
],
[
 30.41 
],
[
 39.76 
],
[
 38.44 
],
[
 42.56 
],
[
 33.4 
],
[
 27.41 
],
[
 32.21 
],
[
 19.84 
],
[
 12.49 
],
[
 39.21 
],
[
 17.56 
],
[
 34.81 
],
[
 12.84 
],
[
 27.61 
],
[
 8.89 
],
[
 40.64 
],
[
 32.29 
],
[
 25.01 
],
[
 31.01 
],
[
 28.89 
],
[
 32.76 
],
[
 37.01 
],
[
 19.56 
],
[
 28.44 
],
[
 29.89 
],
[
 39.76 
],
[
 13.36 
],
[
 30.21 
],
[
 24.04 
],
[
 35.24 
],
[
 21.2 
],
[
 18.29 
],
[
 36.45 
],
[
 27.24 
],
[
 10.01 
],
[
 27.29 
],
[
 27.09 
],
[
 34.09 
],
[
 16.24 
],
[
 56.56 
],
[
 25.36 
],
[
 33.44 
],
[
 27.89 
],
[
 14.85 
],
[
 36.76 
],
[
 26.4 
],
[
 20.64 
],
[
 33.01 
],
[
 23.09 
],
[
 31.8 
],
[
 8.64 
],
[
 14.8 
],
[
 24.61 
],
[
 32.21 
],
[
 41.61 
],
[
 21.96 
],
[
 37.01 
],
[
 10.6 
],
[
 43.09 
],
[
 33.21 
],
[
 12.84 
],
[
 25.76 
],
[
 14.36 
],
[
 35.69 
],
[
 25.64 
],
[
 23.8 
],
[
 56.24 
],
[
 29.96 
],
[
 41.24 
],
[
 37.6 
],
[
 34.45 
],
[
 31.36 
],
[
 25.6 
],
[
 28.84 
],
[
 38.89 
],
[
 24.96 
],
[
 37.45 
],
[
 37.44 
],
[
 28.24 
],
[
 25.49 
],
[
 24.21 
],
[
 33.81 
],
[
 24.01 
],
[
 35.61 
],
[
 18.21 
],
[
 28.36 
],
[
 31.56 
],
[
 40.41 
],
[
 27.36 
],
[
 37.24 
],
[
 27.24 
],
[
 44.64 
],
[
 35.65 
],
[
 34.96 
],
[
 18.05 
],
[
 29.25 
],
[
 40.21 
],
[
 31.65 
],
[
 33.29 
],
[
 22.09 
],
[
 13.29 
],
[
 37.41 
],
[
 27.69 
],
[
 26.36 
],
[
 31.56 
],
[
 26.44 
],
[
 22.96 
],
[
 24.69 
],
[
 36.24 
],
[
 18.09 
],
[
 33.4 
],
[
 45.64 
],
[
 32.01 
],
[
 15.84 
],
[
 25 
],
[
 23.16 
],
[
 23.6 
],
[
 34.21 
],
[
 16.65 
],
[
 29.85 
],
[
 43.04 
],
[
 50.04 
],
[
 44.01 
],
[
 19.21 
],
[
 27.96 
],
[
 30.24 
],
[
 24.36 
],
[
 26.69 
],
[
 34.49 
],
[
 26.64 
],
[
 14.09 
],
[
 23.24 
],
[
 15.45 
],
[
 33.81 
],
[
 33.84 
],
[
 30.2 
],
[
 26.81 
],
[
 23.24 
],
[
 19.21 
],
[
 24.04 
],
[
 29.2 
],
[
 23.76 
],
[
 34.41 
],
[
 25.21 
],
[
 53.29 
],
[
 45.44 
],
[
 25.21 
],
[
 35.01 
],
[
 22.49 
],
[
 37.05 
],
[
 18.29 
],
[
 35.04 
],
[
 14.16 
],
[
 38.49 
],
[
 27.61 
],
[
 31.89 
],
[
 30.64 
],
[
 41.56 
],
[
 31.96 
],
[
 33.49 
],
[
 26.01 
],
[
 18.21 
],
[
 38.76 
],
[
 37.09 
],
[
 54.84 
],
[
 36.44 
],
[
 34.81 
],
[
 25.09 
],
[
 39.45 
],
[
 29.81 
],
[
 24.76 
],
[
 23.61 
],
[
 20.64 
],
[
 25.69 
],
[
 26.76 
],
[
 36.2 
],
[
 30.6 
],
[
 25.36 
],
[
 43.01 
],
[
 20.76 
],
[
 38.85 
],
[
 32.01 
],
[
 16.21 
],
[
 25.25 
],
[
 35.49 
],
[
 20.45 
],
[
 25.76 
],
[
 55.89 
],
[
 28.49 
],
[
 26.09 
],
[
 34.89 
],
[
 49.29 
],
[
 27.81 
],
[
 38.76 
],
[
 19.96 
],
[
 36.76 
],
[
 41.45 
],
[
 32.61 
],
[
 19.01 
],
[
 36.36 
],
[
 36.21 
],
[
 43.76 
],
[
 28.21 
],
[
 24.21 
],
[
 29.41 
],
[
 31.81 
],
[
 28.45 
],
[
 23.96 
],
[
 17.81 
],
[
 46.81 
],
[
 41.85 
],
[
 22.16 
],
[
 22.44 
],
[
 29.41 
],
[
 39.04 
],
[
 29.09 
],
[
 30.65 
],
[
 24.56 
],
[
 28.21 
],
[
 27.36 
],
[
 30.61 
],
[
 32.01 
],
[
 9.84 
],
[
 34.24 
],
[
 40.04 
],
[
 15.61 
],
[
 31.61 
],
[
 33.61 
],
[
 12.25 
],
[
 51.49 
],
[
 44.09 
],
[
 38.89 
],
[
 60.49 
],
[
 45.76 
],
[
 33.61 
],
[
 27.21 
],
[
 18.44 
],
[
 15.09 
],
[
 18.96 
],
[
 25.81 
],
[
 36.16 
],
[
 38.85 
],
[
 21.84 
] 
];
data.addColumn('number','estVar');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartHistogramID1bb639b888bd() {
var data = gvisDataHistogramID1bb639b888bd();
var options = {};
options["allowHtml"] = true;
options["height"] = "200px";
options["legend"] = {position: 'none'};
options["title"] = "Distribution of Biased Sample Variances";
options["histogram"] = { hideBucketItems: true, bucketSize: 2 };
options["hAxis"] = { title: 'Values', showTextEvery: 3};
options["vAxis"] = { title: 'Frequency'};

    var chart = new google.visualization.Histogram(
    document.getElementById('HistogramID1bb639b888bd')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "corechart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartHistogramID1bb639b888bd);
})();
function displayChartHistogramID1bb639b888bd() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartHistogramID1bb639b888bd"></script>
 
<!-- divChart -->
  
<div id="HistogramID1bb639b888bd" 
  style="width: 500; height: 200px;">
</div>
**`ggplot2` Plot Example from Shiny App:**
![plot of chunk unnamed-chunk-2](pitch-figure/unnamed-chunk-2-1.png) 

