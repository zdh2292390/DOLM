# DOLM: Domain-oriented Language Modeling with Adaptive Hybrid Masking and Optimal Transport Alignment

The Pytorch implementation for KDD'21 paper: Domain-oriented Language Modeling with Adaptive Hybrid Masking and Optimal Transport Alignment.


## Fine-tuning (Supervised training & tesing on downstream tasks)
Our model supports 4 downstream tasks on e-commerce text analysis: 
1. Review Aspect Extraction (AE)
2. Review-based Question Answering (RQA)
3. Review Aspect Sentiment Classification (ASC)
4. Product Title Categorization (PTC)


To run fine-tuning experiments on all of the four tasks, first run the following training/testing scripts to get results:

```
sh fine-tune/script/run_ae.sh 
sh fine-tune/script/run_asc.sh 
sh fine-tune/script/run_pc.sh 
sh fine-tune/script/run_rqa.sh 
```

Then you can run the following jupyter notebook in to run evaluations and calculate performance metrics:
```
fine-tune/run_eval.ipynb
```

If you want to modify the code of modeling part for each downstream task (ae, asc, pc, rqa), you can find them here:
```
fine-tune/src/run_ae.py 
fine-tune/src/run_asc.py 
fine-tune/src/run_pc.py 
fine-tune/src/run_rqa.py 
```

## Pre-training (Self-supervised training on large-scale e-commerce text)
The hyperparam configs for each experiments are included in the [configs](https://github.com/RutgersDM/DKGR/tree/master/configs) directory. To start a particular experiment, just do
```
sh run.sh configs/${dataset}.sh
```
where the `${dataset}.sh` is the name of the config file. For example, 
```
sh run.sh configs/nell.sh
```


