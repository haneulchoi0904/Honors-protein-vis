# Honors-protein-vis

Molecular dynamics (MD) simulations record how a protein moves over time. This project turns each moment of a simulation into a **contact network** (which residues touch each other) and looks for visual representations that show **how proteins change state over time, and which part of the protein changes**. It builds on the *Reducing Snapshots to Points* approach (van den Elzen et al., IEEE TVCG 2016) and moves towards transition networks of protein states.

## Notebooks

The notebooks are snapshots of the work over time; the latest one contains everything.

| Notebook | Contents |
|---|---|
| `exploration.ipynb` | First steps: dimensionality reduction on coordinates, building a contact graph, a first dynamic network |
| `exploration 5 oct.ipynb` | RMSD, PCA/t-SNE on coordinates, contact maps, Snapshots-to-Points on contact networks |
| `exploration 19 oct.ipynb` | Adds the options from the Snapshots-to-Points paper: window width and overlap, normalization, time vs. PC1, colouring by derived attributes, representative states |
| `exploration 6th nov.ipynb` | Centrality vectors as snapshot vectors, the mdCATH dataset at several temperatures, multi-domain proteins (whole protein vs. domains) |
| **`exploration 18th nov.ipynb`** | **Latest.** Everything above, plus feedback checks (t-SNE, repetitions, mdCATH projection), transition networks with per-domain attribution, replicas, event alignment, a geometric check, and a first swimlane prototype |

## Data

The simulation data is not included in this repository.

- **ATLAS** (https://www.dsimb.inserm.fr/ATLAS): download the full archive of a protein (for example `1a62_A`, `16pk_A`, `1k5n_A`) and unzip it next to the notebooks, so that you get a folder like `1k5n_A_protein/` containing `1k5n_A.pdb` and `1k5n_A_prod_R1_fit.xtc` (plus R2 and R3).
- **mdCATH** (Hugging Face, `compsciencelab/mdCATH`): the 6th and 18th Nov notebooks download one domain file (`mdcath_dataset_<domain>.h5`) automatically.

## Setup

Python 3 with pip:

```bash
pip install numpy pandas scipy scikit-learn matplotlib mdtraj igraph h5py huggingface_hub
```

Then open a notebook in Jupyter and run it from top to bottom. Some steps (centralities for every frame, extra replicas) take several minutes.
