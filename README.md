# Visualization and Analytics for Defensive Shape and Ball Location Correlation Using Spatiotemporal Soccer Tracking Data
Heather Craddock   - Delaware State University
Thesis in requirements for M.S. Computer Science Degree  

**_NB._** This thesis is a work in progress, due to be presented virtually on July 10th, 2020; code will be added to this public repository after completion of thesis requirements.


## Abstract:
Soccer is the world's most popular sport, and the market for sports analytics is becoming increasingly lucrative as vast sums of money are on the line for winning performances and media streaming rights. Automated analytics tools are becoming more prevalent and increasingly important to improve both the performances of teams and players and the experience of sports fans.

Much of the research that uses player tracking data to analyze team performance focuses on attacking performance, which neglects the wealth of performance information that can be gained using organized defensive positioning. Further, while the low availability of data that combines accurate player and ball positions can inhibit research in this area, the implicit relationship between player movement and ball location can offer useful additional information about team and player performance. Firstly, this research explores the current deficits in data collection and availability as it pertains to spatiotemporal soccer data. Further, this research uses the position of the defensive team to infer the approximate location of the ball from augmented player tracking data, helping to pursue a greater understanding of the added value that object relationship data can provide when solving spatiotemporal analytics problems in the soccer domain. Further, as visualization is an important component of providing useful performance analysis to coaches and players, this research presents a tracking data visualization framework to improve the accessibility of the results of analysis.

## VISUALIZATION
For the visualization component, I used Python and the Bokeh framework to animate the spatiotemporal data, as seen below. Bokeh allows the use of simple components, such as sliders (allowing the user to select the game time), pausing functionality, and custom buttons (such as turning on and off convex hulls and field grid lines).
Additions will include highlighting the ball's predicted zone once integration with the learning mechanism is complete.
## Bokeh 
