# Fake News Detection

[![CI](https://github.com/shxamill/fake_news_detection/actions/workflows/ci.yml/badge.svg)](https://github.com/shxamill/fake_news_detection/actions/workflows/ci.yml) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

> [!IMPORTANT]
> **Archived.** This is an earlier copy of the project. The maintained version, with the same classifier and Streamlit app in a cleaner layout, is **[shxamill/fake_news](https://github.com/shxamill/fake_news)**.

An educational fake-news classification project with a Streamlit demo, serialized scikit-learn model artifacts, and Jupyter notebooks for preprocessing and model training.

## What is included

- A Streamlit interface for entering a news article or social post.
- A saved classifier and TF-IDF vectorizer.
- A notebook for preprocessing text data.
- A notebook for training a TF-IDF and Logistic Regression model.

## Important limitations

This project is not a reliable fact-checking authority. A classifier prediction is only an estimate based on its training data and can be wrong, biased, or out of date. Verify important claims against independent, reputable primary sources.

The training notebooks refer to CSV files that are not included in this repository. The expected data paths are described below; training from scratch is therefore not reproducible from the committed files alone.

## Repository layout

~~~text
.
├── requirements.txt
└── Fake-News-Detection1-main/
    └── Fake-News-Detection1-main/
        ├── app/app.py
        ├── model/
        │   ├── fake_news_model.pkl
        │   └── tfidf.pkl
        └── notebooks/
            ├── 01_data_preprocessing.ipynb
            └── 02_model_training.ipynb
~~~

The nested directory name is retained from the imported project folder.

## Setup

Use Python 3.11 or another version compatible with the listed packages.

~~~bash
python -m venv .venv
~~~

Activate the environment:

~~~bash
# Linux / macOS
source .venv/bin/activate

# Windows PowerShell
.venv\Scripts\Activate.ps1
~~~

Install dependencies from the repository root:

~~~bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
~~~

## Run the Streamlit application

Change into the inner project directory before running the app. The application loads the model using paths relative to that directory.

~~~bash
cd Fake-News-Detection1-main/Fake-News-Detection1-main
streamlit run app/app.py
~~~

Streamlit prints the local URL in the terminal.

## Training notebooks and data

The notebooks expect files in the inner project directory under data/:

- data/Fake.csv
- data/True.csv
- data/cleaned_news.csv

These datasets are not committed. Obtain and use datasets only when their provenance and usage rights are clear. Do not commit private or restricted datasets. The preprocessing notebook creates intermediate data needed by the model-training notebook.

## Model artifact safety

The .pkl files are Python pickle artifacts. Only load them when you trust their source: pickle deserialization can execute code. Model/vectorizer compatibility can also depend on the scikit-learn version used to create them; that version is not currently recorded alongside the artifacts.

## Development checks

There is no dedicated automated unit-test suite yet. Run:

~~~bash
python -m compileall -q Fake-News-Detection1-main/Fake-News-Detection1-main/app
~~~

For changes to preprocessing or training, record the dataset source, feature construction, train/test methodology, evaluation metrics, and package versions.

## Contribution and support

See [CONTRIBUTING.md](CONTRIBUTING.md), [SECURITY.md](SECURITY.md), [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md), and [SUPPORT.md](SUPPORT.md).

## License

This project is licensed under the [MIT License](LICENSE).
