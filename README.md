# MPAI Audio Analyser: Speed Irregularities Detector

### Usage:

```
    python3 src/main.py "path_to_wav_file" "path_to_binary_model" "path_to_4classes_model"
```

where the path to the model is the path to the **folder** containing the model, for example `models-def/model-binary-separateclasses`

---

The script generates a folder called `output` in the project directory, that contains:

- a log file for each channel describing the irregularities found, with their relative timestamps
- a folder for each channel containing the respective .wav file and spectrogram
- a folder for each channel containing the respective segmented spectrogram

The output folders are only for manual revision, they can be eliminated in the final version of the program

---

### Dataset Extraction

1.  The code used for extracting the spectrogram data from the audio files is in `notebooks/spectral_extraction.ipynb`

    - At the end of the notebook execution you'll have a dataset divided in two subfolders, one labeled 'correct' and the other 'wrong'

    - If you want to download the dataset directly, you can find it at this link: https://drive.google.com/file/d/1Hlm7xSH6ZX_6LUB88vXAZWO3_kfFJxkO/view?usp=drive_link

2.  The code used for dividing the dataset in training-validation-testing and fitting the model is
    in `notebooks/model_fit_colab.ipynb`, and it's suited for running in Google Colab

        - The notebook uses the dataset generated in the previous step, if you want to recreate the steps
          I suggest you zip the dataset into an archive and you upload it into your google drive so you can load it in Colab

3.  The colab notebook generates a zip archive of the model, which can be downloaded and used after extraction. The directory `models-def`
    contains some pre-trained models. For now the `main.py` script uses the models `model-binary-separatechannels` and `model-4classes-separatechannels`
