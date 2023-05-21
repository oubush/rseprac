# Problem 5:
See the problem_5 subdirectory.
A client wishes to put information on our Omniglobe (https://arcscience.com/omniglobe-technology/).
They provided a series of NetCDF files with names like: ozone_8dec2009.nc, ozone_7dec2009.nc, ozone_9dec2009.nc, ... etc.
A python script is used to access the files, extract some data and produce 2D images in PNG format.
The software for the Omniglobe:
• scans the contents of a folder
• generates an animated sequence from the PNG files contained in the directory.
This fragment of the Python script sets up the filenames to be written.
```
# Build up filename
VarName = "Ozone_"
TimeStamp = "2001-01-01" # this could be in the nc file
Frame = str("%04d"%simhour)
MetaData = VarName+TimeStamp+"_"+Frame
fname_out = Home+MetaData+".png"
# create the file
savefig(fname_out, bbox_inches="tight", pad_inches=0.0)
```
In the script fragment above:  
(i) Can you determine the content of the fname_out variable?  
(ii) What information is missing?

# Answer to the problem 5

(i) The content of the `fname_out` variable is a string representing the file name of the PNG image that will be created. It is constructed using various variables and strings concatenated together.  

The format of `fname_out` is: `"{Home}Ozone_2001-01-01_{Frame}.png"`

(ii) In the provided script fragment, the values of th `Home` and `simhour` variables are not shown. 

It can be assumed that the `Home` variable represents the directory path where the PNG file will be saved.

The `simhour` variable seems to represent the hour or time value associated with each frame. In the given script fragment, `Frame` is created by formatting `simhour` to have a length of 4 digits with leading zeros using the `%04d` formatting. 

One would need to ensure that `Home` and `simhour` are assigned appropriate values in the script.

Another example of missing information may be the `TimeStamp`, which is being set to a fixed value `"2001-01-01"`. However, its actual value should be extracted from the nc file to reflect the specific timestamp associated with each frame.

