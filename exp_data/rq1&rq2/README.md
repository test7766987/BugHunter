# RQ1 & RQ2 Data

## Overview

The dataset for this study consists of 71 applications with a total of 121 crash bugs. The applications are sourced from two main datasets: 20 applications with 34 bugs from the Themis benchmark, and an additional 51 applications with 87 bugs collected from F-Droid.

## Dataset Details

### 1. Themis Benchmark Dataset

You can download the dataset in [Themis Benchmark GitHub Repository](https://github.com/the-themis-benchmarks/home)

### 2. Additional Collected Dataset

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
