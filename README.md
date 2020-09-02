# Bam Splitter

This python script uses [pysam](https://pysam.readthedocs.io/en/latest/#) to parse BAM files, find reads containing a deletion of interest, and then split the BAM file into two, one containing the reads with the deletion and one without. It can be run from the command line using the following options:

## Input

Command line opitons:

 * -b : BAM file to subset, must be indexed using 'samtools index' beforehand in order for pysam to work properly
 * -d : The range of the deletion of interest in the format of "START-END"
 * -o : location/prefix to give output files

Bam Splitter will return 

## Output

## To-Do:
 * Add in chromosome specification (currently must have BAM file narrowed down to region of interest)
 * Make it work on single bp deletions (currently only works on ranges)
 * Test!!

 Happy to have contributions, suggestions, etc. 
