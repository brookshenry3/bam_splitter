# Bam Splitter

This python script uses [pysam](https://pysam.readthedocs.io/en/latest/#) to parse BAM files, find reads containing a deletion of interest, and then split the BAM file into two, one containing the reads with the deletion and one without. It can be run from the command line using the following options:

## Input

Command line options:

 * -b : BAM file to subset, must be indexed using 'samtools index' beforehand in order for pysam to work properly
 * -d : The range of the deletion of interest in the format of "START-END" (Can be same value for single bp deletion)
 * -o : location/prefix to give output files

Bam Splitter will return... 

## Output

 * {OUTPUT}_deletion_readids.txt : a txt file containging the list of reads that contain the deltion 
 * {OUTPUT}_deletions.bam : BAM file containing the reads that contain the deletion
 * {OUTPUT}_nodeletions.bam : BAM file containing the reads that do not contain the deletion

## !Caveats!

Currently BAM Splitter has no way to specify chromosome (hoping to add this option soon) so the user must narrow down their intial bam file to the region of interest using:

    samtools view -b input.bam region_of_interest

And subsequently index this as described in the "input" section.

There has been very minimal testing done for this, hoping to add some tiny test bams in soon.

## Example Usage:

    python3 bam_splitter.py -b input.bam -d 124213-12420 -o location/prefix

## To-Do:
 * Add in chromosome specification (currently must have BAM file narrowed down to region of interest)
 * Add testing data

 Happy to have contributions, suggestions, etc. 
