+++
weight = 4
+++
{{% section %}}


1. Representation
2. <span style="color: red;font-size: 1.25em;">Single sample inference</span>
3. Multi sample inference
4. Evaluation

---

### Traditional reference-based variant calling

<p class="fragment fade-in-then-semi-out">Assume the sample is the same as the reference</p>
<p class="fragment fade-in-then-semi-out">Create a pileup of the sample on the reference</p>
<p class="fragment fade-in-then-semi-out">Isolated SNPs are quite clear</p>
<p class="fragment fade-in">Indels and clustered variants....not so much</p>

---

### PanRG-based variant calling

<p class="fragment fade-in-then-semi-out">Find the closest recombinant of your sample</p>
<p class="fragment fade-in">Much better starting point - variation (should be) more succinct</p>

---

### Quasi-map reads

<p class="fragment fade-in">Sketch reads - break into $(w,k)$-minimizers</p>
<p class="fragment fade-in">Index shows where reads have matches (<b>hit</b>)</p>
<p class="fragment fade-in">Filter out "isolated" hits - keep clusters</p>
<p class="fragment fade-in">Store $k$-mer coverage information on index $k$-mer graph</p>

---

### Infer closest recombinant

<img src="images/recombinant.png" style="border: none;">

Use dynamic programming within each local PRG to infer the maximum likelihood path

<p class="fragment fade-up"><b>Problem:</b> What if my sample has variants not in the PRG?</p>

---

### Variant discovery

<img src="images/find-candidate.png" style="border: none;" height="450">

Flag suspicious coverage drops on the ML path

---

### Local assembly

<p class="fragment fade-in">Build de Bruijn graph of flagged regions</p>
<p class="fragment fade-in">Enumerate all "likely" paths in dBG</p>
<p class="fragment fade-in">Feed new paths back into PanRG and repeat previous steps</p>

---

## Genotyping

- Poisson model of ($k$-mer) coverage
- Genotype each site (on ML path)

<img src="images/build-prg.png"  height="300" style="border: none;">

---

1. Representation
2. Single sample inference
3. <span style="color: red;font-size: 1.25em;">Multi sample inference</span>
4. Evaluation

---

How do you compare samples if their VCFs are based on different references?

---

### Infer closest recombinant *for the set of genomes*

<p class="fragment fade-in">Infer ML path for each sample</p>
<p class="fragment fade-in">For each ML path, increment counts for each path</p>
<p class="fragment fade-in">Dynamic programming to select most supported path</p>

---

### Make small differences look small

<img src="images/pandora-compare.png" style="border: none;">

---

<img src="images/relax.gif" style="border: none;" height="550">

---

## Recap


<img src="images/pandora.png" style="border: none;" height="600">


{{% /section %}}
