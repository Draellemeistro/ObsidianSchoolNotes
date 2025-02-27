# Tensor Processing Unit
[Googles side om tpu'er](https://cloud.google.com/tpu?hl=en)
[Wikipedia TPU](https://en.wikipedia.org/wiki/Tensor_Processing_Unit)

- AI _accelerator application-specific integrated circuit_ ([[ASIC]]) developed by [[Google Cloud IoT|Google]]
- Built specifically to perform tensor operations very fast
- Used for neural network machine learning, particularly using Google's own [[TensorFlow]] software
- Google began using [[TPU|TPUs]] internally in 2015, and in 2018 made them available for third party use.

## ML training performance and benchmarks **[[TPU]] vs CPU** 
![[image_TPU.png]]

## ML Inference at the [[Edge ML-AI]] with/without [[TPU]]
- Time spent to perform a single inference with several popular models on the Edge TPU
	- For the sake of comparison, all models running on both CPU and Edge [[TPU]] are the  [[TensorFlow]] Lite versions.
- They are all trained using the **ImageNet dataset** with 1.000 classes.
![[image_TPU-1.png]]
