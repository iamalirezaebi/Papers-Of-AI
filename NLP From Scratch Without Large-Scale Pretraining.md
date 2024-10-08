1. Avoid Large-Scale Pretraining:
TLM focuses on using task-specific data combined with a small relevant subset of a general corpus.
Instead of training over a massive dataset, you use your task data to query the general corpus, retrieving only a small relevant portion, which saves computation.
2. Small Subset Retrieval:
Use BM25 or another text retrieval method to get a tiny subset of a larger corpus related to your task. This can reduce the training size from gigabytes to megabytes.
For example, if your task is sentiment analysis, extract relevant documents from a larger corpus using key phrases or data samples from your task.
3. Efficient Training from Scratch:
The method proposed by TLM allows you to train models from scratch on smaller, task-relevant data rather than using a pretrained language model.
Optimize both the task objective (e.g., classification) and language modeling objective using your retrieved data, reducing computational demand.
4. Use Fewer Compute Resources:
This method drastically reduces FLOPs (floating point operations), requiring significantly less hardware power.
According to the paper, this approach can scale down training from needing thousands of GPUs to just a handful of GPUs or even single-GPU training for smaller tasks,
meaning a high-end laptop can handle these tasks.
5. Choose Smaller Models:
Instead of large models like RoBERTa-Large, you can select or build smaller architectures (e.g., BERT-Base or even smaller custom models) and train them efficiently 
using TLM.
6. Focus on High-Impact Tasks:
If your task does not require general-purpose models but focuses on specific tasks (like classification, sentiment analysis, etc.), this method allows you to train 
directly on relevant task-specific data, which can significantly cut down on memory and compute requirements.
