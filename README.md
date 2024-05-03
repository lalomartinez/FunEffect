FunEffect
=========

# FunEffect: Fungal Effector Prediction Pipeline

Fungal Effector Prediction Pipeline is a Python based pipeline that automates the prediction of putative fungal effectors from a given input FASTA file using a series of bioinformatics tools and algorithms.

## Description

This pipeline utilizes SignalP, WoLF-PSORT, TMHMM, PredGPI, and EffectorP to predict putative fungal effectors from a protein FASTA file. It performs the following steps:

1. Predicts signal peptides using SignalP.
2. Filters signal peptide-positive sequences using WoLF-PSORT.
3. Predicts transmembrane helices using TMHMM.
4. Predicts GPI-anchored proteins using PredGPI.
5. Integrates predictions to identify putative fungal effectors.
6. Runs EffectorP to refine predictions.

## Installation

1. Clone the repository:

```bash
git clone https://github.com/your_username/effector-prediction-pipeline.git
cd effector-prediction-pipeline
```

## Install dependencies:

Ensure you have the necessary bioinformatics tools (SignalP, WoLF-PSORT, TMHMM, PredGPI, and EffectorP) installed on your system and available in your PATH.
  
1. SignalP 5.0 (https://services.healthtech.dtu.dk/services/SignalP-5.0/)
2. WoLF-PSORT (https://github.com/fmaguire/WoLFPSort)
3. TMHMM 2.0 (https://services.healthtech.dtu.dk/services/TMHMM-2.0/)
4. PredGPI (https://github.com/BolognaBiocomp/predgpi)
5. EffectorP 3.0  (https://github.com/JanaSperschneider/EffectorP-3.0)
6. faSomeRecords (https://hgdownload.cse.ucsc.edu/admin/exe/linux.x86_64/faSomeRecords)

## Add installation directory of installation of EffectorP 3.0, predGPI and TMHMM 2.0 

```
effectorP_directory= "/path/of/installation/EffectorP-3.0" 
predgpi_directory= "/path/of/installation/predgpi"
TMHMM2_directory= "/path/of/installation/tmhmm-2.0c"
```
## Change TMHMM2.0.options file
   Change original options file by the following 
```
# You can add/remove options to decodeanhmm.
# Options also work on the command line with a `-' in front.
#	Command line options overrule those in this file.
# To see options, try `decodeanhmm -h'.
#            - some options might not work (fossils in the code)
# You can turn a switch by putting `no' in front, e.g. `-noPrintSeq'

modelfile TMHMM2.0.model

# You can try to comment/uncomment these to get more or less
# of the output lines preceeded by '%'

PrintNumbers
#PrintScore
#PrintStat

#Print sequence
#PrintSeq

# One-best decoding
N 1



# Background distribution used for calculation of background score.
#
#  Overall background distribution:
# A:0.081 C:0.015 D:0.054 E:0.061 F:0.040
# G:0.068 H:0.022 I:0.057 K:0.056 L:0.093
# M:0.025 N:0.045 P:0.049 Q:0.039 R:0.057
# S:0.068 T:0.058 V:0.067 W:0.013 Y:0.032
#
# Background distribution has to be given in order of the protein
# alphabet in the model, wich is alphabetical
#
background 0.081 0.015 0.054 0.061 0.040 0.068 0.022 0.057 0.056 0.093 0.025 0.045 0.049 0.039 0.057 0.068 0.058 0.067 0.013 0.032
```

## Usage

Run the script with the following command:
```bash
python FunEffect.py -i input.fasta -o output_dir
```

Command-line Arguments

    -i, --input: Path to the input FASTA file.
    -o, --output: Path to the output directory where results will be saved.


## Reporting bugs
For any inquiries or issues, please open an issue on the GitHub repository.
Please report bugs to the [Github issues
page](https://github.com/lalomartinez/FunEffect/issues)

## License
MIT License

## Contact
[Dr. J. Eduardo Martinez-Hernandez](eduardo.martinez@cgna.cl)

