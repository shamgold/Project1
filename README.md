# Project1

Shamber Goldstein

January 31, 2020

B ME 450

Project 1: CTD


GitHub: shamgold/Project1, https://github.com/shamgold/Project1/blob/master/Project%201.ipynb 


Task:

The goal of Project 1 is to analyze and compare the speed of sound profile for various bodies of water in both winter and summer. This is done by looking at the properties directly and indirectly measured by CTDs on shallow and deep profilers in these areas. The properties of interest to us are salinity, temperature, and density (pressure), as we are able to use these in calculating the speed of sound profile (ssp) for each dive. This requires us to first analyze the number of dives and separate out the data according to this number. 

How I Did It:

I began my code by importing necessary packages including pyplot, numpy, requests, datetime, and more. After this I created one large function containing all of my code that I would be able to call for all of the research arrays. This function received inputs including the url for the data, the names of the measured properties for each data set all input as strings, and the date and times of sunrise and sunset. The first section of the function loads in the data. I did this by copying and pasting the text from the bottom of the OOI page where I found data, but replacing a specific url with the function input, allowing it to load in any data. I then converted the file to json so I would be able to extract data from it. This is exactly what I did in the next section. I created separate lists for the salinity, time, temperature, and depth by putting the data points into separate arrays. Next I analyzed the number of dives by testing when the profiler reached near the surface, every time it did I increased the number of dive counts. I also plotted the depth vs time so I could visually see the dives. I also plotted the time of sunset and sunrise on the same graph. To do this I had to cenvert the time into seconds sense 1/1/1970. I did this using code from the OOI website that converts the UTC date and time to Pacific date and time, then put in a line of code that puts that into seconds. I then measured when each dive began and ended. I did this by taking the index of the depth data point when it reached near the surface. I was then able to use these indices to calculate and plot the speed of sound profiles for each dive. This was done by creating a function that simply calculated the ssp for inputs of temperature, salinity, and depth. I then called this function in a loop that looped for each dive. The function was called in this loop using the input properties ranging from the index at the start of a dive to the end. The ssps at these indices were then plot against the depths at these indices. Finally, I calculated and plotted the average ssp at each depth. Due to the measured depths not being at the exact same points for each dive, I calculated the average ssps at small ranges of depth. I did this by creating sections for a range of depths. This is necessary because no two measured depth values are the exact same. I then looped through and calculated the average of the ssps at the depths in each section. I then plotted these averages at an index indicating which section of depths it corresponds to. This concluded the function. When I called the function for each array in each season I ended up with a number of dives count, a plot of the ssp for each dive, and a plot of the average ssp. Both plots for each array are shown below. 

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

In summer, the ssp appears to be the highest towards the surface. This makes sense because ssp is mainly dependant on temperature (high temperature gives higher ssp). In Oregon, in summer, it makes sense for the water temperature to be higher at the surface. In winter, the max ssp is reached at a low depth (about 75 m). This could likely be due to cold surface temperatures.

3.	Compare the ssp profile in day and night of all profilers, explain what you find (effect of day vs night). 

By looking at my plots of depth vs time that have the times of sunset and sunrise plotted on them as well, I can see which dives occur at day and at night. From this I can look at the plot of the speed of sound profiles for each dive and see if the dives during day or night have a higher ssp. Based on this, the speed of sound profile generally appears to be higher at night. 

4.	Compare the ssp profile in summer and winter of all profilers, explain what you find (effect of season). 

Generally, in both seasons, the ssp declines with increasing depth. In some cases for both seasons, when a certain depth is reached, the ssp begins to increase. In winter, the ssp declines slowely at first, and then exponentially quicker. In summer, the ssp declines quickly at first, and then exponentially slower. This shows a change in temperature and/or salinity at different depths between the seasons. 

5.	Compare the average ssp profiles of all profilers recorded at the same day in winter and summer (effect of location). 

The Oregon Offshore Cabled Shallow Profiler Mooring and the Oregon Slope Base Shallow Profiler were both taken on June 10/11, 2019. The average ssp plots seem to be following the same pattern, but with the slope base profiler having a higher ssp overall. The Oregon Offshore Cabled Shallow Profiler Mooring and the Oregon Slope Base Shallow Profiler were both taken on January 20/21, 2020. They both have similar ssp values and reach their max ssp values at about 75 m. However, the slope base shallow profiler has a quicker decline in ssp once the max ssp is reached. 
