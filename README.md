# SeizureSense, a neural network capable of predicting epileptic seizures using EEG data
### Repository made with @Uddhavp22
#### Main code is in SeizureSense.ipynb
## Our process
- **Dataset:** This model is being trained on open data from the free to use [CHB-MIT Scalp EEG Dataset](https://physionet.org/content/chbmit/1.0.0/chb01/#files-panel), which took 23 EEG recordings from 22 patients.
- **Preprocessing:** We filtered out 60 hertz from all of the data and amplified the gamma frequency bands (frequencies greater than 30 hz) as these frequencies are more likely to be seen during and before a seizure. We then split the data and loaded in one-second segments to reduce memory load.
- **Model:** Our model is a Convolutional neural network (CNN) based on the [EEGNET architecture](https://arxiv.org/abs/1611.08024) with the third layer changed to a smaller kernel size to iterate over all channels. The CNN is meant to capture spatial information from the data, and our next step is to create a model that can better capture the temporal aspects, such as a long short term memory (LSTM) or a transformer.
- **Training:** Our model was trained using the adam optimizer with the cross entropy loss function. All training was done on an NVIDIA 3070ti GPU.
- **Accuracy:** Our current best accuracy is *96.97%,* without testing yet for overfitting
