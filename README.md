# Smart Cook Dashboard

Smart Cook Dashboard is an interactive data visualization project for exploring breakfast and brunch recipes.

The project combines Python-based data preprocessing with a browser-based D3.js dashboard. It focuses on ingredient relationships, recipe categories, and cooking timelines.

## Features

- Ingredient pairing network showing which ingredients frequently appear together
- Searchable ingredient graph with zoom, pan, and focus interactions
- Ingredient grouping by broad food category
- Recipe category overview
- Searchable recipe list
- Per-recipe cooking timeline
- Active vs. passive cooking-step classification
- Interactive filtering and tooltips

## Data pipeline

The repository includes Python scripts that transform recipe data into the JSON consumed by the visualization.

```text
Raw recipe CSV
      |
      v
Python preprocessing
      |
      v
parsed_data.json
      |
      v
D3.js dashboard
```

`text_parser.py` cleans ingredient names, parses cooking instructions, estimates step durations, labels active and passive steps, normalizes recipe subcategories, and exports the processed data.

The current processed dataset is capped at 300 recipes for the visualization.

## Tech stack

- JavaScript
- D3.js v7
- HTML
- CSS
- Python
- pandas

## Project structure

```text
.
├── index.html
├── text_parser.py
├── preprocess.py
├── breakfast_recipes.csv
├── parsed_data.json
├── reduced_dataset.csv
├── 1_Recipe_csv.csv
└── 2_Recipe_json.json
```

## Run the visualization

Because the dashboard loads `parsed_data.json` in the browser, it should be served through a local HTTP server rather than opened directly as a file.

For example:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Regenerate the processed data

Install pandas if needed:

```bash
pip install pandas
```

Then run:

```bash
python3 text_parser.py
```

This reads `breakfast_recipes.csv` and regenerates `parsed_data.json`.

## Notes

This repository is a data visualization project focused on transforming a recipe dataset into interactive visual representations of ingredient relationships and cooking workflows.
