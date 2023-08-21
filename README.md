# Package Python Apps
---


A list of ways python apps can be packaged for distribution

# Pyinstaller

Example command below, check the pyinstaller [documentation](https://pyinstaller.org/en/stable/index.html) for more clarity
```bash
pyinstaller \
        --clean \
        -n Kaushal_TTS \
        --add-data country_locale.csv:country_locale.csv \
        --paths /Users/kaushal/.local/share/virtualenvs/streamlit-edge-tts-pciHd8Fx/lib/python3.11/site-packages \
        --collect-data streamlit \
        --collect-data edge_tts \
        --copy-metadata streamlit \
        --copy-metadata numpy \
        --copy-metadata pandas \
        --copy-metadata edge_tts \
        --copy-metadata importlib_metadata \
        main.py

```


# Using the Virtualenv itself

**Note this is also OS dependent** Hence virtualenv from macos won't work on Windows. create the virtualenv on Windows itself using Pipfile or 
requirements and then follow the below steps

 1. go to the location of the virtual env - in this case it was /Users/kaushal/.local/share/virtualenvs/streamlit-edge-tts-pciHd8Fx/*
 2. Zip this folder using the comman - `zip -r <name_of_project> streamlit-edge-tts-pciHd8Fx/*`
 3. copy the created zip to some other folder
 4. unzip the zip
 5. copy and paste the scripts of the project in this unzipped folder where the folder `bin`, `lib`, `etc`, `pyvene.cfg`(if pipenv) exists.
 6. to run the project type the following command where `bin` folder exists - `bin/python -m streamlit run main.py`(for streamlit app)
 7. Create a `.sh` file for executing step 6 for linux/macos and a `.bat` file for windows
