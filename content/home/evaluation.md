+++
weight = 5
+++
{{% section %}}


1. Representation
2. Single sample inference
3. Multi sample inference
4. <span style="color: red;font-size: 1.25em;">Evaluation</span>

---

# Aims

- Benchmark precision and recall of SNP calls against single-reference tools
- Quantify the amount of SNPs recovered using our PanRG approach - i.e. do we solve the single-reference problem?

<p class="fragment fade-in">Complicated as we can't rely on coordinate space</p>

---

## Dataset

20 diverse *E. coli* samples with both Illumina and Nanopore sequencing data and reference assemblies  

A PanRG of 578 *E. coli* genomes (~37k genes and intergenic regions)

---

### References for standard callers

<img src="images/tree.png" height="600" style="border: none;">

---


## Precision

$$\frac{TP}{TP+FP}=1-FDR=\frac{correct\ calls}{calls\ made}$$

---

## Precision

<img src="images/probe-map.png" style="border: none;">

---

## Precision

<img src="images/precision.png"  height="550" style="border: none;">

**Warning**: y-axis scales different

---

### Truth set of SNPs

<p class="fragment fade-in">Pairwise alignments of all 20 genomes</p>
<p class="fragment fade-in">Deduplicate pairwise SNPs - is SNP between G1 and G2 the same as the one between G3 and G4?</p>
<p class="fragment fade-up"><b>HARD!</b></p>

---

### Deduplicating pairwise SNPs

<img src="images/pg-variants.png" style="border: none;">

- Pan-genome variant (PgV) are set of pairwise variants of the same colour
- Restrict to biallelic and one allele per genome for each PgV
- 618K PgVs between 20 genomes

---

### Recall (Sensitivity)

$$\frac{TP}{TP+FN}=1-FNR=\frac{correct\ calls}{expected\ calls}$$

---

### Recall (Sensitivity)

<p class="fragment fade-in">Apply VCF calls to reference - mutated ref</p>
<p class="fragment fade-in">Map PgVs to mutated ref</p>
<p class="fragment fade-in">Considered TP if all bases in allele mapping agree</p>

---

### Recall (Sensitivity)

**Key deliverable**

<img src="images/recall.png" style="border: none;">


---

### Recall phylogeny consistency

Single reference callers achieve higher recall for samples in the same phylogroup as the reference genome, but not for rare loci

<img src="images/F8.jpg" style="border: none;">

---

<img src="images/relax.gif" style="border: none;" height="550">

{{% /section %}}
