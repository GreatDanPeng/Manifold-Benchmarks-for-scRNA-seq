# Manifold Benchmarks for scRNA-seq
UNC Biostats Undergraduate Summer Internships (BUSI) 2023

<img width="1866" alt="poster" src="https://github.com/user-attachments/assets/314c25cb-f642-4c8e-be29-504b9da86dcf" />

## Objectives
* Reproduce the attraction-repulsion spectrum in “Attraction-Repulsion Spectrum…” (Bohm et al., 2022) on both MNIST and Mouse Single-Cell RNA data sets​
```
@article{boehm2022attraction,
  author  = {Jan Niklas Böhm and Philipp Berens and Dmitry Kobak},
  title   = {Attraction-Repulsion Spectrum in Neighbor Embeddings},
  journal = {Journal of Machine Learning Research},
  year    = {2022},
  volume  = {23},
  number  = {95},
  pages   = {1--32},
  url     = {http://jmlr.org/papers/v23/21-0055.html}
}
```
* Add Hessian LLE to the spectrum to determine whether it is a comparable algorithm in terms of visualization and computational intensiveness

## Background
- Neighbor embeddings: family of visualization methods combining attractive force between neighbors with repulsion between all points
- Changing balance between attraction/repulsion → spectrum of embeddings'
- Data
    - MNIST: commonly used, handwritten digits
    - Mouse RNA: 23,822 cells from adult mouse cortex?, split into 133 clusters
      - Inhibitory neurons (warm colors)
      - Excitatory neurons (cool colors)
      - Non-neural cells (neutral colors)

## Methods
Laplacian Eigenmap, t-SNE, UMAP, Hessian LLE

## Attraction-Repulsion Spectrum on MNIST Data Set

The MNIST dataset is a widely used benchmark dataset in the field of machine learning and computer vision. It consists of a collection of handwritten digit images, each of which is 28x28 pixels in size, resulting in a total of 784 features (28 x 28 = 784), aka 'mnist_784'.

## Attraction-Repulsion Spectrum on Mouse Single-Cell RNA Data Set

Here we use and preprocess the Mouse Single-Cell RNA Data Set following the steps in https://github.com/berenslab/rna-seq-tsne, which is a companion repository to our paper https://www.nature.com/articles/s41467-019-13056-x (Kobak & Berens 2019, The art of using t-SNE for single-cell transcriptomics). The dataset can be downloaded in form of read counts from http://celltypes.brain-map.org/api/v2/well_known_file_download/694413985 and http://celltypes.brain-map.org/api/v2/well_known_file_download/694413179 for the VISp and ALM cortical areas, respectively. Only exon counts were used here. The cluster labels and cluster colors were retrieved from http://celltypes. brain-map.org/rnaseq/mouse/v1-alm.

## Comparison of Runtime/Memory for Mouse RNA Data 
For mouse RNA data set: 
- Fastest method: UMAP
- Least Memory used: Laplace Eigenmap
