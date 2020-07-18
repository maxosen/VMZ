# VMZ: Model Zoo for Video Modeling

VMZ is a Caffe2 and Pytorch codebase for video modeling developed by the Computer Vision team at Facebook AI. The aim of this codebase is to help other researchers and industry practitioners:
+ reproduce some of our research results and 
+ leverage our very strong pre-trained models. 


Currently, this codebase supports the following models:
+ R(2+1)D, MCx models [[1]](https://research.fb.com/wp-content/uploads/2018/04/a-closer-look-at-spatiotemporal-convolutions-for-action-recognition.pdf).
+ CSN models [[2]](https://arxiv.org/pdf/1904.02811.pdf) (**note:pytorch implementation is buggy**).
+ R(2+1)D and CSN models pre-trained on large-scale (65 million!) weakly-supervised public Instagram videos (**IG-65M**) [[3]](https://research.fb.com/wp-content/uploads/2019/05/Large-scale-weakly-supervised-pre-training-for-video-action-recognition.pdf).
<<<<<<< HEAD
+ Gradient-Blending for audio-visual modeling [[4]](https://arxiv.org/pdf/1905.12681.pdf) (Caffe2 Only)
=======
+ Gradient-Blending for audio-visual modeling [[4]](https://arxiv.org/pdf/1905.12681.pdf)

## Main Models

We provide our latest video models including R(2+1)D, ir-CSN, ip-CSN (all with 152 layers) which are pre-trained on Sports-1M or **IG-65M**, then fine-tuned on Kinetics-400. Both pre-trained and fine-tuned models are provided in the table below. We hope these models will serve as valuable baselines and feature extractors for the related video modeling tasks such as action detection, video captioning, and video Q&A. More models, e.g. shallower or with shorter clip input are also provided in the [model zoo](tutorials/model_zoo.md). 

### R(2+1)D-152

| Input size | Pretrained dataset | Pretrained model  | Video@1 Kinetics | Video@5 Kinetics | Finetuned model | GFLOPs | params(M) |
| ---------- | --------| ---- | ------- | ------- | -------- | ----- | ------ |
| 32x112x112 | Sports1M | [link](https://www.dropbox.com/s/w5cdqeyqukuaqt7/r2plus1d_152_sports1m_from_scratch_f127111290.pkl?dl=0) | 79.5   | 94.0    | [link](https://www.dropbox.com/s/twvcpe30rxuaf45/r2plus1d_152_ft_kinetics_from_sports1m_f128957437.pkl?dl=0)      | 329.1 | 118.0 |
| 32x112x112 | IG-65M | [link](https://www.dropbox.com/s/oqdg176p7nqc84v/r2plus1d_152_ig65m_from_scratch_f106380637.pkl?dl=0)      | 81.6    | 95.3    | [link](https://www.dropbox.com/s/tmxuae8ubo5gipy/r2plus1d_152_ft_kinetics_from_ig65m_f107107466.pkl?dl=0)      | 329.1 | 118.0 |


### ir-CSN-152
| Input size | Pretrained dataset | Pretrained model  | Video@1 Kinetics | Video@5 Kinetics | Finetuned model | GFLOPS | params(M) |
| ---------- | ------| ------ | ------- | ------- | -------- | ----- | ------ |
| 32x224x224 | Sports1M | [link](https://www.dropbox.com/s/woh99y2hll1mlqv/irCSN_152_Sports1M_from_scratch_f99918785.pkl?dl=0) | 78.2    | 93.0    | [link](https://www.dropbox.com/s/zuoj1aqouh6bo6k/irCSN_152_ft_kinetics_from_Sports1M_f101599884.pkl?dl=0) | 96.7 | 29.6 |
| 32x224x224 | IG-65M | [link](https://www.dropbox.com/s/r0kppq7ox6c57no/irCSN_152_ig65m_from_scratch_f125286141.pkl?dl=0)      | 82.6       | 95.3       | [link](https://www.dropbox.com/s/gmd8r87l3wmkn3h/irCSN_152_ft_kinetics_from_ig65m_f126851907.pkl?dl=0)      | 96.7 | 29.6 |

### ip-CSN-152
| Input size | Pretrained dataset | Pretrained model  | Video@1 Kinetics | Video@5 Kinetics | Finetuned model | GFLOPS | params(M) |
| ---------- | ------ | ------ | ------- | ------- | -------- | ----- | ------ |
| 32x224x224 | Sports1M | [link](https://www.dropbox.com/s/70di7o7qz6gjq6x/ipCSN_152_Sports1M_from_scratch_f111018543.pkl?dl=0) | 78.8    | 93.5    | [link](https://www.dropbox.com/s/ir7cr0hda36knux/ipCSN_152_ft_kinetics_from_Sports1M_f111279053.pkl?dl=0)      | 108.8 | 32.8 |
| 32x224x224 | IG-65M | [link](https://www.dropbox.com/s/1ryvx8k7kzs8od6/ipCSN_152_ig65m_from_scratch_f130601052.pkl?dl=0) | 82.5    | 95.3    | [link](https://www.dropbox.com/s/zpp3p0vn2i7bibl/ipCSN_152_ft_kinetics_from_ig65m_f133090949.pkl?dl=0)   | 108.8 | 32.8 |

### Gradient-Blending on ip-CSN-152
| Input size | Pre-trained dataset | Pre-trained model  | Video@1 Kinetics | Video@5 Kinetics | Finetuned model | GFLOPs |
| -----------| ------------ | -- | ------- | ------- | -------- | ----- |
| 32x224x224 | Sports1M+AudioSet | [link](https://www.dropbox.com/s/u4dgz0z09aaim9x/sports1m_audioset_ip_csn_152.pkl?dl=0) | 80.4    | 94.8    | [link](https://www.dropbox.com/s/ubcy09t8ghes9m7/g_b_ip_csn_152_sports_audioset_ft_kinetics.pkl?dl=0)      | 110.1 | 
| 32x224x224 | IG-65M+AudioSet | [link](https://www.dropbox.com/s/bgxf62o9yzx7zfy/ig_audioset_ip_csn_152.pkl) | 83.3    | 96.0    | [link](https://www.dropbox.com/s/9ja3rlmr568qemt/g_b_ip_csn_152_ig_audioset_ft_kinetics.pkl?dl=0)      | 110.1 |
>>>>>>> 155d9ee92994d8889379578554b4968045e48ac6

## References
1. D. Tran, H. Wang, L. Torresani, J. Ray, Y. LeCun and M. Paluri. **A Closer Look at Spatiotemporal Convolutions for Action Recognition.** CVPR 2018.
2. D. Tran, H. Wang, L. Torresani and M. Feiszli. **Video Classification with Channel-Separated Convolutional Networks.** ICCV 2019.
3. D. Ghadiyaram, M. Feiszli, D. Tran, X. Yan, H. Wang and D. Mahajan, **Large-scale weakly-supervised pre-training for video action recognition.** CVPR 2019.
4. W. Wang, D. Tran, M. Feiszli, **What Makes Training Multi-Modal Classification Networks Hard?** CVPR 2020.


## Suporting Team
This codebase is actively supported by Facebook AI computer vision: @CHJoanna, @weiyaowang, @hengcv, @deeptigp, @dutran, and community researchers @bjuncek (Quansight, Oxford VGG).


