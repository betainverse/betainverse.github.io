    Title: Pymol Color By Data
    Date: 2014-10-13T14:27:13
    Tags: pymol

This post expands on [info](http://kpwu.wordpress.com/2007/11/27/pymol-example-coloring-surface-by-b-factor/) from a few other [blog](http://kpwu.wordpress.com/2012/09/11/pymol-custom-spectrum-colors/) posts. 

1. Download data2bfactor.py from [http://pldserver1.biochem.queensu.ca/~rlc/work/pymol/](http://pldserver1.biochem.queensu.ca/~rlc/work/pymol/). 
2. Download spectrumany.py from [http://pymolwiki.org/index.php/Spectrumany](http://pymolwiki.org/index.php/Spectrumany). 
3. Save these scripts to a known location, let's say ~/scripts/. 
4. Open pymol & load your protein structure.
5. Run the scripts you downloaded using the PyMOL> commandline:
```
PyMOL> run ~/scripts/data2bfactor.py
PyMOL> run ~/scripts/spectrumany.py
```
6. Your data should be formatted like this:
```
3	0.677985
4	0.794402
5	0.972709
```
Extra columns can cause problems. Headers might cause problems. If you exported your file from excel, you may have to change your line break format. On a mac, you might see a bunch of ^M characters in your file, so you would use a terminal to do this:
```
tr '\r' '\n' < macfile.txt > unixfile.txt
```
If the file came from windows, you might need to do this:
```
tr -d '\r' < windowsfile.txt > unixfile.txt
```
<!-- more -->
