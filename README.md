# DOLM: Domain-oriented Language Modeling with Adaptive Hybrid Masking and Optimal Transport Alignment

The Pytorch implementation for KDD'21 paper 'Domain-oriented Language Modeling with Adaptive Hybrid Masking and Optimal Transport Alignment'.



### Pre-training (Self-supervised training on large-scale e-commerce text)
The hyperparam configs for each experiments are included in the [configs](https://github.com/RutgersDM/DKGR/tree/master/configs) directory. To start a particular experiment, just do
```
sh run.sh configs/${dataset}.sh
```
where the `${dataset}.sh` is the name of the config file. For example, 
```
sh run.sh configs/nell.sh
```

## Fine-tuning (Supervised training & tesing on downstream tasks)
We support 4 e-commerce downstream tasks: 
1. Review Aspect Extraction (AE)
2. Review-based Question Answering (RQA) 
3. Review Aspect Sentiment Classification (ASC)
4. Product Title Categorization (PTC)






