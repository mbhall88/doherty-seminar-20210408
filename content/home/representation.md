+++
weight = 3
+++
{{% section %}}



#### Acknowledgements

<div style="display: flex;align-items: center;margin-left: auto; margin-right: auto; width: 50%;">
    <img src="images/rachel.jpeg"  height="150" style="border: none;box-shadow: none">
    <span style="">Rachel Colquhuon</span>
</div>

<div style="display: flex;align-items: center;">
    <img src="images/leandro.jpg"  height="100" style="border: none;box-shadow: none">
    <span style="">Leandro Ishi</span>
    <img src="images/zam.jpg"  height="100" style="border: none;box-shadow: none">
    <span style="">Zam Iqbal</span>
    <img src="images/leah.jpg"  height="100" style="border: none;box-shadow: none">
    <span style="">Leah Roberts</span>
</div>

<div style="font-size: 0.7em;">
<ul>
<li>Kerri Malone (EBI)</li>
<li>Martin Hunt (EBI)</li>
<li>Brice Letcher (EBI)</li>
<li>Jane Hawkey (Monash Uni)</li>
<li>Sophie George (Oxford)</li>
<li>Louise Pankhurst (Oxford/Edinburgh)</li>
</ul>
</div>

---

1. <span style="color: red;font-size: 1.25em;">Representation</span>
2. Single sample inference
3. Multi sample inference
4. Evaluation

---

### Representation of pan-genome reference graphs

<p class="fragment fade-in-then-semi-out">
Local PRG (population reference graph) represents one locus
</p>
<p class="fragment fade-in-then-semi-out">
PanRG (pan-genome reference graph) is the set of all local PRGs
</p>
<p class="fragment fade-in-then-semi-out">
Local PRG can be anything you like - method is agnostic
</p>
<p class="fragment fade-in-then-semi-out">
Consider all loci independently - let go of structure/ordering
</p>
<p class="fragment fade-in">
<em>Note: locus == local PRG</em>
</p>

---

### Constructing local PRGs

**Recursive Cluster Collapse** (RCC) algorithm takes an MSA and produces a local PRG
(which is secretly just a DAG)

<img src="images/build-prg.png"  height="300" style="border: none;">

---

### Constructing local PRGs

<video data-autoplay loop src="videos/rcc.webm">
</video>

Implemented in <https://github.com/iqbal-lab-org/make_prg>

---

## Indexing

$(w,k)$-minimizers on a DAG

<br>

<img src="images/kmer-graph.png" height="170" style="border: none;">

---

<img src="images/relax.gif" style="border: none;" height="550">

---

{{% /section %}}
