A Keras implementation of neural attention model for speech command recognition
This repository presents a recurrent attention model designed to identify keywords in short segments of audio. It has been tested using the Google Speech Command Datasets (v1 and v2). For a complete description of the architecture, please refer to the paper https://arxiv.org/pdf/1808.08929.pdf.

The main contributions of the papers are:

A small footprint model (201K trainable parameters) that outperforms convolutional architectures for speech command recognition (AKA keyword spotting);
A SpeechGenerator.py script that enables loading WAV files saved in .npy format from disk (like a Keras image generator, but for audio files);
Attention outputs that make the model explainable (i.e., it is possible to identify what part of the audio was important to reach a conclusion).
Attention Model
One usual problem with deep learning models is that they are usually "black-box" in the sense that it is very difficult to explain why the model reaches a certain decision. Attention is a powerful tool to make deep neural network models explainable: the picture below demonstrates that the transition from phoneme /a/ to phoneme /i/ is the most relevant part of the audio that the model used to decide (correctly) that the word is "right". Please refer to our paper for confusion matrix and more attention plots.

Attention for word Right

How to use this code
The Demo notebook is preconfigured with a set of tasks: ['12cmd', 'leftright', '35word', '20cmd']. Each of these refer to how many commands should be recognized by the model. When loading the Google Speech Dataset, the user should also select which version to download and use by adjusting the following line:

gscInfo, nCategs = SpeechDownloader.PrepareGoogleSpeechCmd(version=1, task = '35word')

If you want a pretrained model, model-attRNN.h5 contains pre-trained weights for task 35word, version=2.


Reference <\br>
A neural attention model for speech command recognition
Douglas Coimbra de Andradea, Sabato Leob, Martin Loesener Da Silva Vianac, Christoph Bernkopfc
Laboratory of Voice, Speech and Singing, Federal University of the State of Rio de Janeiro
bAdecco Italia S.P.A - GSK Vaccines Srl cCERN
