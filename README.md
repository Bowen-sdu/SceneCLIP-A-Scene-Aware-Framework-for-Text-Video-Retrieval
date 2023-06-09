# SceneCLIP-A-Scene-Aware-Framework-for-Text-Video-Retrieval
The official repository for SceneCLIP.

## Dependencies
Our model was trained and evaluated using the following package dependencies:
* Pytorch 1.8.0
* Python 3.7.12

## Datasets
Our model was trained on MSR-VTT and MSVD datasets. Please download the datasets utilizing following commands .
```
# MSR-VTT
wget https://github.com/ArrowLuo/CLIP4Clip/releases/download/v0.0/msrvtt_data.zip

# MSVD
wget https://github.com/ArrowLuo/CLIP4Clip/releases/download/v0.0/msvd_data.zip
```

## Training
We utilize 1 NVIDIA RTX 3090 24GB GPU for training. You can directly train with following commands:
```
# MSR-VTT-9k
python train.py --exp_name=exp_name --videos_dir=videos_dir --scene_type=average --batch_size=32 --noclip_lr=3e-5 --dataset_name=MSRVTT --msrvtt_train_file=9k

# MSR-VTT-7K
python train.py --exp_name=exp_name --videos_dir=videos_dir --scene_type=average --batch_size=32 --noclip_lr=1e-5 --dataset_name=MSRVTT --msrvtt_train_file=7k

# MSVD
python train.py --exp_name=exp_name --videos_dir=videos_dir --scene_type=average --batch_size=32 --noclip_lr=1e-5 --dataset_name=MSVD
```
## Evaluation
```
# MSR-VTT-9k
python train.py --exp_name=exp_name --videos_dir=videos_dir --scene_type=average --batch_size=32 --load_epoch=-1 --dataset_name=MSRVTT --msrvtt_train_file=9k

# MSR-VTT-7K
python train.py --exp_name=exp_name --videos_dir=videos_dir --scene_type=average --batch_size=32 --load_epoch=-1 --dataset_name=MSRVTT --msrvtt_train_file=7k

# MSVD
python train.py --exp_name=exp_name --videos_dir=videos_dir --scene_type=average --batch_size=32 --load_epoch=-1 --dataset_name=MSVD
```

## Acknowledgement
Codebase from [X-Pool](https://github.com/layer6ai-labs/xpool).
