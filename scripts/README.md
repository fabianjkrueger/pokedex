# Sripts

## `acquire_dataset.py`

The dataset is stored in the `data/pokedex` directory.
You don't need to run this script again and download the dataset again.
If you still want to download it, you can do so by running this script again.

The data set is downloaded from Roboflow using the roboflow python API package.
The roboflow python API package is installed in the `requirements.txt` file.
It checks if the dataset is already downloaded and will not download it again if
it is.

For it to work, you need to have a Roboflow API key.
To create one, go to https://roboflow.com/, create an account if you don't have
one yet, and follow the instructions to create an API key.

Once you have the API key, you have to make it available to this script.
Be careful about your API key!
It is a secret and should not be shared with anyone.
Don't commit and push your API key to a web hosted repository like GitHub.

To make you API key available to this script, you have multiple options:

### Preferred option
Create a `.env` file in the root of the repository and add the
`ROBOFLOW_API_KEY` environment variable to it.

Just run the following command when your current working directory is the root
of the repository ("pokedex/") and make sure to replace
`your_actual_api_key_here` with your actual API key.

```bash
# create the .env file and add the API key to it
echo "ROBOFLOW_API_KEY=your_actual_api_key_here" > .env
```

This is the preferred option because it is the most secure and easiest to
manage.
If you do it like this, you don't have to make any changes to this script.
The .env file is automatically ignored by git here, so it won't be committed and
pushed to the repository, and you can safely save the .env file without worrying
about your API key being shared with others.

Alternatively, you can also:

### Alternative option

Set the `ROBOFLOW_API_KEY` environment variable in the script.
For this, you just need to exchange the following line in the script:

```python
API_KEY = os.getenv("ROBOFLOW_API_KEY")
```

with the following line:

```python
API_KEY = "your_actual_api_key_here"
```

This also works and it's the easiest option.
It's not the most secure and easy to manage option, however, because your API
key will be visible in the script and you have to make sure to not commit and
push the script to a public repository.
This way you either have to remove the API key from the script before committing
and pushing, or you have to make sure to not commit and push the script to a
public repository.

### Finally, you can also

I'd recommend using option 1, but if you have a good reason to use one of the
other options, you can do so.
For instructions, please browse the web or ask a colleague or LLM for help.

- Set the `ROBOFLOW_API_KEY` environment variable in your operating system.

- Set the `ROBOFLOW_API_KEY` environment variable in your IDE.
