# Sagri-nested-ner
Domain Adaptation in Nested Named Entity
Recognition From Scentific Artilces in Agriculture [SoICT2023]

# Baseline
This repo is based on [Triaffine-nested-ner](https://github.com/GanjinZero/Triaffine-nested-ner)

# Environment
All codes are tested under Python 3.7, PyTorch 1.7.0 and Transformers 4.6.1.
Need to install opt_einsum for einsum calculations.
At least 16GB GPU are needed for training.

Make sure you have installed all required packages by running 

```shell
  apt-get install build-essential -y
  pip install -r requirements.txt
```

# Dataset
We only put 100 samples for train/dev/test.
Please put datas under data/dataset_name, you can also refer word_embed.generate_vocab_embed for data paths.

# Extract word embedding
Please download [cc.en.300.bin](https://dl.fbaipublicfiles.com/fasttext/vectors-crawl/cc.en.300.bin.gz) and [BioWordVec_PubMed_MIMICIII_d200.bin](https://ftp.ncbi.nlm.nih.gov/pub/lu/Suppl/BioSentVec/BioWordVec_PubMed_MIMICIII_d200.bin) and run *python word_embed.py* to generate required json files. You need to change the path of word embedding.

# Reproduce

sagri
```shell
bash let_train.sh
```

The results will be saved in the folder *runs*. You can use flag --continue_from *path_to_checkpoint* to continue training from a checkpoint for further training strategy exploration.