# ML Assignment 4 — End-to-end: raw file to model-ready data

**Dataset:** UFO sightings (NUFORC reports, ~80k rows, 11 columns), TidyTuesday 2019-06-25
- Folder: https://github.com/rfordatascience/tidytuesday/tree/master/data/2019/2019-06-25
- Raw CSV: https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2019/2019-06-25/ufo_sightings.csv

**Task prepared for:** classify the reported `ufo_shape` (21 classes). No model is trained; the notebook stops at `X_train, X_test, y_train, y_test`.

## Files
- `assignment4_endtoend.ipynb` — `load_data()`, `clean(df)`, `add_features(df)`, `build_pipeline()`, one final cell that runs the whole path, assertions, decisions list
- `ufo_cleaned.csv` — cleaned DataFrame (after `clean` + `add_features`, before imputing/encoding/scaling)
- `pipeline.joblib` — fitted imputing + encoding + scaling pipeline (fitted on the training split only). It expects the output of `add_features()` as input.

## Before and after (Q7)
| | Raw file | Cleaned DataFrame | Model-ready matrix (train+test) |
|---|---|---|---|
| rows | 80,332 | 78,312 | 78,312 |
| columns | 11 | 18 | 77 |
| missing values | 17,418 | 9,153 | 0 |
| exact duplicate rows | 0 | 0 | 54 (identical feature vectors) |
| duplicate sightings (date_time + city_area + description) | 9 | 0 | n/a |

Train / test shapes: `X_train` (62,649 × 77), `X_test` (15,663 × 77).
