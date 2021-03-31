This repository hosts the slides for my seminar at the Doherty Institute on 08/04/2021.

**Live slides: <https://doherty-04-21.netlify.app/>**

[TOC levels=1-3]: #

## Table of Contents
- [Abstract](#abstract)
- [Preprint](#preprint)
- [Run locally](#run-locally)
  - [Requirements](#requirements)
  - [Serve](#serve)

# Abstract

#### Nucleotide-resolution bacterial pan-genomics with reference graphs

Bacterial genomes follow a U-shaped frequency distribution whereby most genomic loci are either rare (accessory) or common (core); the union of these is the pan-genome. The alignable fraction of two genomes from a single species can be low (e.g. 50-70%), such that no single reference genome can access all single nucleotide polymorphisms (SNPs). The pragmatic solution is to choose a close reference, and analyse SNPs only in the core genome. Given much bacterial adaptability hinges on the accessory genome, this is an unsatisfactory limitation.
We present a novel pan-genome graph structure and algorithms implemented in the software `pandora`, which approximates a sequenced genome as a recombinant of reference genomes, detects novel variation and then pan-genotypes multiple samples. The method takes fastq as input and outputs a multi-sample VCF with respect to an inferred data-dependent reference genome, and is available at <https://github.com/rmcolq/pandora>.

Constructing a reference graph from 578 *E. coli* genomes, we analyse a diverse set of 20 *E. coli* isolates. We show `pandora` recovers at least 13k more rare SNPs than single-reference based tools, achieves equal or better error rates with Nanopore as with Illumina data, 6-24x lower Nanopore error rates than other tools, and provides a stable framework for analysing diverse samples without reference bias. We also show that our inferred recombinant VCF reference genome is significantly better than simply picking the closest RefSeq reference.

This is a step towards comprehensive cohort analysis of bacterial pan-genomic variation, with potential impacts on genotype/phenotype and epidemiological studies.

# Preprint

> [Colquhoun, R. M. et al. Nucleotide-resolution bacterial pan-genomics with reference graphs. bioRxiv (2020) doi:10.1101/2020.11.12.380378.](https://doi.org/10.1101/2020.11.12.380378)

# Run locally

These slides are built on top of my [EBI template][template], using [reveal-hugo].

## Requirements

Firstly, to serve the slides locally, you need to have [Hugo][hugo] installed.

```shell
$ brew install hugo
# also install optional Pygments package for syntax highlighting in presentation
$ pip install Pygments
```

Hugo will serve the presentation as a local static site in your web browser and update
as you make changes in the source code of the presentation.

Next, clone this repository

```shell
$ repo="doherty-seminar-20210408"
$ git clone --recurse-submodules "https://github.com/mbhall88/$repo"
$ cd "$repo"
# if you forgot to give the recursive flag when cloning
$ git submodule update --init --recursive
```

## Serve

To serve the presentation in your web browser run the following from the root directory
of the repository.

```shell
$ hugo serve
```

In your web browser, navigate to <http://localhost:1313/>. Every time you make changes
this webpage will auto-reload to reflect those changes.

[hugo]: https://gohugo.io/
[reveal-hugo]: https://github.com/dzello/reveal-hugo
[template]: https://github.com/mbhall88/reveal-hugo-ebi
