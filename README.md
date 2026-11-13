# codealpha_task1-AI-
# Language Translation Tool

> CodeAlpha Artificial Intelligence Internship | Task 1: Language Translation Tool

A web-based translation tool built with Python and Gradio. The user enters text, picks a source and target language, and gets the translation instantly, with optional text-to-speech.

## Objective

Create a user interface where a user can enter text and select source and target languages, send the text to a translation API, and display the translated result clearly on screen.

## Features

- Text input with source and target language dropdowns
- **Auto Detect** option for the source language
- Translation through Google Translate (via `deep-translator`)
- **Automatic fallback** to the MyMemory translation service if Google rate-limits the request
- **Swap button** to reverse the language direction in one click
- **Text-to-speech:** hear the translation read aloud (via `gTTS`)
- Example inputs for quick testing
- Error handling for empty input and failed requests

## How It Works

1. The user types text and chooses the source and target languages.
2. The app sends the text to Google Translate through `deep-translator`.
3. If Google refuses the request (for example, rate limiting), the app retries once, then falls back to MyMemory. When the source is "Auto Detect", `langdetect` identifies the language for the backup service.
4. The translated text is shown in the output box.
5. If text-to-speech is enabled, `gTTS` converts the translation to an MP3 that plays in the interface.


## Project Structure

```
CodeAlpha_LanguageTranslationTool/
├── Language_Translation_Tool.ipynb   # Full notebook with outputs
├── requirements.txt                  # Dependencies
└── README.md
```

## How to Run

### Option 1: Google Colab (recommended)
1. Open the notebook in Colab (**File > Open notebook > GitHub**, paste this repo's URL).
2. Run the cell. It installs the libraries and starts the app.
3. Use the interface shown in the notebook, or open the public `gradio.live` link printed in the output.

### Option 2: Locally
```bash
git clone https://github.com/YOUR_USERNAME/CodeAlpha_LanguageTranslationTool.git
cd CodeAlpha_LanguageTranslationTool
pip install -r requirements.txt
```
Copy the code from the notebook into a file such as `app.py`, remove the `!pip install` line, and run:
```bash
python app.py
```

## Tech Stack

Python, Gradio, deep-translator (Google Translate and MyMemory), gTTS, langdetect

## Limitations

- An internet connection is required for translation and text-to-speech.
- The free Google Translate endpoint can rate-limit requests, especially on shared servers such as Google Colab. The MyMemory backup handles this but accepts only about 500 characters per request.
- Text-to-speech does not support every language that translation supports.
- The Gradio `share` link only works while the notebook cell is running.

## Future Improvements

- Document and file translation
- Translation history
- Speech-to-text input
- Switch to the official Google Cloud Translation API for production use

## Author

**zainshahji**


Built as part of the [CodeAlpha](https://www.codealpha.tech) Artificial Intelligence Internship.
