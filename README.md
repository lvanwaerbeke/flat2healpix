# flat2healpix
Short python script to convert flat fits mask file to healpix mask map. Setup for KiDS-N mask

**Warning:** some healpy routines are not compatible with recent numpy version (does not accept indices as floats). Two changes had to be made:

1) to fix hp.mollview, in healpy/projector.py line 474

ysize=xsize/2  -->  ysize=xsize//2

2) to fix hp.write_map, in healpy/fitsfunc.py line 203

array=mm2.reshape(mm2.size/1024,1024),  -->  array=mm2.reshape(int(mm2.size/1024),1024),
