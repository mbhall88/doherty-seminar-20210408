This repository hosts the slides for my seminar at the Doherty Institute on 08/04/2021.

## Live slides: **<https://doherty-04-21.netlify.app/>**

- [Abstract](#abstract)
- [Install](#install)
- [Usage](#usage)
  - [Serve](#serve)

If you would like to serve the slides locally, then read on. If you are interested in
copying the presentation style, then see my [EBI template][ebi] or my [Nordtheme template][nord].

# Abstract

Bacterial genomes follow a U-shaped frequency distribution whereby most genomic loci are either rare (accessory) or common (core); the union of these is the pan-genome. The alignable fraction of two genomes from a single species can be low (e.g. 50-70%), such that no single reference genome can access all single nucleotide polymorphisms (SNPs). The pragmatic solution is to choose a close reference, and analyse SNPs only in the core genome. Given much bacterial adaptability hinges on the accessory genome, this is an unsatisfactory limitation.
We present a novel pan-genome graph structure and algorithms implemented in the software pandora, which approximates a sequenced genome as a recombinant of reference genomes, detects novel variation and then pan-genotypes multiple samples. The method takes fastq as input and outputs a multi-sample VCF with respect to an inferred data-dependent reference genome, and is available at <https://github.com/rmcolq/pandora>.

Constructing a reference graph from 578 E. coli genomes, we analyse a diverse set of 20 E. coli isolates. We show pandora recovers at least 13k more rare SNPs than single-reference based tools, achieves equal or better error rates with Nanopore as with Illumina data, 6-24x lower Nanopore error rates than other tools, and provides a stable framework for analysing diverse samples without reference bias. We also show that our inferred recombinant VCF reference genome is significantly better than simply picking the closest RefSeq reference.

This is a step towards comprehensive cohort analysis of bacterial pan-genomic variation, with potential impacts on genotype/phenotype and epidemiological studies.

# Install

Firstly, to develop the presentation, you need to have [Hugo][hugo] installed.

```sh
brew install hugo
# also install optional Pygments package for syntax highlighting in presentation
pip3 install Pygments
```

Hugo will serve the presentation as a local static site in your web browser and update as
you make changes in the source code of the presentation.

Next, clone this template in a directory (ideally named for your presentation)

```sh
presentation="awesome_conference"
git clone --recurse-submodules https://github.com/mbhall88/reveal-hugo-ebi "$presentation"
cd "$presentation"
# if you forgot to give the recursive flag when cloning
git submodule update --init --recursive
```

# Usage

## Serve

To serve the presentation in your web browser run the following from the root directory
of the repository.

```sh
hugo serve
```

In your web browser, navigate to <http://localhost:1313/>





[revealjs]: https://revealjs.com/
[hugo]: https://gohugo.io/
[nord]: https://github.com/mbhall88/reveal-hugo-nord
[ebi]: https://github.com/mbhall88/reveal-hugo-ebi
