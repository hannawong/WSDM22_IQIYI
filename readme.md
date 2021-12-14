# WSDM 2022 IQIYI User Retention Score Prediction Solution

## Directory

Organize the data as the following directory tree:
```py
- data
- raw_data
    - app_launch_logs.csv
    - user_interaction_data.csv
    - user_playback_data.csv
    - user_portrait_data.csv
    - video_related_data.csv
    - test-a.csv
- feature.py
- model_tools.py
- model.py
- train.py
```

## How to run this code
Firstly run the following command for data preprocessing
```sh
python feature.py
```

Then run the following command for training & evaluating & generating submission file
```sh
python train.py
```

## Ways to improve 💡

- Use `user_portrait_data.csv` as user-side features. Make sure to encode each categorical data in one-hot manner and discretize each numerical data by equal-depth binning, and then embed all the features with embedding table.

- Combine `user_interaction_data` and `user_playback_data` with `video_related_data` to formulate user sequential behavior, and use model like DIEN+auxillary loss, Transformer, MIMN, or other state-of-the-art methods to model such sequential behavior. 
