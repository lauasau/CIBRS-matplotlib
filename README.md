# :memo: Introduction

Welcome! :smile: For this project, I will create a step-by-step tutorial on how I create visualizations with Python's matplotlib library. I love using matplotlib to create visualizations since it is extremely easy to learn and use! The goal for this project is to improve my Python skills, so hopefully this tutorial can help for you too :smiling_face_with_three_hearts:

<img width="640" height="180" alt="image" src="https://github.com/user-attachments/assets/0edb7720-ab9a-4d77-93a3-6989b2bd54c4" />

## :chart_with_upwards_trend: Obtaining the Data
For this project, I will be using CIBRS (California Incident Reporting System) data. Specifically, we will be analyzing San Diego crime data from the years 2021 to 2025. The dataset that I am using can be found [here](https://opendata.sandag.org/stories/s/bsk4-5xvp).

First, we will need to import the following libraries: 

```python
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib.dates as mdates
from pathlib import Path
```

## :file_folder: Loading the Data
```python
Next, we will load our data ...
SRC = "/Users/lau/Downloads/CIBRS_Group_A_Public_Crime_Data_20260827(in).csv"
OUT = Path(__file__).parent / "charts"
OUT.mkdir(exist_ok=True)
```

```SRC``` is a string holding the absolute path to the source CSV. Every chart created later reads from this one variable via ```pd.read_csv(SRC)```, so it would be the single place to edit if you want to move or rename the file.

```OUT``` is the output directory for the generated PNGs. ```Path(__file__).parent``` resolves to the folder the script itself lives in (regardless of what directory you run it from), and ```/ "charts"``` appends a ```charts``` subfolder to that path — so charts always land next to the script, not wherever your terminal happens to be ```cd```'d into.

```OUT.mkdir(exist_ok=True)``` creates that charts/ folder if it doesn't exist yet. ```exist_ok=True``` means it won't raise an error on subsequent runs when the folder is already there — so the script is safe to re-run repeatedly.













