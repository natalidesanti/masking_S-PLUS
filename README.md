# MASKING S-PLUS

This repo contains a code and a document explaining how to mask some tiles from the Southern Photometric Local Universe Survey ([S-PLUS](https://www.splus.iag.usp.br/)). It was made as a _term project_ for the discipline [Astronomical databases and astrostatistics in the era of big data](https://uspdigital.usp.br/janus/componente/disciplinasOferecidasInicial.jsf?action=3&sgldis=AGA5926).

## Code description

The code is organized as follows:

   - 1. Text section: explain the general idea behind the work;
   - 2. Main code: 
     - a) Working with the bands: contains the code necessary to get and generate the masks for each band using two different approaches (I) finding the objects and (II) segmenting the image and, then, finding the objects;
     - b) Building the final mask: joining all the masks;
   - 3. SExtractor analysis: uses tables from the masked and unmasked fits images (in each band) to measure the number of found objects, as well the interference in the magnitudes. It compares the original and masked images.

The necessary data to run the notebook (sections 1 and 2) is giving using S-PLUS python interface, and it is in the part 2.a in the notebook. To get access to it, you need to make an account in [S-PLUS cloud](https://splus.cloud/) and log-in in the cell provided in the notebook. In order to organize the data and the results, I create some folders, using `os` (to create the folders: `data/field_name/` and `results/field_name/fits`). You can easily change this cell and choose the best way and to save the things as you want, but you will need to change it in all the save stages of the notebook.

The necessary data to run the part 3 is obtained running [SExtractor](https://www.astromatic.net/software/sextractor/). But do not worries, I upload here the results from it. Otherwise, you can run it by yourself in the `data/` and `results/field_name/fits/` folders, for each respective band and field (after installing SExtractor in your machine and after running the previous parts of the notebook) using:

`$ sex *name_of_your_image* -c configuration_file_of_your_image.sex`

## Document description

Contains a pdf, explaining the motivation, steps and results of this project.

If you have any doubts, complains or suggestions, please, contact me: `natalidesanti@gmail.com`.