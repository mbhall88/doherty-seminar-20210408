+++
weight = 2
+++
{{% section %}}

### Bacterial Genomes 101

- 85-90% of bacterial genome is genes

- Shared gene content generally used as genome similarity measure

- Bacterial genomes are incredibly diverse &rarr; pan-genome

---

### *Bacterial* pan-genome


<img src="images/pangenome.png"  height="400" style="border: none;">

In an "open" pan-genome, such as *E. coli*, two individuals could share as little as 30%
of their genes<sup style="font-size: small;">1</sup>

<font size="0.1em;">1. Horesh, G. et al. Different evolutionary trends form the twilight zone of the bacterial pan-genome. doi:10.1101&#x2F;2021.02.15.431222.</font>

---

### How should we call SNPs in bacteria?

Spoiler: this is the core of our aim

---

### The single-reference problem

<img src="images/single-ref.png"  height="550" style="border: none;">

---

## Reference bias

<p class="fragment fade-in-then-semi-out">
<b>Hard</b>: missing chunks from reference - result of pan-genome
</p>

<p class="fragment fade-in">
<b>Soft</b>: decreased ability to align as edit distance between reference and sample increases
</p>

---

### Current solutions to reference bias

<p class="fragment fade-in-then-semi-out">
Restrict to similar genomes with a closely related reference - i.e. outbreak
</p>
<p class="fragment fade-in-then-semi-out">
Only analyse core genome SNPs and do gene presence/absence for the accessory genome
</p>
<p class="fragment fade-up">
<b>Problem</b>: Given much bacterial adaptability hinges on the accessory genome, these are unsatisfactory limitations.
</p>

---

## Our solution

<p class="fragment fade-in-then-semi-out">
Decompose pan-genome into atomic units (loci) with representative sequences for each
</p>
<p class="fragment fade-in-then-semi-out">
Construct set of reference graphs of all loci
</p>
<p class="fragment fade-in-then-semi-out">
Map reads (Illumina/Nanopore) to the set of reference graphs
</p>
<p class="fragment fade-in-then-semi-out">
Discover and/or genotype variation for sample(s)
</p>
<p class="fragment fade-up">
<a href="https://github.com/rmcolq/pandora">https://github.com/rmcolq/pandora</a>
</p>

{{% /section %}}
