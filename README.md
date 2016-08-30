# Variant Calling Workflow in Swift #
## Problem statement ##
Want a reasonably flexible variant calling workflow with the following features:
1. Able to run on multiple clusters, so we could support work with different collaborators, such as
  * mForge - OGE - Mayo
  * Blue Waters - Cray aprun + PBS Torque - to enable us to run large scale projects and bring lots of $$$
  * biocluster - Slurm - to serve HPCBio clients
  * standalone servers - ? no scheduler ? - individual H3A labs
2. enable user to specify which software alternatives to use for each step of the workflow, such as
  * BWA-MEM vs novoalign for alignment
  * samtools vs sambamba for SAM/BAM conversion
  * novosort vs Picard vs samblaster for marking of duplicates
  * UnifiedGenotyper vs HaplotypeCaller for variant calling
3. enable user to choose workflow configuration, such as
  * align only or
  * realign only or
  * variant calling only or
  * align + realign + variant calling together or
  * align + realign only or
  * realign + variant calling only
4. enable user to choose the kind of data analysis:
  * input data are multiplexed vs 1 sample/lane
  * analyze samples individually or joint calling (? obsolete ? ); or do GenotypeGVCF in the end

The current Bash-based workflow has all of the above, except for the ability to run on different clusters.
Also, it is difficult to maintain, such that introducing new features is very laborious.
Documentation is equally difficult. Those are the factors that drove us to explore Swift as a replacement for Bash glue.
## Usage ##
TODO: Write usage instructions
