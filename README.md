# equivariant-st-transformer

Equivariant (planar SE(3)) Transformer experiments for Spatial Transcriptomics (Visium), with symmetry breaking analysis on Liver Regeneration ST. We embed 2D coordinates as $(x, y, 0)$ and evaluate rotation sensitivity and hexatic order (ψ6) using learned embeddings.

[![Demo Video](./assets/thumbnail.jpg)](https://www.youtube.com/watch?v=eHXcQGTBgtE)

## Installation

```
conda create -n se3_visium python=3.8 -y
conda activate se3_visium

pip install --index-url https://download.pytorch.org/whl/cu121 \ torch==2.3.1 torchvision==0.18.1 torchaudio==2.3.1

## CPU Version
#pip install dgl==2.3.0 -f https://data.dgl.ai/wheels/torch-2.3/repo.html --no-deps 
## CUDA Version
pip install "dgl==2.3.0+cu121" -f https://data.dgl.ai/wheels/torch-2.3/cu121/repo.html --no-deps

pip install anndata scanpy pandas numpy scipy scikit-learn tqdm matplotlib
pip install psutil torchdata
pip3 install PyYAML
pip install pydantic
git clone https://github.com/FabianFuchsML/se3-transformer-public.git
cd se3-transformer-public
#cd _shinn/Python_readable/se3-transformer-public
python -m pip install -e .

# Error Check
python -c "import torch; print('torch', torch.__version__)"
python -c "import dgl; print('dgl', dgl.__version__)"
python -c "import equivariant_attention; print('equivariant_attention ok')"
python -c "from equivariant_attention.modules import GSE3Res, get_basis_and_r; print('se3 ok')"

pip3 install igraph leidenalg
pip install jupyter jupyterlab
pip install ipykernel
python -m ipykernel install --user --name se3_visium --display-name se3_visium

pip install lie-learn
```

## How to Use

Please refer to `data/DATASET_NOTE.md` for data and `tutorial/st_liver_regeneration.ipynb` for runnable code. This notebook contains: 

* Data loading (Visium / Liver Regeneration)
* Planar coordinate embedding: $(x, y, 0)$
* Model inference / embedding extraction
* Symmetry breaking metrics: rotation sensitivity, hexatic order (ψ6)
* Example plots / summaries

## Video lecture

A walkthrough of the motivation, method (planar SE(3) with $(x, y, 0)$), and symmetry-breaking metrics (rot_sens, ψ6):

- 🎥 [YouTube Link](https://www.youtube.com/watch?v=eHXcQGTBgtE)
