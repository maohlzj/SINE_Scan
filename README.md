SINE_Scan: an efficient tool to discover SINEs in genomic datasets

Prerequisites
The following software tools/modules should be installed in your system:
1. Perl and BioPerl Modules. All modules can be obtained from CPAN (http://search.cpan.org/).
	(1).	Statistics::Basic; (we have put this module into SINE_Scan subdirectory modules. The user does not need to install it)
	(2).	Parallel::ForkManager; (we have put this module into SINE_Scan subdirectory modules. The user does not need to install it)
	(3).	Bio::AlignIO;
	(4).	Bio::Align;
	(5).	Bio::PairwiseStatistics;
	(6).	Bio::SimpleAlign;
	(7).	Getopt::Long;
	(8).	File::Basename;
	(9).	Get::Sdt;
	(10).	Bio::SeqIO;
	(11).	Bio::Seq;
	(12).	Bio::Tools::Run::StandAloneBlast;
	(13).	Bio::SearchIO;

2. Python 2.X

3. SINE-Finder.py: The python script can be downloaded from http://www.plantcell.org/content/suppl/2011/08/29/tpc.111.088682.DC1/Supplemental_Data_Set_1-sine_finder.txt.

Installation and usage of SINE_Scan
Here we walk through the whole installation and running process by showing an example of using SINE_Scan to analyse human chromosome 21. Detailed explanation can be found in the user guide.

1.	Download SINE_Scan v1.1.1 from Github and install it in a directory (Here we did analysis in a directory named /home/maohlzj/SINE_Scan-v1.1.1).
	(1).	Download SINE-Finder from Plant Cell website, rename the downloaded file as SINE-FINDER.py, and put it into /home/maohlzj
	(2).	Install SINE_Scan by typing: 
		a.	cd /home/maohlzj/SINE_Scan-v1.1.1
		b.	perl SINE_Scan_Installer.pl -f /home/maohlzj/ncbi-blast-2.2.31+/bin/makeblastdb -b /home/maohlzj/ncbi-blast-2.2.31+/bin/blastn -c /home/maohlzj/cd-hit/cd-hit-est -e /home/maohlzj/EMBOSS-6.6.0/emboss/stretcher -M /home/maohlzj/muscle -l /home/maohlzj/bedtools2/bin/bedtools -a /home/maohlzj/sine_finder.py

2.	Analysis of human chr21
	(1).	Put human chromosome 21 (file name: chr21.fasta) in /home/maohlzj/SINE_Scan-v1.1.1
	(2).	Run SINE_Scan by typing:
		perl SINE_Scan_process.pl -s 123 -g chr21.fasta -d Chr21 -z Chr21 -o chr21 >Chr21.log
