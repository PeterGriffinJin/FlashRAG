# Building Wiki Corpus

You can create your own wiki corpus by following these steps.

## Step0: Install necessary tools

First, install the required tools:
```bash
pip install wikiextractor==0.1
python -m spacy download en_core_web_lg
```

If you encounter issues downloading en_core_web_lg, you can manually download it:
```bash
wget https://github.com/explosion/spacy-models/releases/download/en_core_web_lg-3.7.1/en_core_web_lg-3.7.1-py3-none-any.whl
pip install en_core_web_lg-3.7.1-py3-none-any.whl
```


## Step1: Download Wiki dump

Download the Wikipedia dump you require in XML format. For instance: 

```bash
wget https://archive.org/download/enwiki-20181220/enwiki-20181220-pages-articles.xml.bz2
```

You can access other dumps from this website[](https://archive.org/search?query=Wikimedia+database+dump&sort=-downloads).


## Step2: Run process script

Execute the provided script to process the wiki dump into JSONL format. Adjust the corpus partitioning parameters as needed:

```bash
python preprocess_wiki.py --dump_path ../enwikinews-20240420-pages-articles.xml.bz2  \
                        --save_path ../test_sample.jsonl \
```