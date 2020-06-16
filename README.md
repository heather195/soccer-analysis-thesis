# Visualization and Analytics for Defensive Shape and Ball Location Correlation Using Spatiotemporal Soccer Tracking Data
Heather Craddock   - Delaware State University
Thesis in requirements for M.S. Computer Science Degree  

**_NB._** This thesis is a work in progress, due to be presented virtually on July 10th, 2020; code will be added to this public repository after completion of thesis requirements.


### Abstract:
Soccer is the world's most popular sport, and the market for sports analytics is becoming increasingly lucrative as vast sums of money are on the line for winning performances and media streaming rights. Automated analytics tools are becoming more prevalent and increasingly important to improve both the performances of teams and players and the experience of sports fans.

Much of the research that uses player tracking data to analyze team performance focuses on attacking performance, which neglects the wealth of performance information that can be gained using organized defensive positioning. Further, while the low availability of data that combines accurate player and ball positions can inhibit research in this area, the implicit relationship between player movement and ball location can offer useful additional information about team and player performance. Firstly, this research explores the current deficits in data collection and availability as it pertains to spatiotemporal soccer data. Further, this research uses the position of the defensive team to infer the approximate location of the ball from augmented player tracking data, helping to pursue a greater understanding of the added value that object relationship data can provide when solving spatiotemporal analytics problems in the soccer domain. Further, as visualization is an important component of providing useful performance analysis to coaches and players, this research presents a tracking data visualization framework to improve the accessibility of the results of analysis.

### Data Processing Techniques:
Due to the limited data availability (discussed in the thesis document and to be added here soon), it was important to use creative data processing techniques to compensate for missing or inaccurate data, as well as make the most out of the data available. This included multiple methods, one of which is oversampling limited data over a Gaussian distribution. 

By generating a Gaussian distribution for each defensive player, given the mean as the original *(x,y)* at a time, *t*, a spread, and a number of points to generate, *n*, we can augment the original formation with data generated over each individual point's distribution. If this is done for each defensive player (11 players), and one ball, from *11+1* data points, and one formation, we can generate *(11+1)n* data points and *n* corresponding ball locations, all of which differ from the original formation but can still represent a similar formation of players.

In addition, continuous *x* and *y* data can also be discretized into **_zones_**, which represent segments of the soccer field as they may be seen by players or coaches analyzing the game. For instance, a coach may visualize four *channels* through which their team can attack or maintain defensive shape, and thus the field can be divided into four along the *y*-axis. They may also consider the field in *thirds*: an attacking third, midfield third, and defensive third, and thus the field can be divided into three along the *x*-axis. Different granularity of zones will be analyzed when considering the ball location correlation problem.

### Defensive Shape and Ball Location Correlation
Given these defensive players from the data, and a ball location, we can set up a supervised learning problem where the position of each player, given as the zone they occupy or the count of individuals per zone, is given as an input to a learning network, with the zone location of the ball as the output. Oversampling can aid in this, as oversampled players at a single timestep will cause the more occupied zones to be weighted more heavily. This component is in progress at the time of the most recent update. 

### Visualization
For the visualization component, I used Python and the Bokeh framework to animate the spatiotemporal data, as seen below. Bokeh allows the use of simple components, such as sliders (allowing the user to select the game time), pausing functionality, and custom buttons (such as turning on and off convex hulls and field grid lines).
Additions will include highlighting the ball's predicted zone once integration with the learning mechanism is complete, as well as live data regarding the team in possesion and the area and spread of the convex hull.

![viz](http://heathercraddock.com/resources/viz1.gif)
