# Pokédex
Pokémon classification as capstone project 1 for ML Zoomcamp 2024

# Get the Environment

```bash
# create environment from environment.yml file
conda env create -f environment.yml

# activate environment
conda activate pokedex
```

Whenever running Jupyter notebooks, make sure you are connected to the pokedex
kernel.

# Data

This is the data set:

```markdown
# roboflow URL
https://universe.roboflow.com/robert-demo-qvail/pokedex/dataset/14
```

For ease of use, the data is tracked in this repository and does not need to be
downloaded. 
If you still want to download it yourself, you can of course do so.
The data was downloaded using the Roboflow API.
It automatically detects if the data is already present on your machine, so if
you don't remove the directory `data/pokedex/`, it won't be downloaded again.

## Quickstart

This is an easy and quick way to download the data.
For more information and alternative ways, please refer to
`scripts/README.md`.

For the download to work, you need to have a Roboflow API key.
If you don't have a Roboflow account, go to https://roboflow.com/, create one,
and follow the instructions to create an API key.

Make the API key available to the data download script `acquire_dataset.py`.
Be careful about your API key!
It is a secret and should not be shared with anyone.
Don't commit and push your API key to a web hosted repository like GitHub.

To make the key available to Python, create a `.env` file in the root of the
repository and add the
`ROBOFLOW_API_KEY` environment variable to it.
To do so, just run the following command when your current working directory is
the root of the repository (`pokedex/`) and make sure to replace
`your_actual_api_key_here` with your actual API key.

```bash
# create the .env file and add the API key to it
echo "ROBOFLOW_API_KEY=your_actual_api_key_here" > .env
```

The `.env` file is automatically ignored by git here, so it won't be committed and
pushed to the repository, and you can safely save the file without worrying about your API key being shared with others.

To start the download, just run this command when your current working directory
is the repo root `pokedex/`:

```bash
python scripts/acquire_dataset.py
```
