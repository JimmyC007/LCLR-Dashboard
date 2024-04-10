# The Data
Two different devices were used to collect the speed and volume data before and after each project. A large challenge was getting the two datasets to match in a way that they could be displayed together seamlessly. Examples of raw data from both sources is available in this folder.
## Tubes
Pneumatic tubes are laid out in pairs across the road and capture the speed of vehicles that passed over them. From these tubes we can get a text file with a line for each vehicle that drove past.
![Photo of pneumatic tubes used to count vehicles and record their speed.](https://qph.cf2.quoracdn.net/main-qimg-bbaaee4a2bfeb0fedc9ccf9386d7e3e4-lq)

## Radars
Traffic counting radars are fixed to a pole and aimed at a section of the road to count the number of vehicles that pass as well as capture their speed. These devices produce a .log file with a line for each vehicle that drove past.
    ![Photo of radar.](https://ct-technologyinfo.com/wp-content/uploads/2019/06/Radar-Traffic-Counter.jpg)

# Formatting the Raw Data
I needed to do plenty of data wrangling before being able to visualize it in Power BI. Some of the key problems I faced were:
*  Convert the two different raw data types to the same format to be stored as a csv
*  Find a common name for each project site
     *  Often the data sources would have different names for the same location
     *  This needed to be fixed so that data collected before a project could be compared to data collected after at each site
*  Ensure data quality
     *    The radars are generally more reliable than the tubes but there were cases where the device was set up poorly and some data needed to be filtered out

I used R to write a script to import the data, clean it, and save the data in a csv file ready to import to Power BI. The annotated R script is available in this folder.
