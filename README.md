Stat 157 Project 2 - Earthquake Location Visualization
======================================================

Introduction
------------
* Team: **David Barrera**, **Christina Ho**, **Roland Shen**, **Khoa Tran**
* Update code to produce same output as old code on earthquake website and parameterize 
  the function so that for any list of earthquakes in a particular region (i.e. California) 
  it will generate a map showing the correct location.

Preliminary Setup Steps
-----------------------
To run this example you'll need to install the following packages
inside your virtual machine:

    sudo apt-get install libgeos-3.3.3 python-mpltoolkits.basemap python-mpltoolkits.basemap-data python-mpltoolkits.basemap-doc

If you have to use Pandas 0.12.0 for `read_json`, install Pandas with Pip as followed: 

```bash
sudo apt-get install python-dev   
pip install pandas
```

You will also need to install Folium for viewing the plots locally: `pip install folium`. Then, run

```bash
git clone https://github.com/kqdtran/recent-quakes    
cd recent-quakes    
ipython notebook --ip=0.0.0.0 --no-browser --pylab=inline
```  

to reproduce our work in `dugtrio.ipynb`.
    
You can view the plot on your local machine by opening up `map.html`, or you can also see it live at 
http://bl.ocks.org/kqdtran/7063887

Other Information
-----------------    

The USGS [eqa7day-M1.txt data url](http://earthquake.usgs.gov/earthquakes/catalogs/eqs7day-M1.txt)
used in this program has been deprecated.

As suggested by the warning message in the data feed:

    This USGS data file has been deprecated. To continue receiving
    updates for earthquake information you must switch to the new data
    format [http://earthquake.usgs.gov/earthquakes/feed/]. In the
    future, data feeds will be updated and deprecated following our
    official deprecation policy
    [http://earthquake.usgs.gov/earthquakes/feed/policy.php].

you need to upgrade this program to use the new USGS data feed:

http://earthquake.usgs.gov/earthquakes/feed/

The new data feed includes a link for [Programmatic
Access](http://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php).
You should use the [pandas JSON parser](http://pandas.pydata.org/pandas-docs/dev/io.html) to read the
data instead of the `read_csv` function in the original code.

For more information on JSON and pickle and the advantages of each, follow this link: http://pymotw.com/2/json/
For more information on pandas click here: http://pandas.pydata.org/pandas-docs/dev/io.html
