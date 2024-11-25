1. Decrease the value of doc_stride to overlap windows
2. Use a linear scheduler with warmup
3. Accelerate the training by using Automatic mixed precision
4. Pre-processing: the model does not expect the answer starts from the middle of the window now
5. Change the pre-train model to a bigger one (luhua/chinese_pretrain_mrc_macbert_large). Decrease the batch size hyperparameter to avoid running out of memory. Use [gradient accumulation](https://kozodoi.me/python/deep%20learning/pytorch/tutorial/2021/02/19/gradient-accumulation.html) to increase the effective batch size.
6. Post-processing: ignore the answer if the start index is after the end index 