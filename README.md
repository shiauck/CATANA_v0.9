========================
README for CATANA (v0.9)
========================
Time-stamp: <2018-03-02 10:45:34 Cheng-Kai Shiau>

Introduction
============

In higher eukaryotes, the generation of RNA isoforms,
including alternative splicing events (AS) and alternative
transcript products (AT), from one single gene increases
functional and regulatory diversities. Identification of
these RNA isoforms is essential for genomic studies.
However, no tool can provide comprehensive alternative event
annotation including both AS and AT. Here we develop a tool
named Comprehensive Alternative Transcripts Atlas based oN
Annotation (CATANA) to identify all 10 known AS and AT
events.

Installation
============

Not required!
CATANA is written by Perl without additional packages.
Installation is not required!

Usage of CATANA
===============

::

  perl CATANA.pl [-i] <Input GTF/GFF3 file name> [-o] <Folder name for output, optional>
                 [-l] <Log file name, optional> [-d] <Debug message, optional>

Options
------------

-i/--infile FILENAME
````````````````````

This is the only one required parameter for CATANA. The
gene annotation stored in GTF/GFF3 format will be parsed.
CATANA will automatically recognize which format it is to
prevent manual error.

-o/--outdir DIRNAME
```````````````````

This is optional parameter. The default output directory
for holding all 10 alternative events output is named
'alternative_event_annotation'. CATANA will stop if the
folder exists to prevent any accidental mistake.

-l/--log
````````

This is optional parameter. By default, the log will not
be output. The log file is created when the log file name
is given.

-d/--debug
``````````

This is optional parameter. By default, the debug message
is turned off. Set this parameter to 1 to dump out debug
message.

Examples
========

::
   perl CATANA.pl -i manually_created_alternative_events/simulated_SE.gff3 -l test.txt

This command execute CATANA to process simulated skipped
exon example GFF3 contained under folder named
'manually_created_alternative_events' with default rather
than given output folder name, and then dump processing log
into file named 'test.txt'.

Supplementary tools under CATANA
================================

There are two tools under CATANA folder. One is named
'counting_gene_IDs.sh', and the other one is GFF3 simulator.

counting_gene_IDs.sh
````````````````````

'counting_gene_IDs.sh' is a BASH shell script using 'awk'
to calculate the number of unique gene names under the
given output folder.

GFF3 simulator
``````````````

GFF3 simulator is separated into 10 short R scripts. Each
R script is used to simulate a specific AS or AT event.
We have already generated a set of all 10 AS and AT events
with their graphic gene models shown by IGV. All the R
scripts, simulated GFF files and figures are stored under
folder named 'manually_created_alternative_events'.


