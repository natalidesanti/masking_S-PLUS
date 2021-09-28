# MASKING S-PLUS

This repo contains a code and a document explaining how to mask some tiles from the Southern Photometric Local Universe Survey ([S-PLUS](https://www.splus.iag.usp.br/)). It was made as a _term project_ for the discipline [Astronomical databases and astrostatistics in the era of big data](https://uspdigital.usp.br/janus/componente/disciplinasOferecidasInicial.jsf?action=3&sgldis=AGA5926).

This work was made with the extremelly helpful contributions from [Maria Luísa Gomes Buzzo](http://lattes.cnpq.br/9829508296992486), [Felipe de Almeida Fernandes](http://lattes.cnpq.br/3565984584227844), [Lilianne Nakazono](http://lattes.cnpq.br/8135231533828484), [Erik Vinicius Rodrigues de Lima](http://lattes.cnpq.br/6523110145757023) and Professors [Claudia Lucia Mendes de Oliveira](http://lattes.cnpq.br/1170240266075175), [Zeljko Ivezic](http://faculty.washington.edu/ivezic/) and [Luis Raul Weber Abramo](http://lattes.cnpq.br/4558796258762790).

## Code description

The code is organized as follows:

   * 1. **Text section:** explain the general idea behind the work (`document/document.pdf`);
   * 2. **Codes:**
     * a) `getting_and_preprocessing_data.ipynb`: get fz images, convert fz to fits, convert fits to RGB images, crops the borders, get and convert the original S-PLUS mask into image/matrix form, save the saturated points;
     * b) `masking-SPLUS.ipynb`: build the masks using computer vision techniques with and without segmentations image;
     * c) `creating_SPLUS_total_mask.ipynb`: get all the masks (for each different band) and join them in one band;
     * d) `SExtractor_analysis.ipynb`: use the tables from the masked and unmasked fits images (in each band) to measure the number of found objects, as well the interference in the magnitudes. It compares the original and masked images.

The necessary data to run the notebook (apart from d section) is giving using S-PLUS python interface. To get access to it, you need to make an account in [S-PLUS cloud](https://splus.cloud/) and log-in in the cell provided in the notebook. In order to organize the data and the results, I create some folders, using `os` (to create the folders: `data/field_name/` and `results/field_name/fits`). You can easily change this cell and choose the best way and to save the things as you want, but you will need to change it in all the save stages of the notebook.

The necessary data to run the part (d) is obtained running [SExtractor](https://www.astromatic.net/software/sextractor/). But do not worries, I upload here the results from it. Otherwise, you can run it by yourself in the `data/` and `results/field_name/fits/` folders, for each respective band and field (after installing SExtractor in your machine and after running the previous parts of the notebook) using:

`$ sex *name_of_your_image* -c configuration_file_of_your_image.sex`

## Document description

Contains a pdf, explaining the motivation, steps and results of this project.

If you have any doubts, complains or suggestions, please, contact me: `natalidesanti@gmail.com`.