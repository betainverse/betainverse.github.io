    Title: Script to show methyls as spheres in Pymol
    Date: 2014-12-10T09:00:50
    Tags: pymol

Here is a pymol script to show methyl groups on your protein as spheres, color-coded by residue type. 

Download the script [here](https://raw.githubusercontent.com/betainverse/methyls/master/pymol/showmethyls.py).

Usage:
Load the script into pymol using the run... item in the pymol File menu to select this script or load it from the Pymol command line, then actually run it using the showmethyls command:

     PyMOL> run /home/userName/path/toscript/showmethyls.py
     PyMOL> showmethyls

Note that you can use the cd command on the pymol command line as you would in bash/tcsh, if you don't remember the exact path to the script by heart. 


![](/img/spherelegend.png)
![](/img/methyls2.png)