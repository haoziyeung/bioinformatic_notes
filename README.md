# call low freq mutations by varscan
* samtools mpileup -f /gpfs/users/yanghao/database/ref/b37/human_g1k_v37_decoy.fasta -l NF.bed --ff UNMAP,SECONDARY,QCFAIL,DUP -d 100000 -L 100000 BM01180317004.bam| java -jar /gpfs/users/yanghao/software/VarScan.v2.3.9.jar mpileup2cns --min-reads2 1 --min-coverage 1 --strand-filter 1 --output-vcf 1 --variants 1 --min-var-freq 0.0001 --p-value 1 --min-avg-qual 20 > BM01180317004.NF.mosaic.vcf

# convert vcf(bgzip/tabix indexed) to tsv(txt)
* python /gpfs/users/yanghao/software/vcf2tsv/vcf2tsv.py BM01180317004.NF.mosaic.vcf.gz BM01180317004.NF.mosaic.vcf.txt
