    Title: Pymol: sphere representation and ionic radii
    Date: 2014-12-18T11:18:41
    Tags: pymol

I just want to point out and reiterate an old [forum message](https://www.mail-archive.com/pymol-users@lists.sourceforge.net/msg04718.html) about using PyMOL to display ions as spheres. The spheres representation shows the van der Waals radius of an atom. Apparently PyMOL stores the nonionic radii by default, 1.73 A for Mg, for example, rather than 0.71 A for Mg++. If you look up the desired ionic radius: 

[https://www.webelements.com/nickel/atom_sizes.html](https://www.webelements.com/nickel/atom_sizes.html)

You can set them in PyMOL using the alter command, to obtain a more appropriate picture:

     PyMOL> alter (elem Ni), vdw=0.83
     PyMOL> rebuild

![](/img/Ni.png)
