Final Project Writeups
 
 
Component 1: Transportable Array Interactive
Reason for the Approach:
Slider Component
The sliders individually index time and station, giving the user multiple dimensions in which to move around the data. 

Map 
Using a map to plot the locations of each station is logical as each station is accompanied by coordinates (longitude and latitude). The map provides a visualization of the transportable array in a manner that is understable, geographically. 

Oscillogram
The decision to incorporate an oscillogram is based upon the first component’s requirements, but also it is an easy to understand visualization. 

Spectrogram
We chose a hexbin plot to represent the spectrogram, plotting the absolute value of the seismograph readings to give an impression of the total intensity, rather than show a hexbin version of what is already shown in the oscillogram above it. We borrowed this idea from a ResearchGate post on Spectrograms and Oscillograms.

Audio

Strengths of the Approach:
This approach shows a multidimensional view of earthquake data: location, intensity, and movement. It takes a complex set of data and breaks it into digestible components. 
 
Weaknesses of the Approach:
Several weaknesses arose during the course of compiling component 1. One major weakness is the map component. Although we wanted to originally plot every station and update the color based on each respective station’s intensity readings over time, we were unable and resorted to selecting a specific station, which would geographically appear on the map and the time slider would change the station (marker’s) intensity. Another weakness is arranging and coordinating the multiple plots into one figure. The solution we found was to use matplotlib gridspec.  
Additional Wishes
We thought it would have been useful to turn the time slider into a playable widget, where the user could set the slider where they like and click ‘Play’ to start the visualization. 
Additionally, the station slider could have more utility. As it is, you drag the slider and hope to land on the station you want. An option that lets the user pick a specific station would be more useful. 
Contributions from the Group 
Contribution
Group Member(s)
Primary coding
Walker
Additional contributions to code
Julia
Strategizing, review and feedback
Bradley, Henry, Julia, Walker
Commenting and documentation
Walker
 
 
Component 2: Transportable Array Movie 
Reason for the Approach
Our approach was to use Jupyter to create individual .png image files of seismic activity measured at each station at each point in time. The image files were then zipped and exported, so that we could use MEncoder to stitch them together into a movie, along with a simple cover slide that we made using Microsoft Paint to create an .png image file that was the same size and shape as our figures.
 
To provide context, the image files were set on a basemap that centers the focus on the continental United States. Stations were plotted by longitude and latitude. Color was used to indicate seismic activity at a particular point in time, with a diverging colormap selected to indicate both positive and negative values. The min and max on the color scale were set to include all altitude values in the dataset that are within two standard deviations of the mean. (This choice of outlier removal was made after observing a version of the video that had set the min and max color at the min and max of the altitude values. We found that outlier altitude values were expanding our color bars so far that it was difficult to see variations in color for most of the event. Changing to remove outliers made for a much more impactful video.) The neutral, central color, which shows up as grey in our colorbar, was set at "0" (or no change in altitude). 
 
In our first attempt at creating the video, we ran our code for all 14,400 individual image files. Using an “industry standard” (personal communication, J. Makela, November 26, 2017) of 24 frames per second, this would lead to a long video -- 10 minutes. And, the processing time was also very lengthy (e.g., over 6 hours for only the first step of creating the images).  After reviewing the initial images, we decided to focus on the single, most active hour in the dataset, which fell between 20 minutes and 80 minutes. 
 
What we hope to for individuals to gain out of this visualization is an understanding of how the measurement of seismic activity moves across the distance of the United States over time. This is demonstrated by a “wave” of color that moves from west to east across the continent – moving from near the earthquake epicenter to further away.  
Strengths of the Approach
The movie demonstrates movement over time in a structured space of the continental United States. The viewer is able to see both seismic activity and time variation, as required by the assignment. 
Weaknesses of the Approach
Some information is lost in the complexity of this representation. For example, the station colors provide a sense of positive or negative seismic measurements, however, exact numbers are not available for individual stations in this presentation. 
Additional Wishes 
Looking at our final production, we are excited about what we were able to accomplish. However, one particular aspect that could use discussion and improvement is the way that the time is presented above the graph. Currently, it shows time elapsed in the following format: “0 days HH:MM:SS”. What is odd about our representation is that it uses the times directly from the file, and the video starts from 20 minutes, and ends at 80 minutes. That would not make much sense to a viewer outside of our IS590DV course. This was an easy shorthand for our programming. But, perhaps it would have made more sense to present the full date and time here? Or maybe to adjust the time elapsed to start at zero and run to 60 minutes, so that it would show an hour within the context of our visualization. So, these would be possible directions for improvement. 
Contributions from the Group
Contribution
Group Member(s)
Primary coding
Julia
Additional contributions to code
Walker
Strategizing, review and feedback
Bradley, Henry, Julia, Walker
Commenting and documentation
Julia
Transition from Jupiter code into video
Julia
 
 
 
 
Component 3: UFO Database and Supplemental Data
Reason for the Approach:
We wanted to visualize the number UFO sightings per state up against NIH data on gallons of alcohol consumed per year per capita since 1977. We decided to ask: what is the correlation between UFO sightings and alcohol consumption on a state-by-state basis?  

To do this, we had to bring in a tertiary dataset. The alcohol data was already normalized by state population, so we need to “denormalized” the data so it would match the UFO data. Some things that we considered before we did this: census data is collected every 10 years, and the alcohol dataset was collected from 14-year-olds (14yo) and older. Due to time and data constraints, we found the census data for the year closest to the average, and we found the percentage of those 14 years old and older. Using that data, we found the percentage of 14yo’s and older for each state, and multiplied it by the gallons of alcohol consumed per capita for each state, resulting in the estimated total gallons of alcohol consumed, by state, for each year.

This resulted in… stuff.
and … other stuff

Strengths of the Approach:


Weaknesses of the Approach:
 

Additional Wishes (if anything):

 
Contributions from the Group:
 
Contribution
Group Member(s)
Identification of supplemental dataset
Julia, Henry
Formatting of supplemental dataset
Henry
Primary coding
Henry
Additional contributions to code
??
Strategizing, review and feedback
Bradley, Henry, Julia, Walker
Commenting and documentation
Henry
 
 
Component 4: Infographic
Reason for the Approach: 
We decided the UFO data combined with alcohol consumption would lend itself well to the storytelling style of an infographic. We found a positive correlation between alcohol consumed (per person? Per capita?) and UFO sightings. While this does not mean there is a causal link, our group decided to see if we could use the infographic medium to push an agenda. 
 
Strengths of the Approach: 
Takes large amounts of data from two disparate datasets and presents a single message that unifies the two in a succinct way.  
Doesn’t overwhelm
Only uses data for core message (I sort of already said this). 
Weaknesses of the Approach: 
Bias? Forced correlation? Pretty weak argument...
Lack of detailed explanation? (this can be said of just about any infographic)
Infographics are static, and time is one of the variables in our data. Our IG will fall out of date. 
Might not be using numbers in all the graphs, which further obfuscates the data.  
Additional Wishes (if anything):
We had the choice to use the graphics Canva had to offer (fast and easy), or create the images we had in mind and upload them (time consuming). In the end, we opted to use the design elements available in Canva even though they were different from our original concept. Given infinite time, we would have designed a more custom look. 
 
Contributions from Group:
 
Contribution
Group Member(s)
Brainstorming ideas?
Julia, Bradley
Research?
 
Data analysis?
Henry 
Storyboarding / Messaging?
Bradley, Julia
Layout / Design?
Bradley
Review and feedback?
Bradley, Henry, Julia, Walker
Documentation?
Bradley 
 

