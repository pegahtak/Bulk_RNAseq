1- upload the fastq files to the server 
2- make a folder by the name of your choice:
mkdir [DIR_NAME]
3- move all the fastq files to that folder 
mv *fastq* [DIR_NAME]/
if your fastq files are with .fq suffix, change that accordingly in the code above.

2- prepare a list of all the file names without their fastq extension. each line should contain one sample for example if the 

alternatively you can use the readily availbe script make_list.sh run it like below
bash make_list.sh
3-
3- run the pre_anlaysis step by the command below: if you are submitting to comouting nodes use qsub 
qsub -cwd -l h="[NAME OF NODE]" -M [Your emial] -m e preanalysis.sh [SAMPLES LIST]

this step may take a while. You will get an email notification when it is done.

4- look into reports and check if the QC and alignemnt are ok. 
Interpretation of QC and multiQC report

5- get the count matrix 
download the organism genome from []
6- open the file getCount.sh and in the line GTF="ADDRESS" replace "ADDRESS" with the absolute path to your gtf file.
7- run the getCount.sh script as described before
qsub -cwd -l h=[NAME OD NODE] -M [Your emial] -m e getCount.sh
when the job is complete there shoud be a file named count.txt in the folder you created. 
You can now use this count matrix for DGEA step explained in the code [CAR-E2]
