## To use the code provided in the folder neural-enhance-master:

* Pre-trained models are not provided. You can download it via this link : https://github.com/alexjc/neural-enhance/releases/tag/v0.3 \
The files `name.pkl.bz2` is to put in the folder containing the file `enhance.py`

* The main file to use to increase the resolution of an image is `enhance.py`. It is possible to use different option in the program with some comand lines. Some examples are visible below:
  * Run the super-resolution script to increase the resolution of a single image, zoom factor 4:1.\
  `python3 enhance.py --type=photo --model=repair --zoom=1 broken.jpg`\
  need the pretrained model : `ne4x-photo-defaut-0.3.pkl.bz2`\
  \
  * Run the super-resolution script to repair JPEG artefacts, zoom factor 1:1.\
  `python3 enhance.py --type=photo --model=repair --zoom=1 broken.jpg`\
  need the pretrained model : `ne1x-photo-repair-0.3.pkl.bz2`\
  \
  * Process multiple good quality images with a single run, zoom factor 2:1.\
  `python3 enhance.py --type=photo --zoom=2 file1.jpg file2.jpg`\
  need the pretrained model : `ne2x-photo-defaut-0.3.pkl.bz2`\

## Remarks:

the programs provided are slightly modified compare to those available in gitHub (https://github.com/alexjc/neural-enhance#1-examples--usage) due to a scipy framework version compatibility issue:\
for Scipy version > 1.0.0 :  functions scipy.ndimage.imread() and scipy.misc.toimage() no longer exist 
* `scipy.ndimage.imread(filename, mode='RGB')` :arrow_right: `imageio.imread(filename, pilmode='RGB')`
* `scipy.misc.toimage()` :arrow_right: `Image.fromarray()`


