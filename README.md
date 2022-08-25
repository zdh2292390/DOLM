# DOLM: Domain-oriented Language Modeling with Adaptive Hybrid Masking and Optimal Transport Alignment

The Pytorch implementation for KDD'21 paper: Domain-oriented Language Modeling with Adaptive Hybrid Masking and Optimal Transport Alignment.

## Requirements
```
pip install -r requirements.txt
```
- python 3.8.5
- scipy 1.6.2
- tqdm 4.62.3
- torch 1.7.1
- numpy 1.19.2
- cuda 10.2 

You also need java-jdk in order to run the ASC task below.
```
conda install -c cyclus java-jdk
```
I would recommend using conda to manage all the python packages.

## Fine-tuning (Supervised training & tesing on downstream tasks)
Our model supports 4 downstream tasks on e-commerce text analysis: 
1. Review Aspect Extraction (AE)
2. Review-based Question Answering (RQA)
3. Review Aspect Sentiment Classification (ASC)
4. Product Title Categorization (PTC)


To run fine-tuning experiments on all of the four tasks, you must first run the following jupyter notebook to train the model on each task:
```
fine-tune/script/run_training.ipynb
```

Equivalently, you can also use the following shell scripts to train each task respectively:
```
sh fine-tune/script/run_ae.sh ae bert ae 5
sh fine-tune/script/run_asc.sh asc bert asc 5
sh fine-tune/script/run_pc.sh pc bert pc 5
sh fine-tune/script/run_rqa.sh rqa bert rqa 5
```
(The shell script needs 4 parameters to be specified: $p1=task name, $p2=model name, $p3=result directory, $p4=run times)


Then you can use the following jupyter notebook to run evaluations and calculate performance metrics:
```
fine-tune/run_eval.ipynb
```

If you want to write customized code based on the fine-tune model of each downstream task (ae, asc, pc, rqa), you can read and modify the fine-tune code of each task below (might also need to read related dependency code):
```
fine-tune/src/run_ae.py 
fine-tune/src/run_asc.py 
fine-tune/src/run_pc.py 
fine-tune/src/run_rqa.py 
```

## Pre-training (Self-supervised training on large-scale e-commerce text)
We have included the pre-trained model using our approach in the directory. 
```
fine-tune/pretrained_model/pytorch_model.bin
```
The fine-tuning code is set to use it directly as the foundation model.




