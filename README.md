- [1. D-NeRF: Neural Radiance Fields for Dynamic Scenes](#1-d-nerf-neural-radiance-fields-for-dynamic-scenes)
  - [1.1. Installation](#11-installation)
  - [1.3. Download Dataset](#13-download-dataset)
  - [1.6. Train](#16-train)
  - [1.2. QuickStart](#12-quickstart)

---
# 1. D-NeRF: Neural Radiance Fields for Dynamic Scenes
[Project](https://www.albertpumarola.com/research/D-NeRF/index.html)

[Paper](https://openaccess.thecvf.com/content/CVPR2021/papers/Pumarola_D-NeRF_Neural_Radiance_Fields_for_Dynamic_Scenes_CVPR_2021_paper.pdf) 

[Code](https://github.com/albertpumarola/D-NeRF)

## 1.1. Installation
```bash
git clone git@github.com:sword4869/D-NeRF.git
cd D-NeRF
conda create -n dnerf python=3.10 -y
conda activate dnerf
pip install -r requirements.txt
```

## 1.3. Download Dataset
[drive](https://drive.google.com/file/d/19Na95wk0uikquivC7uKWVqllmTx-mBHt/view?usp=sharing) or [dropbox](https://www.dropbox.com/s/0bf6fl0ye2vz3vr/data.zip?dl=0). 


```bash
├── data 
│   ├── mutant
│   ├── standup 
│   ├── ...
```
## 1.6. Train
First download the dataset. Then,
```bash
python run_dnerf.py --config configs/mutant.txt
```

## 1.2. QuickStart
You can download the pre-trained models from [drive](https://drive.google.com/file/d/1uHVyApwqugXTFuIRRlE4abTW8_rrVeIK/view?usp=sharing) or [dropbox](https://www.dropbox.com/s/25sveotbx2x7wap/logs.zip?dl=0). 
```bash
├── logs 
│   ├── mutant
│   ├── standup 
│   ├── ...
```

```bash
python run_dnerf.py --config configs/mutant.txt --render_only --render_test
```
This command will run the `mutant` experiment. When finished, results are saved to `./logs/mutant/renderonly_test_799999`. To quantitatively evaluate model run `metrics.ipynb` notebook

> We provide simple jupyter notebooks to explore the model.

| Description      | Jupyter Notebook |
| ----------- | ----------- |
| Synthesize novel views at an arbitrary point in time. | render.ipynb|
| Reconstruct mesh at an arbitrary point in time. | reconstruct.ipynb|
| Quantitatively evaluate trained model. | metrics.ipynb|