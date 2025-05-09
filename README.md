# deai-gromacs
GROMACS is a package for high-performance molecular dynamics and output analysis. Molecular dynamics is a computer simulation method for analyzing the physical movements of atoms and molecules.

# Downloading datasets​

Datasets can be found here https://www.rcsb.org, In this example we use RCSB PDB - 1AKI dataset. After downloading, place it in a local folder called “input”

## Uploading the datasets to IPFS​

The simplest way to upload the data to IPFS, you can upload your dataset to IPFS using IPFS CLI:
### ipfs add -r input/

added QmTCCqPzX3qSJHuMeSma9uCqUnriZ5eJX7MnxebxydL89f input/1AKI.pdb
added QmeeEB1YMrG6K8z43VdsdoYmQV46gAPQCHotZs9pwusCm9 input
 113.59 KiB / 113.59 KiB [=================================] 100.00%

 Use this entry QmeeEB1YMrG6K8z43VdsdoYmQV46gAPQCHotZs9pwusCm9, use your output of IPFS add!!

## GROMACS Docker Image

gromacs/gromacs: we use the official gromacs in this test/poc - Docker Image

Test version

lilypad run --target 0x102272dB860Ed4fcaC73eB0E1785441aaAF4a303 github.com/deai-factory/deai-gromacs:main -i InputsCID=QmY6LfPca7yoBXTrtXskvrSYa9bh5tDEE2HDRqCUZvnT1n -i Query="echo 15 | gmx pdb2gmx -f input/1AKI.pdb -o outputs/1AKI_processed.gro -water spc"


--target 0x16f6400D30F1d2ACD63Bb27202725680db93e63c => Running on the 4 Way A100 GPU server

-i InputsCID=QmY6LfPca7yoBXTrtXskvrSYa9bh5tDEE2HDRqCUZvnT1n => Folder location on IPFS

-i Query="echo 15 | gmx pdb2gmx -f input/1AKI.pdb -o outputs/1AKI_processed.gro -water spc" => Running the Gromacs command gmx. 

The InputsCID Folder will be mounted to the GROMACS/GROMACS as input and gmx is reading the file from the input volume. Reading the file 1AKI.pdb. 
