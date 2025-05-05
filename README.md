### OMZ_aggregates

Repository containing the scripts used for the marker gene based metagenome analyses described in Li et al (in preparation).

#### read trawling
The script read_trawler.py uses DIAMOND (https://www.nature.com/articles/s41592-021-01101-x) to search all reads in a metagenome against a database of amino acid sequences of a marker gene. It will then compare the hits against an outgroup database and write a "blast score ratio" file, allowing for selection of only reads that match the marker gene dataset better than any other protein. 
As outgroup database, we used the total protein complement of the genomes in a dereplicated set of GTDB (r207) and GEMOTU genomes.

The read_trawler.py script creates a directory to store output files based on read file and marker gene database file:
{read file name}__{marker db name}__read_search

The read_trawler.py script contains hardcoded values for DIAMOND performance on the server at MPI Bremen (line 82), but these can be easily modified

The script blast_based_read_lookup_new.pl is a helper for the read_trawler.py script that gets the sequences from the read file after the first DIAMOND has run.


#### marker gene databases
The marker gene databases here are based of the genomes in a dereplicated set of GTDB (r207) and GEMOTU. The protein basename corresponds to the genome identifier, and can therefore be directly linked to GTDB-tk assigned genome taxonomy. The marker gene databases provided are built as described for mcrA in Speth and Orphan 2018 (https://peerj.com/articles/5614/)
