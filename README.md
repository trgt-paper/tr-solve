# TR-solve

TR-solve is a tool for determining the structure of repeat alleles. It works by
first finding putative motifs and then labeling the runs of these motifs within
the given allele sequence. The last step is accoplished using a Hidden Markov
Model (HMM).

## Availability

TR-solve binaries are [available here](https://github.com/trgt-paper/tr-solve/releases).

## Usage example

The tool accepts reads sequences from the standard input and then outputs a list
of motifs and their spans. For example let's apply TR-solve to CAGCAGCAGCATCATCATCAT
like so:

```bash
$ echo "CAGCAGCAGCATCATCATCAT" | ./tr-solve 
  CAGCAGCAGCATCATCATCAT   CAG(0-9),CAT(9-21)
```

The output consists of the original sequence and the motif list CAG(0-9),CAT(9-21).
It tells us that TR-solve found runs of two motifs, CAG and CAT. The run of CAGs
spans the first nine bases of the query sequence and the run of CATs spans the rest.
