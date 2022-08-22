# DOLM

The pytorch implementation for paper 'Domain-oriented Language Modeling with Adaptive Hybrid Masking and Optimal Transport Alignment'.



## Pre-training (Self-supervised training on large-scale e-commerce text)
The hyperparam configs for each experiments are included in the [configs](https://github.com/RutgersDM/DKGR/tree/master/configs) directory. To start a particular experiment, just do
```
sh run.sh configs/${dataset}.sh
```
where the `${dataset}.sh` is the name of the config file. For example, 
```
sh run.sh configs/nell.sh
```

## Fine-tuning (Supervised training & tesing on downstream tasks)






