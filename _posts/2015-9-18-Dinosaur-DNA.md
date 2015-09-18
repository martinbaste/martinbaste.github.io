---
layout: post
title: Guessing a dinosaur's DNA
---

We had a lecture about phylogenetics today, and somehow we ended up talking about dinosaurs.
Apparently the decay rate of the DNA makes it almost impossible for us to get a dinosaur's DNA from it's fossil. This is because by the time we try to recover the genetic material, it will most probably be non-existant. 

But it looks like proteins decay slower, so we can get the proteins sequenced and get a little insight on the molecular appearance of the dinosaurs.

And it got me thinking. We can guess the DNA sequence for an amino acid sequence. We'll get a very large amount of valid DNA sequences. 
But what if we have multiple closely-related proteins? Can we make a better guess?

I'm pretty sure someone already thought about this and got a much better answer, but anyway:

---

### One sequence

Let's assume that we have a 50% GC content (i.e., each base can appear with the same probability, 1/4) and no codon bias (all codons appear with the same frequency).

1. Say we have a single amino acid, in this case *Met*.
   This one is easy, *met* is only encoded by this codon: **ATG**. 
   We know the 3 positions in the DNA sequence with 100% confidence.

2. We could also have the amino acid *Gln*.
   This one is encoded by the codons **CAA** and **CAG**. 
   This way the first two bases will be with 100% confidence **C** and **A**, but the third one can be, with 50% probability, **A** or **G**.

3. And a more complex example: *Leu*.
   There are 6 codons encoding *Leu*: **TTA**, **TTG**, **CTT**, **CTC**, **CTA**, **CTG**. 
   The second nucleotide is **T**. We are assuming that each codon has the same probability of being used, in this case: 1/6. 
   Now, the probability of using a **T** on the first position would be: 1 \* 1/6 + 1 \* 1/6 + 0 \* 1/6 + 0 \* 1/6 + 0 \* 1/6 + 0 \* 1/6 = 1/3. 
   Following the same logic, the probability of  having a **C** is 1/6 + 1/6 + 1/6 + 1/6 = 2/3.
   Now for the third nucleotide: 
   **A** has 2/6, **T** has 1/6, **G** has 2/6 and **C** has 1/6. This is, of course, not knowing what nucleotide the first one is.

---

### Multiple sequences

If we had two closely related sequences, and they differ on a single position, we can get some information about the sequence. 

1. A simple example would be having a *His* and a *Gln* in the same position in two related proteins:
   The codons for *His* are **CAT** and **CAC**, for *Gln* would be **CAA** and **CAG**.
   
   In this case the first and second nucleotides would be surely **CA**. 
   Assuming both sequences are "valid" forms of the protein, the third nucleotide could be any of the four, with the same probability.

2. What would happen if the amino acids were *Phe* and *Leu*?
   This are the codons coding for them:
|Phe   | TTT |
|      | TTC |
|-----:|----:|
|Leu   | TTA |
|      | TTG |
|-----:|----:|
