# Memrise-word-uploader
A bundle of scripts to easily upload words, their definitions, POS and audio to the website called 'Memrise'. 
## Pre-requisites
Get Chrome WebDriver from [here](https://sites.google.com/a/chromium.org/chromedriver/), extract its content, create a folder named `web_drivers` and put the driver file in it.

You need an API key to get word definitions from Merriam-Webster Dictionary API. You can register and get your API key [here](https://www.dictionaryapi.com/). Merriam-Webster Dictionary has several sub-dictionaries. You should get an API key for Merriam-Webster Learners' Dictionary. After getting your key please set the `key` variable in `get_def_and_audio.py`.

Lastly, you need a Memrise account and a course that you can edit its word list. Set `memrise_id` and `memrise_password` variables in `audio_uploader.py`. Also set `course_name` variable to your course's name.
## How to use
There are two basic scripts. One of them is `get_def_and_audio.py` which gets word definitions for listed words in `words.txt` using Merriam-Webster Dictionary API. It can also generate audio files for given words in `words.txt`. Type the words that you want to work with in `words.txt`. Each line should contain one word. If you set `get_definitions` parameter to `True` in `get_def_and_audio.py` then you will be asked to select a definition from a list of definitions for each word. Because a word may have several definitions in the dictionary. Definitions will be written to an output file named `definitions.txt`. Go to *Memrise->Your Course->Edit Page*. Your word list should contain *Word | Definition | Audio | Part of Speech* columns. Select *Bulk add words* from the *Advanced* tab. Copy the content of your `definitions.txt` file. Save and voilà.

After entering words to your course you can run `audio_uploader.py`. It reads words from `words.txt`, audio files from *audio* folder and uploads them.