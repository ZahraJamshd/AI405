# Speaker Identification and Voice-Activity Detection

This repository contains the T-03 final project for the Artificial Intelligence course.

The project studies a lightweight serial pipeline for detecting speech and identifying enrolled speakers in continuous meeting audio.

## Phase 1

Phase 1 uses three recordings from the AMI Meeting Corpus: `ES2002d`, `ES2008d`, and `ES2014d`. The selected data contains 12 meeting-speaker identities and three 300-second evaluation excerpts containing speech, silence, and overlapping speech.

The baseline uses:

- A pretrained Silero VAD for speech-interval detection.
- A pretrained SpeechBrain ECAPA-TDNN model for 192-dimensional speaker embeddings.
- Five clean enrollment segments per speaker.
- Cosine similarity against 12 enrolled speaker centroids.

Phase 1 configures and verifies the two baseline components. Final VAD F1, top-1 speaker-identification accuracy, and error analysis are reserved for Phase 2.

## Repository Files

- `T03.ipynb`: Notebook containing the Phase 1 baseline setup.
- `Phase1.pdf`: Phase 1 report.
- `requirements.txt`: pinned Python dependencies.
- `README.md`: project overview and execution instructions.

## Running the Notebook

1. Open `T03.ipynb` in Google Colab.
2. Use a CPU runtime.
3. Select `Runtime > Restart session and run all`.
4. Internet access is required to download the selected AMI recordings and pretrained models.

## Project Status

Phase 1 completed. Phase 2 will connect Silero VAD and ECAPA-TDNN serially and evaluate the pipeline on the selected continuous excerpts.