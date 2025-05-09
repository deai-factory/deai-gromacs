# deai-gromacs

Demo version

lilypad run --target 0x16f6400D30F1d2ACD63Bb27202725680db93e63c github.com/deai-factory/deai-gromacs:main -i InputsCID=QmY6LfPca7yoBXTrtXskvrSYa9bh5tDEE2HDRqCUZvnT1n -i Query="echo 15 | gmx pdb2gmx -f input/1AKI.pdb -o outputs/1AKI_processed.gro -water spc"


--target 0x16f6400D30F1d2ACD63Bb27202725680db93e63c => Running on the 4 Way A100 GPU server

-i InputsCID=QmY6LfPca7yoBXTrtXskvrSYa9bh5tDEE2HDRqCUZvnT1n => Folder location on IPFS

-i Query="echo 15 | gmx pdb2gmx -f input/1AKI.pdb -o outputs/1AKI_processed.gro -water spc" => Running the Gromacs command gmx. 

The InputsCID Folder will be mounted to the GROMACS/GROMACS as input and gmx is reading the file from the input volume. R%eading the file 1AKI.pdb. 
