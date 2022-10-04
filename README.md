# test-ucsc
## Steps to create

```bash
./bedToGenePred in.bed out.genepred
./genePredToBigGenePred out.genepred stdout | sort -k1,1 -k2,2n > out.txt

wget https://genome.ucsc.edu/goldenPath/help/examples/bigGenePred.as
./bedToBigBed -type=bed12+8 -tab -as=bigGenePred.as out.txt http://hgdownload.soe.ucsc.edu/goldenPath/hg38/bigZips/hg38.chrom.sizes out.bb
```

Upload `.bb` file somewhere and use following track line to display in UCSC genome browser

```
browser position chr19:44905790-44909388 
track type=bigGenePred baseColorDefault=genomicCodons name="bigGenePred Example Four" description="Ex4:BigGenePred Made from GTF" visibility=pack bigDataUrl=URL_TO_BB
```
