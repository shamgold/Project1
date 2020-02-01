# Project1

Shamber Goldstein

January 31, 2020

B ME 450

Project 1: CTD


GitHub: shamgold/Project1

Task:

The goal of Project 1 is to analyze and compare the speed of sound profile for various bodies of water in both winter and summer. This is done by looking at the properties directly and indirectly measured by CTDs on shallow and deep profilers in these areas. The properties of interest to us are salinity, temperature, and density (pressure), as we are able to use these in calculating the speed of sound profile (ssp) for each dive. This requires us to first analyze the number of dives and separate out the data according to this number. 

How I Did It:

I began my code by importing necessary packages including pyplot, numpy, requests, and datetime. After this I created one large function containing all of my code that I would be able to call for all of the research arrays. This function received inputs including the url for the data and the names of the measured properties for each data set, all input as strings. The first section of the function loads in the data. I did this by copying and pasting the text from the bottom of the OOI page where I found data, but replacing a specific url with the function input, allowing it to load in any data. I then converted the file to json so I would be able to extract data from it. This is exactly what I did in the next section. I created separate lists for the salinity, time, temperature, and depth by putting the data points into separate arrays. Next I analyzed the number of dives by testing when the profiler reached near the surface, every time it did I increased the number of dive counts. I then measured when each dive began and ended. I did this by taking the index of the depth data point when it reached near the surface. I was then able to use these indices to calculate and plot the speed of sound profiles for each dive. This was done by creating a function that simply calculated the ssp for inputs of temperature, salinity, and depth. I then called this function in a loop that looped for each dive. The function was called in this loop using the input properties ranging from the index at the start of a dive to the end. The ssps at these indices were then plot against the depths at these indices. Finally, I calculated and plotted the average ssp at each depth. Due to the measured depths not being at the exact same points for each dive, I calculated the average ssps at small ranges of depth. I did this by looping through each measured depth value and checking if it was within a certain range, if it was it would be added to an array that would then by summed and divided by its length to find its average. This average would then be plotted. The loop would then progress to a new range of depth to test and a new index of depth and ssp to look at. This concluded the function. When I called the function for each array in each season I ended up with a number of dives count, a plot of the ssp for each dive, and a plot of the average ssp. Both plots for each array are shown below. 

Results/Plots:

Oregon Shelf Surface Piercing Profiler Mooring: Winter (2 dives)
![alt text](https://github.com/shamgold/Project1/blob/master/(W)OregonShelfSurfacePiercingProfilerMooring.png "P1")

Oregon Shelf Surface Piercing Profiler Mooring: Summer (10 dives)
![alt text](https://github.com/shamgold/Project1/blob/master/(S)OregonShelfSurfacePiercingProfilerMooring.png "P2")

Oregon Offshore Cabled Shallow Profiler Mooring: Winter (9 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(W)OregonOffshoreCabledShallowProfilerMooring.png "P3")

Oregon Offshore Cabled Shallow Profiler Mooring: Summer (9 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(S)OregonOffshoreCabledShallowProfilerMooring.png "P4")

Oregon Offshore Cabled Deep Profiler Mooring: Winter (2 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(W)OregonOffshoreCabledDeepProfilerMooring.png "P5")

Oregon Offshore Cabled Deep Profiler Mooring: Summer (12 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(S)OregonOffshoreCabledDeepProfilerMooring.png "P6")

Oregon Slope Base Shallow Profiler: Winter (9 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(W)OregonSlopeBaseShallowProfiler.png "P7")

Oregon Slope Base Shallow Profiler: Summer (9 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(S)OregonSlopeBaseShallowProfiler.png "P8")

Oregon Slope Base Deep Profiler: Winter (2 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(W)OregonSlopeBaseDeepProfiler.png "P9")

Oregon Slope Base Deep Profiler: Summer (2 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(S)OregonSlopeBaseDeepProfiler.png "P10")

Axial Base Shallow Profiler: Winter (9 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(W)AxialBaseShallowProfiler.png "P11")

Axial Base Shallow Profiler: Summer (9 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(S)AxialBaseShallowProfiler.png "P12")

Axial Base Deep Profiler: Winter (2 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(W)AxialBaseDeepProfiler.png "P13")

Axial Base Deep Profiler: Summer (2 dives)

![alt text](https://github.com/shamgold/Project1/blob/master/(S)AxialBaseDeepProfiler.png "P14")

Conclusions:

1.	Compare the number of dives per day of the shallow profiler vs deep profiler 

In most cases, the number of dives per day for the shallow profilers is much lower than that of the deep profilers. This  makes sense because it takes less time for a shallow profiler to make a dive, so move dives can fit into a 24 hour period.

2.	Where is the maximum value of ssp in each season? Explain why the max ssp should be there?



3.	Compare the ssp profile in day and night of all profilers, explain what you find (effect of day vs night). 


4.	Compare the ssp profile in summer and winter of all profilers, explain what you find(effect of season). 


5.	Compare the average ssp profiles of all profilers recorded at the same day in winter and summer (effect of location). 
