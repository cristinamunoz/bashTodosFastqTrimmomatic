# bashTodosFastqTrimmomatic


# Línea de bash para crear un .sh que lea linea por linea y corra todos los fastq por trimmomatic. Va para single end y pair end.


ls | cut -d_ -f1-2 | while read line ; do echo java -jar /media/storage01_900gb/APPS/Bioinformatics/Trimmomatic-0.36/trimmomatic-0.36.jar PE -threads 10 ${line}__raw_reads.read_1.fastq.gz ${line}__raw_reads.read_2.fastq.gz ${line}_1paired.fastq.gz ${line}_1unpaired.fastq.gz ${line}_2paired.fastq.gz ${line}_2unpaired.fastq.gz ILLUMINACLIP:/media/storage01_900gb/APPS/Bioinformatics/Trimmomatic-0.36/adapters/TruSeq3-PE.fa:2:30:10 LEADING:3 TRAILING:3 SLIDINGWINDOW:4:15 MINLEN:36 AVGQUAL:25 ; done > correrTrimomatic.sh
