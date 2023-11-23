# ProtLoc
Multi-label protein subcellular localization based on GraphSAGE and multi-head attention mechanism.  

**Requirements**
=
torch==1.11.0+cu113  
torch-cluster==1.6.0  
torch-geometric==2.1.0  
torch-scatter==2.0.9  
torch-sparse==0.6.13  
torchvision==0.12.0+cu113  
biopython==1.81  
huggingface-hub==0.17.1  
numpy==1.22.4  
scikit-learn==1.3.0  
sentence-transformers==2.2.2  


$ ./tree-md .
# Project tree

.
 * [tree-md](./tree-md)
 * [dir2](./dir2)
   * [file21.ext](./dir2/file21.ext)
   * [file22.ext](./dir2/file22.ext)
   * [file23.ext](./dir2/file23.ext)
 * [dir1](./dir1)
   * [file11.ext](./dir1/file11.ext)
   * [file12.ext](./dir1/file12.ext)
 * [file_in_root.ext](./file_in_root.ext)
 * [README.md](./README.md)
 * [dir3](./dir3)

**Model Training and Prediction Steps**
=
**1. Gets and processes the protein's pdb file to obtain the carbon atom location information and save it as an npy file. You can run the following script.**  
python get_pdb.py    
**2. Calculate the Euclidean distance between carbon atoms and save it as a csv file. You can run the following script.**  
python adj_matrix.py      
**3. Use the protein language model ESM-2 to code the protein sequence and save it as a csv file. You can run the following script.**    
python esm2.py    
**4. Constructing the dataset. You can run the following script.**  
python dataset.py    
**5. To train the model, you can run the following script.**    
python train.py    
**6. You can also use our trained parameters for prediction directly after implementing steps 1, 2, 3, and 4. You can run the following script.**  
python predict.py    
