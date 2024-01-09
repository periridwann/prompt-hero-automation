
# PromptHero Automation

The provided script automates the process of uploading prompt images to Prompt Hero. It simplifies the task by handling the login process, allowing users to configure parameters through config.json, and providing a command-line interface for specifying the type and path of images to upload.

## Installation

Install dependencies from requirements.txt by running the following command:

```bash
pip install -r requirements.txt
```
Execute the following command in the terminal to install Playwright:

```bash
playwright install
```
## Config & Environment Variables

Configure the required parameters in the config.json file. Example configuration:

.env:

`PROMPT_HERO_SESSION_TOKEN`

config.json:
```bash
{
    "prompt": "my flower.",
    "negative_prompt": "",
    "model_user": "Stable Diffusion",
    "version_used": "XL Base 0.9",
    "prompt_category": "Photography",
    "post_title": "",
    "post_description": ""
}
```



## How to get the session token

- Open your browser and log in to https://prompthero.com/users sign_in.
- Open Developer Tools by pressing F12, then find the _prompthero_session cookie in Application > Storage > Cookies > https://prompthero.com/.
- Set the PROMPT_HERO_SESSION_TOKEN variable in the .env file with the obtained session token.
- ![Alt text](https://github.com/periridwann/prompt-hero-automation/blob/main/Screenshot%202024-01-09%20185508.png)

## How to Use

```bash
python main.py -t <type> -p <path>
```
examples:

- To run the script using the default directory (./data/):
```bash
python main.py
```
- To run the script with a custom directory:
```bash
python main.py -t directory -p path/to/your_image_directory/
```
- Or to run the script with a specific file:
```bash
python main.py -t file -p path/to/your_image_directory/image_file.png
```
Ensure you are in the source directory before running the command. The script by default reads image files from the data/ directory and uses config.json for required parameters. If you want to customize the directory, use the -t and -p options as demonstrated above.
