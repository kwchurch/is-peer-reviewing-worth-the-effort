# is-peer-reviewing-worth-the-effort

This GitHub repository describes the data behind our forthcoming paper in Coling-2025: 

```
@article{
title={Is Peer-Reviewing Worth the Effort?},
author={Kenneth Church and
Raman Chandrasekar and John E. Ortega and Ibrahim Said Ahmad},
year={2025},
journal={Coling}
}
```


There are data files like this:

```sh
gunzip <  with_key/2018.summary.gz | head
id	2018	2019	2020	2021	2022	2023	2024	id2	ACL	ArXiv	CorpusId	DBLP	DOI	MAG	PubMedCentral	PubMed
32520422	0	3	0	2	0	3	1	32520422	1	0	1	1	0	0	0	0
52186491	0	4	7	5	3	5	0	52186491	1	1	1	1	1	1	0	0
53082684	0	2	0	0	0	1	0	53082684	1	0	1	1	1	1	0	0
53652545	0	1	0	1	0	0	0	53652545	1	0	1	1	0	1	0	0
53082686	0	18	20	12	5	7	0	53082686	1	0	1	1	1	1	0	0
4858508	1	5	6	4	3	5	0	4858508	1	1	1	1	1	1	0	0
12416669	1	0	4	1	0	0	0	12416669	1	0	1	1	0	1	0	0
21731946	0	4	2	2	2	2	0	21731946	1	0	1	1	0	1	0	0
51878087	0	1	1	0	0	1	0	51878087	1	0	1	1	1	1	0	0
```

and this:


```sh
gunzip < with_key/ACL/ACL.2018.summary2.norm.gz | head
# Anthology2	Anthology	id	2018	2019	2020	2021	2022	2023	2024	id2	ACL	ArXiv	CorpusId	DBLP	DOI	MAG	PubMedCentral	PubMed
# misc	2	32520422	0	3	0	2	0	3	1	32520422	1	0	1	1	0	0	0	0
# EMNLP	D	52186491	0	4	7	5	3	5	0	52186491	1	1	1	1	1	1	0	0
# EMNLP	D	53082684	0	2	0	0	0	1	0	53082684	1	0	1	1	1	1	0	0
# Workshp	W	53652545	0	1	0	1	0	0	0	53652545	1	0	1	1	0	1	0	0
# EMNLP	D	53082686	0	18	20	12	5	7	0	53082686	1	0	1	1	1	1	0	0
# NAACL	N	4858508	1	5	6	4	3	5	0	4858508	1	1	1	1	1	1	0	0
# Workshp	W	12416669	1	0	4	1	0	0	0	12416669	1	0	1	1	0	1	0	0
# LREC	L	21731946	0	4	2	2	2	2	0	21731946	1	0	1	1	0	1	0	0
# Workshp	W	51878087	0	1	1	0	0	1	0	51878087	1	0	1	1	1	1	0	0
```

The file name encodes the publication year (2018 in this case).

The following shows that ther are 1224591 lines in the first file, and 4283
in the second.

```sh 
gunzip <  with_key/2018.summary.gz | wc
gunzip <  with_key/ACL/ACL.2018.summary.gz | wc
```

In both cases, id is a corpus id from semantic scholar.
The larger file lists ids with the appropriate publication year from ACL, arXiv and PubMed.
The last 8 columns are indicator variables (either 0 or 1) indicating the source of the paper.
At least one of ACL, ArXiv and PubMed will be 1.

The smaller file is for papers in the ACL Anthology.  The firsts two columns indicate a venue within the ACL.

The columns with 4-digit numbers are years.  For papers published in 2018, these counts indicate how many citations these papers
had in each year from 2018 to 2024.

