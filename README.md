# BugHunter

Currently, we have organized and open-sourced a portion of the code and data. The complete code and data will be updated shortly.

## Dataset

You can download the dataset in [google drive](https://drive.google.com/file/d/1VGas92RAqguSP_WYRfQllvMHUT7njZyv/view?usp=sharing)

After downloaded, you can unzip the file, and you will get 3 directories: 

```
|─app
├─readme
└─selected_data
```

copy these dir paths into `src/config.ini`:

```
readme_path = [readme path]
selected_app_path = [app path]
selected_data_path = [selected_data path]
```

## Prepare Env

Create your python env:

```
conda create -n bughunter python=3.10 -y
conda activate bughunter
```

Install the requirements packages:

```
pip install requirements.txt
```

## Run

1. Change your path in `src/config.ini`
2. Run `python main.py`

