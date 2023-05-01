# How to run examples

```console
wget https://nlp.stanford.edu/data/glove.840B.300d.zip
unzip glove.840B.300d.zip
mv glove.840B.300d.txt data
```

```console
python3 -m venv venv
. ./venv/bin/activate
pip install -r requirements.txt
```

```console
cd examples
python sif_embedding.py
```

## Memo

オリジナルの`requirements.txt`では`sklearn`とあるが、これは不正確。`scikit-learn`としないとちゃんとinstallされない。
