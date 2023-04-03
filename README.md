# SOLIDER on [Person Search]

[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/beyond-appearance-a-semantic-controllable/person-search-on-cuhk-sysu)](https://paperswithcode.com/sota/person-search-on-cuhk-sysu?p=beyond-appearance-a-semantic-controllable)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/beyond-appearance-a-semantic-controllable/person-search-on-prw)](https://paperswithcode.com/sota/person-search-on-prw?p=beyond-appearance-a-semantic-controllable)

This repo provides details about how to use [SOLIDER](https://github.com/tinyvision/SOLIDER) pretrained representation on person search task.
We modify the code from [SeqNet](https://github.com/serend1p1ty/SeqNet), and you can refer to the original repo for more details.

## Installation and Datasets

Details of installation and dataset preparation can be found in [SeqNet](https://github.com/serend1p1ty/SeqNet).

## Prepare Pre-trained Models 
You can download models from [SOLIDER](https://github.com/tinyvision/SOLIDER), or use [SOLIDER](https://github.com/tinyvision/SOLIDER) to train your own models.
Before training, you should convert the models first.

```bash
python convert_model.py path/to/SOLIDER/log/lup/swin_tiny/checkpoint.pth path/to/SOLIDER/log/lup/swin_tiny/checkpoint_tea.pth
```

## Training

We utilize 1 GPU for training. Please modify the `ckpt` and `OUTPUT_DIR` in the bash file.

```bash
sh run.sh
```

## Performance

| Method | Model | CUHK-SYSU<br>(mAP/R1) | PRW<br>(mAP/R1) |
| ------ | :---: | :---: | :---: |
| SOLIDER | Swin Tiny | 94.91/95.72 | 56.84/86.78 |
| SOLIDER | Swin Small | 95.46/95.79 | 59.84/86.73 |
| SOLIDER | Swin Base | 94.93/95.52 | 59.72/86.83 |

- We use the pretrained models from [SOLIDER](https://github.com/tinyvision/SOLIDER).
- The semantic weight is set to 0.6 in these experiments.

## Citation

If you find this code useful for your research, please cite our paper

```
@inproceedings{chen2023beyond,
  title={Beyond Appearance: a Semantic Controllable Self-Supervised Learning Framework for Human-Centric Visual Tasks},
  author={Weihua Chen and Xianzhe Xu and Jian Jia and Hao Luo and Yaohua Wang and Fan Wang and Rong Jin and Xiuyu Sun},
  booktitle={The IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  year={2023},
}
```
