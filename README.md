# Kaggle Image Segmentation Project

## About

This project tackles automated segmentation of the stomach, small bowel, and large bowel 
from CT scans to support radiation therapy planning for GI cancer patients. Physicians 
currently outline these organs manually on each scan, a process that can stretch a 
15-minute appointment to nearly an hour — and must be repeated daily across weeks of 
treatment. We built and compared two deep learning architectures to explore whether this 
process could be automated without sacrificing accuracy.

**Dataset:** UW-Madison GI Tract Image Segmentation (Kaggle) — filtered from 30,796 raw 
CT slices down to 13,289 scans with valid organ masks, then preprocessed (RLE mask 
decoding, 320×320 resizing, normalization) for training.

**Models:**
- **U-Net** — implemented from scratch in PyTorch as a convolutional baseline, using 
  BCEWithLogitsLoss and Adam
- **TransUNet** — CNN encoder + transformer bottleneck + CNN decoder, designed to test 
  whether self-attention could better capture long-range spatial relationships between 
  organs, using Dice loss and AdamW
