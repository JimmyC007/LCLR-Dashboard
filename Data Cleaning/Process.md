# The Data
Two different devices were used to collect the speed and volume data before and after each project. A large challenge was getting the two datasets to match in a way that they could be displayed together seamlessly. Examples of raw data from both sources is available in this folder.
## Tubes

<img align="right" width="250" height="250" src="https://qph.cf2.quoracdn.net/main-qimg-bbaaee4a2bfeb0fedc9ccf9386d7e3e4-lq">
Pneumatic tubes are laid out in pairs across the  
road and capture the speed of vehicles that passed  
over them. From these tubes we can get a text file  
with a line for each vehicle that drove past.  
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>


## Radars
<img align="right" width="200" height="300" src="https://ct-technologyinfo.com/wp-content/uploads/2019/06/Radar-Traffic-Counter.jpg">
Traffic counting radars are fixed to a pole and aimed at a section of the road to count the number of vehicles that pass as well as capture their speed. These devices produce a .log file with a line for each vehicle that drove past.
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>


## Bluetooth
There are bluetooth devices permanently set up at major intersections across the city to capture data about traffic movements on the network. I used this data to analyse the vehicle delay along streets with LCLR projects before and after they were constructed. Delay is calculated as the actual time it takes a vehicle to drive a length of road minus the time it would take if there was no traffic. i.e. If there are no cars on the road it takes 13 seconds to drive the length of Sesame Street, so if it took a vehicle 17 seconds to drive the length of Sesame Street the delay would be 4 seconds (17 - 13 = 4 seconds). 

# Formatting the Raw Data
I needed to do plenty of data wrangling before being able to visualize it in Power BI. Some of the key problems I faced were:
*  Convert the two different raw data types to the same format to be stored as a csv
*  Find a common name for each project site
     *  Often the data sources would have different names for the same location
     *  This needed to be fixed so that data collected before a project could be compared to data collected after at each site
*  Ensure data quality
     *    The radars are generally more reliable than the tubes but there were cases where the device was set up poorly and some data needed to be filtered out

I used R to write a script that imports the data, cleans it, and saves the data in a csv file ready to import to Power BI. The annotated R script is available in this folder. The bluetooth data for delay is accessed through queries to a data warehouse. While the data itself only needed minor cleaning, a matching table had to be created to link to the speed/volume data so that all the data for a project site wass under a single name. 
