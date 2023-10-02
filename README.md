# Deepwalk implementation of Group 3

# Method

DeepWalk  | [KDD 2014][DeepWalk: Online Learning of Social Representations](http://www.perozzi.net/publications/14_kdd_deepwalk.pdf)



# How to run examples
1. clone the repo and make sure you have installed `tensorflow` or `tensorflow-gpu` on your local machine. 
2. run following commands
```bash
python setup.py install
cd examples
python deepwalk_wiki.py
```

## DeepWalk

```python
G = nx.read_edgelist('../data/wiki/Wiki_edgelist.txt',create_using=nx.DiGraph(),nodetype=None,data=[('weight',int)])# Read graph

model = DeepWalk(G,walk_length=10,num_walks=80,workers=1)#init model
model.train(window_size=5,iter=3)# train model
embeddings = model.get_embeddings()# get embedding vectors
```
