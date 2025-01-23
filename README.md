# Project
the source code and datasets for our paper “In-context Clustering-based Entity Resolution with Large Language Models: A Design Space Exploration”

# Requirements
-------
- Python >= 3.8.0
- scikit-learn 1.3.2
- matplotlib, networkx, tqdm, hydra, numpy, pandas 
--------

# Datasets and Pre-train model
----------
We use the following datasets in our experiments:

- [AffiliationString](https://github.com/merialdo/research.alaska)
- [CiteSheer](https://pages.cs.wisc.edu/~anhai/data)
- [Cora](https://www.gabormelli.com/RKB/CORA_Citation_Benchmark_Task)
- [Google-DBLP](https://pages.cs.wisc.edu/~anhai/data)
- [Music](http://oaei.ontologymatching.org/2011/instance/)
- [Sigmod](http://www.inf.uniroma3.it/db/sigmod2020contest/)
- [Song](https://pages.cs.wisc.edu/~anhai/data)

We use the pre-trained models utilized by SBERT:
- [all-MiniLM-L6-v2](https://www.sbert.net/)

---------


# Structure
------------
- requirements.txt: the environment required to run the code.
- use_canopy_block.ipynb: use canopy block to finish ER task.
- use_jaccard_block.ipynb: use jaccard block to finish ER task.
- use_lsh_block.ipynb: use LSH block to finish ER task.

------------
# Usage
------------

## 1. Set Up the Environment：
 ```
 pip install -r requirements.txt
 ```

## 2. Running the Jupyter Notebook:
 ```
 jupyter notebook
 ```


## 3. Running End-to-End ER Code：

This project contains three code files. The only difference among them is the type of blocking algorithm being used. As an example, we will demonstrate how to use the `use_lsh_block.ipynb` file.

### Step 1: Modify API Key

To connect to GPT, you need to configure your proxy and set your `api_key`. Open the notebook and locate the following lines:

```python
import os

os.environ["http_proxy"] = "proxy address"
os.environ["https_proxy"] = "proxy address"

client = OpenAI(
    api_key="your api key"
)
```

Replace `"proxy address"` with your proxy address if needed, and replace `"your api key"` with your actual OpenAI API key.

### Step 2: Update File Paths

Locate the variables for the data path (`file_path`) and the ground truth path (`gt_path`). Update them to point to your dataset and ground truth files. For example:

```python
file_path = './dataset/cora/'
data_file_path = file_path + 'cora.csv'
gt_path = file_path + 'gt.csv'
```

Replace `file_path` with the directory containing your dataset, and ensure `data_file_path` and `gt_path` point to the correct files.

### Step 3: Run the Notebook

Once the necessary modifications are made:

1. Open the Jupyter Notebook file (e.g., `use_lsh_block.ipynb`).
2. Execute the notebook cells sequentially.
3. Wait for the results to be generated.
---------

