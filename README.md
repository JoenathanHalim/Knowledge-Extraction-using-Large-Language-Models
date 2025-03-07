# Knowledge-Extraction-using-Large-Language-Models

# Abstract
This work aims to extract structural information from text documents using LLMs, guided by a well-defined schema derived from the given process ontology. An interesting challenge lies in determining the optimal trade-off between the size of the LLM (open-source or proprietary) and the cost of fine-tuning due to data collection. Although larger LLMs are generally expected to outperform smaller ones, a key question is whether smaller LLMs, with sufficient fine-tuning, will surpass the performance of their larger counterparts. Another interesting problem is the trade-off between single (extracting all information in a single query) and multiple queries (extracting only a few components in each query) to extract information from documents. 

# Preparing Environment
This repository used base model of quantized [Llama-2-7b-chat-hf](https://huggingface.co/meta-llama/Llama-2-7b-chat-hf). Please note that you would have to request and been granted access from Meta to use the Llama-2 base model.

# Finetuning
```bash
python finetuning.py  \
  --use_peft \
  --peft_method lora \
  --quantization \
  --model_name 'meta-llama/Llama-2-7b-chat-hf' \
  --output_dir './my_lora_weights' \
  --batch_size_training 1 \
  --micro_batch_size 1 \
  --num_epochs 10 \
  --dataset 
```
