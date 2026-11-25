# MNIST Digit Predictor

Course project (DS533, artificial neural networks): a small Streamlit app that classifies a handwritten
digit from an uploaded image with a neural network trained on the MNIST dataset.

## How it works

1. The image is converted to grayscale and resized to 28 x 28 pixels.
2. Pixel values are scaled to the range 0 to 1.
3. The saved Keras model (`mnist_model.keras`) predicts the digit and the app shows the result.

The model expects a **white digit on a black background**, like MNIST itself. A dark digit on white paper
should be inverted first or the prediction will be poor (checked: 97.5% on the first 1,000 MNIST test images,
11.6% when the same images are inverted). The app does not invert for you.

## Run locally

```sh
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt     # TensorFlow 2.16.1 needs Python 3.9 to 3.12
streamlit run app.py
```

Open the address Streamlit prints (usually http://localhost:8501) and upload a `.png` or `.jpg` image.

## Files

| File | What it is |
|---|---|
| `app.py` | Streamlit app |
| `mnist_model.keras` | Trained model (about 1.2 MB) |
| `requirements.txt` | Python dependencies |
