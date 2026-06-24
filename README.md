# Audio-Adversarial-Attacks
Differentiable psychoacoustic adversarial attacks on Wav2Vec2 ASR. Compares standard vs perceptually-aware noise injection for speech recognition evasion.

# Psychoacoustic Adversarial Attacks on Wav2Vec2 Speech Recognition
 
A Masters research project investigating audio adversarial attacks on automatic speech recognition (ASR) systems. This repository contains code comparing two Carlini-Wagner attack methods:
 
1. Standard C&W attack — minimises noise while fooling the ASR model
2. Psychoacoustic C&W attack — integrates human hearing perception constraints directly into the optimisation loss (differentiable penalty)
**Key Results:**
- Both attacks achieve 100% success rate on Wav2Vec2
- Psychoacoustic attack produces +2.40 dB SNR improvement and 23.42% smaller perturbations
- Difference is highly statistically significant (p<0.0001, Cohen's d=1.69)
- The differentiable perceptual constraint outperforms post-hoc projection by efficiently guiding the optimiser away from audible frequencies from step 1
**Innovation:** The psychoacoustic constraint is implemented as a differentiable in-loop spectral penalty (not post-hoc clipping), allowing gradients to encode perceptual information throughout optimisation.
 
Tested on 50 LibriSpeech test-clean clips, targeting the fixed phrase "OPEN THE FRONT DOOR". Includes full Jupyter notebook, statistical analysis (paired t-test, effect sizes), spectral visualisations, and reproducible code (CUDA 11.8, PyTorch 2.0).
