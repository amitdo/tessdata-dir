# Setting Tesseract's data directory

Tesseract data directory can be set in various ways:

1. a) Using the `--tessdata-dir` flag in the command line.\
   b) Using the Tesseract API (for developers, not regular users):\
       Giving the `Init()` method a string as a value for the `datapath` parameter.\
       Internally 1.a. uses 1.b.  
2. Using `TESSDATA_PREFIX` environment variable.
3. Windows only: Using the `tessdata` directory inside the directory where the Tesseract executable was installed.
4. Using the directory `tessdata` inside the directory which was set during compilation. 
5. If none of the other options where used, Tesseract will fallback to using the current dir as the data dir.

This list is ordered by priority. If the data dir is set by more than one of the above options, Tesseract will use the option which is upper in list.

### Using the `--tessdata-dir` flag in the command line

```
# The path should be /path/to/datadir. 
# The path used here is just an example. 
tesseract image.png out -l eng --tessdata-dir /usr/local/tessdata_fast
```

### Using the `TESSDATA_PREFIX` environment variable

From the terminal:

 
```
# The path should be /path/to/datadir. 
# The path used here is just an example. 
export TESSDATA_PREFIX=/usr/share/tessdata
# Tesseract command tool 
tesseract image.png out -l eng
```

References:

[src/ccutil/ccutil.cpp](https://github.com/tesseract-ocr/tesseract/blob/5.3.0/src/ccutil/ccutil.cpp)

[src/tesseract.cpp](https://github.com/tesseract-ocr/tesseract/blob/5.3.0/src/tesseract.cpp)
