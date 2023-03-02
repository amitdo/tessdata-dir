# Setting Tesseract's data directory

Tesseract data directory can be set in various ways:

 1. a) Using the `--tessdata-dir` flag in the command line.\
    b) Using the Tesseract API (for developers, not regular users):\
       Giving the `Init()` method a string as a value for the `datapath` parameter.\
       Internally 1.a. uses 1.b.  
 2. Using `TESSDATA_PREFIX` environment variable.
 3. Windows only: Using the `tessdata` directory inside the directoty where the Tesseract executable was installed.
 4. Using the directory which was set during compilation.
 5. Using the current dir as the data dir.
 

This list is ordered by priority. If the data dir is set by more than one of the above options, Tesseract will use the option which is upper in list.


### Using the `TESSDATA_PREFIX` environment variable

From the terminal:
 
 
```
# The path should be /path/to/datadir. 
# The path used here is just an example. 
export TESSDATA_PREFIX=/usr/share/tessdata
# Tesseract comman tool 
tesseract image.png out -l eng
```
