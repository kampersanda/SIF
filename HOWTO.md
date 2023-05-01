結論：色々修正したけど、エラーが出続ける。もう触らん方がよい。

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

### 正しい依存の指定

オリジナルの`requirements.txt`では`sklearn`とあるが、これは不正確。`scikit-learn`としないとちゃんとinstallされない。

### gloveデータの修正

`sif_embedding.py`で指定されてる`glove.840B.300d.zip`では、52344行目で`. . .`というトークンが含まれており、`.split()`で分割するコードでは、最初の`.`のみがトークンとして扱われて`float()`で落ちる。

6Bならパスするっぽい
