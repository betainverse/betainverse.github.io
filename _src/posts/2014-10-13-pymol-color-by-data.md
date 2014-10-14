    Title: Pymol Color By Data
    Date: 2014-10-13T14:27:13
    Tags: pymol

This post expands on [info](http://kpwu.wordpress.com/2007/11/27/pymol-example-coloring-surface-by-b-factor/) from a few other [blog](http://kpwu.wordpress.com/2012/09/11/pymol-custom-spectrum-colors/) posts. 

1. Your data should be in a tab-delimited text file, formatted like this:

        3	0.677985
        4	0.794402
        5	0.972709

2. You may need to remove extra columns and/or headerscan cause problems. If you exported your file from excel, you may have to change your line break format. From a mac, you might see a bunch of ^M characters in your file. You can use a terminal to do one of these commands to fix the file:

        tr '\r' '\n' < macfile.txt > unixfile.txt
        tr -d '\r' < windowsfile.txt > unixfile.txt

3. Save this data file to a known location, let's say /Users/username/Documents/datafile.txt. It might make things easier to avoid having spaces in file or folder names. It seems to be important to use the absolute filename, rather than using shortcuts like ```~```. 
4. Download data2bfactor.py from [http://pldserver1.biochem.queensu.ca/~rlc/work/pymol/](http://pldserver1.biochem.queensu.ca/~rlc/work/pymol/). 
5. Download spectrumany.py from [http://pymolwiki.org/index.php/Spectrumany](http://pymolwiki.org/index.php/Spectrumany). 
6. Save these scripts to a known location, let's say ~/scripts/. 
7. Open pymol & load your protein structure.
8. Run the scripts you downloaded using the PyMOL> commandline:

        PyMOL> run ~/scripts/data2bfactor.py
        PyMOL> run ~/scripts/spectrumany.py

9. Make a named selection for the set of residues you want to color:

        PyMOL> select MyChainA, 3TGN and chain A and not resn Zn
 
10. You may want to set all the b-factor data for your selection to 0 or to some other number beforehand, because any residues not mentioned in your data file will retain their original crystallographic B-factor:

        PyMOL> alter MyChainA, b=0

11. Now load your data onto your selection using the data2b_res function defined within data2bfactor.py:

        PyMOL> data2b_res MyChainA, /Users/username/Documents/datafile.txt

11. Now color by B-factor. If you are lucky and the color gradient you want is already included in Pymol, you can use the function spectrum:

        PyMOL> spectrum b, rainbow, MyChainA, minimum=0.6, maximum=1

12. You will need to play around with minimum and maximum to optimize the image according to your data. 
13. If you want a color gradient not already defined in Pymol, you will need to use the spectrumany command:

        PyMOL> spectrumany b, red gray80, MyChainA, minimum=0.6,maximum=1

14. Now use the Display menu to make sure the Background is not set to be opaque, and ray trace the image:

        PyMOL> ray

15. Save your image and your session!

![](/img/Zn_hNOE.png)
<!-- more -->
