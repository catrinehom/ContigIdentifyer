# ContigExtractor

ContigExtractor is a pipeline to find read ID's from contigs from Nanopore MinION sequencing matching input references. 

## Requirements

- [KMA](https://bitbucket.org/genomicepidemiology/kma/src/master/) 
- [Unicycler](https://github.com/rrwick/Unicycler/) 
- [BLAST+](https://www.ncbi.nlm.nih.gov/books/NBK279671/) 

## Installation

The following instructions will install the latest version of ContigExtractor:

```
git clone https://github.com/catrinehom/ContigExtractor.git

cd ContigExtractor/

chmod a+x ContigExtractor.sh
chmod a+x ChooseContigs.py
chmod a+x IDFinder.py
chmod a+x ErrorHandling.py
```

### Move to bin 
You might want to move the program to your bin to make the program globally excecutable. 
The placement of your bin depends on your system configuration, but common paths is:

```
/usr/local/bin/
```
OR
```
~/bin/
```

Example of move to bin:

```
mv ContigExtractor.sh /usr/local/bin/
mv ChooseContigs.py /usr/local/bin/
mv IDFinder.py /usr/local/bin/
mv ErrorHandling.py /usr/local/bin/
```

## Usage

To run full pipeline:

```
./ContigExtractor.sh [-i <fastq filename>] [-r <references filename>] [-o <output filename>]
```

If you already ran Unicycler you can input the assembly files:
```
./ContigExtractor.sh [-i <fastq filename>] [-r <references filename>] [-o <output filename>] [-g <Unicycler assembly.gfa>] [-f <Unicycler assembly.fasta>]
```

### Optional flags
```
-t threads for Unicycler, default=8
-c circular contigs output only, default='True'
-l length (maximum) of contigs, default=500000
```

## Pipeline overview

![alt text](https://github.com/catrinehom/ContigIdentifyer/blob/master/SSI_pipeline_overview.png)
