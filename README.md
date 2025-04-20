# Prefix-Tuning Reproduction with Sentiment Control 

This project reproduces the method described in the paper  
**"Prefix-Tuning: Optimizing Continuous Prompts for Generation"**  
(Li & Liang, ACL 2021), using the GPT-2 language model and custom sentiment-labeled data.

---

##  What is Prefix-Tuning?

Prefix-Tuning is a parameter-efficient method that conditions a frozen language model using **trainable prefix vectors**, injected as **past key/values** at each transformer layer, without updating the model weights.

---

##  Project Overview

This project includes:

-  A **simplified SentimentPrefixModel**:  
  A baseline version where the prefix is prepended to the embedding layer only (no transformer injection)

- A **FullPrefixTuningModel**:  
   main reproduction that injects prefix vectors into the **past_key_values** of **all GPT-2 transformer layers**

-  New implimentation for **sentiment-controlled generation**:  
  Prefix tokens are learned for `positive` and `negative` sentiment labels

-  A novel **prefix mixing extension**:  
  Generate with an `alpha`-blended mix of positive and negative prefixes for smooth sentiment control



---

##  Evaluation

Evaluated using:

- **BLEU** and **ROUGE (1, 2, L)** scores via `evaluate` 
- **Manual inspection** of generated outputs across sentiment conditions
- **Loss tracking** across training




**Reference:**
@misc{li2021prefixtuning,  
  title={Prefix-Tuning: Optimizing Continuous Prompts for Generation},  
  author={Xiang Lisa Li and Percy Liang},  
  year={2021},  
  eprint={2101.00190},  
  archivePrefix={arXiv},  
  primaryClass={cs.CL}  
}

For more details, visit the [original repository](https://github.com/XiangLi1999/PrefixTuning).
