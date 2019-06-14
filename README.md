# BoBro2: An integrated toolkit for accurate prediction and analysis ofcis-regulatory motifs at a genome scale

## Abstract:

**MOTIVATION:**
We present an integrated toolkit, BoBro2.0, for prediction and analysis of cis-regulatory motifs. This toolkit can (i) reliably identify statistically significant cis-regulatory motifs at a genome scale; (ii) accurately scan for all motif instances of a query motif in specified genomic regions using a novel method for P-value estimation; (iii) provide highly reliable comparisons and clustering of identified motifs, which takes into consideration the weak signals from the flanking regions of the motifs; and (iv) analyze co-occurring motifs in the regulatory regions.

**RESULTS:**
We have carried out systematic comparisons between motif predictions using BoBro2.0 and the MEME package. The comparison results on Escherichia coli K12 genome and the human genome show that BoBro2.0 can identify the statistically significant motifs at a genome scale more efficiently, identify motif instances more accurately and get more reliable motif clusters than MEME. In addition, BoBro2.0 provides correlational analyses among the identified motifs to facilitate the inference of joint regulation relationships of transcription factors.

**Citing us:** Ma, Q., Liu, B., Zhou, C., Yin, Y., Li, G., & Xu, Y. (2013). *Bioinformatics*, 29(18), 2261–2268. doi:10.1093/bioinformatics/btt397 

# Usage
## Installation

Enter the folder "BoBro2.0" and type

```
./INSTALL
```

## BBA

BBA can do co-occurrence Analysis for file 'Input' by CMD:

```
perl BBA.pl Input SequenceNum
```

For example 
```
perl BBA.pl Motif_position_for_BBA 10
```


### Inputs 

The input file include TF name and the sequence lables which contain binding sites of this TF(see 'Motif_position_for_BBA' for example).
The format of input file:

    >AcrR
    2251
    1650
    >Ada
    183
    2393
    1341
    241
    >AgaR
    2081
    1299

Here is motif information for 3 TFs: AcrR, Ada, and AgaR. the name should have '>' ahead;
The number 2251 means there is a motif occurence for TF AcrR in 2251st promoter sequences.

### Outputs
The result file will be in file "Input.BBA" and "Input.BBA.all";

The significantly co-occurence TF pairs are collected in "Input.BBA";
Data for all TF pairs are in "Input.BBA.all";

The data in result file have 7 columns with means:
1. TF1
2. TF2
3. Hyper-geometric p-value
4. Total sequences number
5. The number of sequences contain binding sites of TF1
6. The number of sequences contain binding sites of TF2
7. The number of sequences contain binding sites for both TF1 and TF2




## BBS

The major program in the provided package is `BBS`, it can search motifs in a fasta file using known alignment or matrix format of moitfs

1.  Search motif in alignment format:
```
perl BBS.pl motif_alignment promoters 1
```
2.  Search motif in matrix format:
```
perl BBS.pl motif_matrix promoters 2 
```
3.  Search motif in consensus format
```
perl BBS.pl motif_consensus promoters 3
```
4.  Search motif considering background genome:
```
perl BBS.pl motif_consensus promoters 1/2/3 background
```

### Inputs
Matrix:

    >Matrix
    A    5   6   4   5   4   1   0   4   4   3   5   1   2   4   3   3   0   0   3   4   3   3   3   3   3
    C    5   0   2   2   1   2   1   5   1   0   0   1   5   0   0   0   0   7   0   0   0   4   4   1   0
    G    0   1   0   4   6   5   2   1   5   8   6   8   0   5   8   8   2   2   7   7   8   4   4   4   8
    T    1   4   5   0   0   3   8   1   1   0   0   1   4   2   0   0   9   2   1   0   0   0   0   3   0
    >end
    
Alignment:

    >Alignment
    ATCAACTGAAACAAAACGAAAGATT
    GAAAACCATTATCTTTCGTTTTATT
    GACTTTCATTATGTTTCTTTTGTGA
    ACCAAGTGAAATGAAACGAAAGGCA
    AACTTTCAGTTTCTTTTCTATAGAT
    AAATTTCGTTTTATTTCTTTTTTCT
    GCAATCCCTTTTGCTTCCTTTATCT
    GCCTTTCTTTTTCTTTCGTTTTGAT
    CAGGGTCAATTAGCTTCGTTTTGAT
    GCAAAACGAAATGAAACGAAAGTTT
    AAGGTGGGCTTGCATTTGCTTAATA

Consensus:

    >Consensus
    AGGRKTTBCCGA

## BBR



## Contact

Any questions, problems, bugs are welcome and should be dumped to
Qin Ma <Qin.Ma@osumc.edu>
