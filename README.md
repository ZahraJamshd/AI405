# Speaker Identification and Voice-Activity Detection

This repository contains the T-03 final project for the Artificial Intelligence course.

The project evaluates a lightweight serial pipeline for detecting speech and identifying enrolled speakers in continuous meeting audio.

## Dataset and Baseline

The project uses three recordings from the AMI Meeting Corpus: `ES2002d`, `ES2008d`, and `ES2014d`. The selected data contains 12 meeting-speaker identities and three continuous 300-second evaluation excerpts containing speech, silence, speaker changes, and overlapping speech.

The pipeline uses:

- A pretrained Silero VAD model for speech-interval detection.
- A pretrained SpeechBrain ECAPA-TDNN model for 192-dimensional speaker embeddings.
- Five clean enrollment segments per speaker.
- Cosine similarity against 12 enrolled speaker centroids.
- A simple similarity-margin heuristic for exploratory overlap analysis.

No model training or fine-tuning is performed.

## Evaluation Results

The serial pipeline processes 256 VAD-detected intervals across 15 minutes of evaluation audio.

- Overall frame-level VAD F1: `0.9028`
- Overall top-1 speaker-identification accuracy: `0.9125`
- Eligible single-speaker intervals: `160`
- Short-interval speaker accuracy: `0.8500`
- Long-interval speaker accuracy: `0.9750`
- Exact overlap-pair matches: `1` out of `59`

The overlap result is exploratory and is not treated as a main evaluation metric.

## Repository Files

- `T03.ipynb`: Executed Colab notebook containing the baseline, serial pipeline, evaluation, error analysis, and demo.
- `Phase1.pdf`: Phase 1 report.
- `Phase2.pdf`: Phase 2 report.
- `requirements.txt`: Pinned Python dependencies.
- `README.md`: Project overview and execution instructions.

## Running the Notebook

1. Open `T03.ipynb` in Google Colab.
2. Use a CPU runtime.
3. Select `Runtime > Restart session and run all`.
4. Internet access is required to download the selected AMI recordings and pretrained models.

## Project Status

Phase 1 and Phase 2 are complete.