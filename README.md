# Xshell
fastqc
fastqc -o data -t 2 pm1151_1.qf.gz -o data pm1151_2.fq.gz
spades
nohup spades.py	-1	data/pm1151_1.fq.gz	-2	data/pm1151_2.fq.gz	-o	spades --careful -t 24 -m 100 &
quast
quast.py -o quast/pm1151 spades/pm1151/contigs.fasta
Abricate
abricate --db resfinder ./spades/pm1151/contigs.fasta > abricat/resfinder_pm1151.txt
abricate-Virulence
abricate --db vfdb ./spades/pm1151/contigs.fasta > abricate-Virulence/vfdb_pm1151.txt
plasmid
abricate -db plasmidfinder ./spades/pm1151/contigs.fasta > abricate-Plasmid/plasmid_pm1151.txt
建立文件 mkdir
rm -rf 删除目录和文件
touch 创建新文件
cat 查看文件内容
head 查看文件前几行
mv 文件名 / /
cp.....
