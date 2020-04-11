# Transfer Learning on DC TTS for Emotional Speech Generation

This repo contains attempts to apply transfer learning to the dc_tts text-to-speech model decribed in the paper [Efficiently Trainable Text-to-Speech System Based on Deep Convolutional Networks with Guided Attention](https://arxiv.org/abs/1710.08969). The code used is a modified version of [Kyubyong's dc_tts code](https://github.com/Kyubyong/dc_tts). The [pretrained model](https://www.dropbox.com/s/1oyipstjxh2n5wo/LJ_logdir.tar?dl=0) was also provided in Kyubong's repo. It was pretrained on the [LJ Speech Dataset](https://keithito.com/LJ-Speech-Dataset/). Scarlett Johansson's voice was trained during transfer learning

---
Transfer Learning is accomplished by selecting the model layers to train in hyperparameters.py

---

Task List:
- [x] add selectable list of layers for transfer learning
- [x] prelim model training
- [ ] add scoring history plots
- [ ] detailed exploration of which layers to train
- [ ] explore data augmentation methods
- [ ] explore post-processing

## Prelim Model Training
- ~6 hrs of training on Tesla V100 GPU
- Layers trained:
  -  SSRN(C_13, C_14, C_15, C_16)
  -  Text2Mel/TextEnc(HC_11, HC_12, HC_13, HC_14, HC_15)
  -  Text2Mel/AudioEnc(HC_9, HC_10, HC_11, HC_12, HC_13)
  -  Text2Mel/AudioDec(HC_7, C_8, C_9, C_10, C_11)


## References:
- [Efficiently Trainable Text-to-Speech System Based on Deep Convolutional Networks with Guided Attention](https://arxiv.org/abs/1710.08969)
- [Kyubyong's dc_tts repo](https://github.com/Kyubyong/dc_tts)
- [Exploring Transfer Learning for Low Resource Emotional TTS](https://www.researchgate.net/publication/330382963_Exploring_Transfer_Learning_for_Low_Resource_Emotional_TTS)

