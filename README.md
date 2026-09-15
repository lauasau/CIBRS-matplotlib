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
Next, we will load our data ...

```python
SRC = "/Users/lau/Downloads/CIBRS_Group_A_Public_Crime_Data_20260827(in).csv"
OUT = Path(__file__).parent / "charts"
OUT.mkdir(exist_ok=True)
```

```SRC``` is a string holding the absolute path to the source CSV. Every chart created later reads from this one variable via ```pd.read_csv(SRC)```, so it would be the single place to edit if you want to move or rename the file.

```OUT``` is the output directory for the generated PNGs. ```Path(__file__).parent``` resolves to the folder the script itself lives in (regardless of what directory you run it from), and ```/ "charts"``` appends a ```charts``` subfolder to that path — so charts always land next to the script, not wherever your terminal happens to be ```cd```'d into.

```OUT.mkdir(exist_ok=True)``` creates that charts/ folder if it doesn't exist yet. ```exist_ok=True``` means it won't raise an error on subsequent runs when the folder is already there — so the script is safe to re-run repeatedly.


## :paintbrush: Styling the Color Palette
This is completely optional: I will be using the Catppuccin Mocha theme in order to color my charts. I will be creating a custom color palette dictionary by utilizing the palette's official hex codes.

```python
# --- Catppuccin Mocha palette ---
CTP = {
    "base": "#1e1e2e", "mantle": "#181825", "crust": "#11111b",
    "surface0": "#313244", "surface1": "#45475a", "surface2": "#585b70",
    "text": "#cdd6f4", "subtext0": "#a6adc8", "overlay0": "#6c7086",
    "blue": "#89b4fa", "lavender": "#b4befe", "mauve": "#cba6f7",
    "pink": "#f5c2e7", "red": "#f38ba8", "peach": "#fab387",
    "yellow": "#f9e2af", "green": "#a6e3a1", "teal": "#94e2d5",
    "sky": "#89dceb", "sapphire": "#74c7ec", "maroon": "#eba0ac",
}
```

- Background: ```base``` is the figure background
  ```mantle``` is the axes/plot-area background. It is slightly darker and gives the plot a subtle "panel" feel against the figure.
  ```crust``` is darkest. It is defined but unused here. It is reserved for things like tooltips/borders if it is ever needed. 
- Surfaces: ```surface0```/```surface1```/```surface2``` are mid-tone grays used for UI chrome. For this, I use ```surface1``` for grid lines and ```surface2``` for the axes border/edge, and ```surface0``` for the legend box background.
- Text tones: ```text``` (brightest, main labels/titles), ```subtext0``` (dimmer, used for tick labels so they recede a bit), ```overlay0``` (dimmest, unused currently — reserved for de-emphasized elements).
Accent colors: ```blue```, ```mauve```, ```green```, ```peach```, ```pink```, ```yellow```, ```teal```, ```red```, ```lavender```, ```sapphire```, ```sky```, ```maroon``` are the palette's signature pastel accents used for data, such as bars, lines, and histogram fill.



























