# oavss

## Overview
This is the demo and pytorch implementation of our paper: "Online Audio-Visual Speech Separation with Generative Adversarial Training". In this work, we propose the **causal audio-visual speech separation model** and **streaming inference strategy**, which make our model do online audio-visual speech separation. Besides, **generative adversarial training** is adopted in our model to reduce the effects of SI-SNR, which can reduce the word error rate (WER) of separated audio on public automatic speech recognition (ASR) system (e.g., Baidu ASR).

We will release code soon. If you have any question about implementation details, feel free to ask me (zhangpeng2018@ia.ac.cn)

<div align=center><img width="700" src="./image/figure2.png" alt="The structure of our proposed model."/></div>

## Dataset
We conduct experiments on 2-speaker mixtures created from the [Lip Reading Sentences 2](http://www.robots.ox.ac.uk/~vgg/data/lip_reading/lrs2.html) audio-visual dataset, which consists of thousands of spoken sentences from BBC television with their corresponding transcriptions. The training, validation, and test sets are generated according to the broadcast date. The method of generating 2-speaker mixtures as follows: we randomly select two audios from the dataset, then mix them at a random signal-noise-ratio (SNR) between -5 dB and 5 dB. The corresponding two videos are concatenated to simulate a cocktail party scene. Finally, we simulated 40k, 5k, and 3k utterances for training, validation, and test sets, respectively.

# Result
### Audio samples
- Listen to the audio samples at [*./samples*](./samples)
- Spectrogram sample
<div align=center><img width="700" src="./image/spec/figure1.png" alt="The spectrogram sample."/></div>

### Metric
| Models | Online | SDR | PESQ | STOI(%) | WER(%) |
| --------------- | --- | ---- | --- | --| --- |
| Mixed audio | - | 0.15 | 1.78 | 69 | 72.2 |
