# Contributing

This repository contains a Streamlit inference app and notebooks for a text-classification workflow.

## Setup

From the repository root:

~~~bash
python -m venv .venv
python -m pip install -r requirements.txt
~~~

Activate the virtual environment before installing or running the project.

## Run the application

~~~bash
cd Fake-News-Detection1-main/Fake-News-Detection1-main
streamlit run app/app.py
~~~

Run from the inner project directory because the app loads model/ using a relative path.

## Training workflow

The notebooks expect CSV files under the inner project's data/ directory. The expected filenames are Fake.csv, True.csv, and cleaned_news.csv. The dataset files are not included in this repository; do not add private or unlicensed data.

## Before opening a pull request

- Run python -m compileall -q Fake-News-Detection1-main/Fake-News-Detection1-main/app.
- Check notebook JSON validity and execute affected notebook cells when the required data is available.
- Keep text preprocessing consistent between training and inference.
- Record training data provenance, dependency versions, and evaluation methodology when changing model artifacts.
- Do not describe a classifier prediction as proof that a claim is true or false.
- Never load untrusted pickle files or commit secrets and personal information.

There is currently no dedicated automated model test suite.
